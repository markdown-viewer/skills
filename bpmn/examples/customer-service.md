# Customer Service

Support ticket lifecycle: intake, triage, escalation tiers, SLA monitoring, and resolution tracking.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Message Start | `mxgraph.bpmn.event.messageStart` |
| End Event | `mxgraph.bpmn.event.end` |
| Escalation End | `mxgraph.bpmn.event.escalationEnd` |
| Exclusive Gateway | `mxgraph.bpmn.gateway2.exclusive` |
| Inclusive Gateway | `mxgraph.bpmn.gateway2.inclusive` |
| Timer Intermediate | `mxgraph.bpmn.event.timerCatching` |
| User Task | `mxgraph.bpmn.user_task` |
| Service Task | `mxgraph.bpmn.service_task` |
| Business Rule Task | `mxgraph.bpmn.business_rule_task` |

## Example

Customer submits ticket → auto-classify → tier 1/2/3 support → SLA monitoring → resolution:

```plantuml
@startuml
left to right direction

mxgraph.bpmn.event.messageStart "Ticket\nReceived" as start
mxgraph.bpmn.service_task "Auto\nClassify" as classify
mxgraph.bpmn.business_rule_task "Priority\nRules" as priority

mxgraph.bpmn.gateway2.exclusive "Support\nTier?" as gw_tier

rectangle "Tier 1 — Self Service" {
  mxgraph.bpmn.service_task "Knowledge\nBase Search" as kb
  mxgraph.bpmn.gateway2.exclusive "Resolved?" as gw_kb
}

rectangle "Tier 2 — Agent" {
  mxgraph.bpmn.user_task "Agent\nInvestigation" as agent
  mxgraph.bpmn.event.timerCatching "SLA\n4h" as sla_t2
  mxgraph.bpmn.gateway2.exclusive "Resolved?" as gw_agent
}

rectangle "Tier 3 — Engineering" {
  mxgraph.bpmn.user_task "Engineer\nDiagnosis" as eng
  mxgraph.bpmn.event.timerCatching "SLA\n24h" as sla_t3
  mxgraph.bpmn.gateway2.exclusive "Resolved?" as gw_eng
}

rectangle "Resolution" {
  mxgraph.bpmn.service_task "Update\nTicket" as update
  mxgraph.bpmn.service_task "Send\nSurvey" as survey
}

mxgraph.bpmn.event.end "Ticket\nClosed" as end_ok
mxgraph.bpmn.event.escalationEnd "SLA\nBreach" as end_esc

start --> classify
classify --> priority
priority --> gw_tier

gw_tier --> kb : "Low"
gw_tier --> agent : "Medium"
gw_tier --> eng : "Critical"

kb --> gw_kb
gw_kb --> update : "Yes"
gw_kb --> agent : "No"

agent --> sla_t2
sla_t2 --> end_esc

agent --> gw_agent
gw_agent --> update : "Yes"
gw_agent --> eng : "No"

eng --> sla_t3
sla_t3 --> end_esc

eng --> gw_eng
gw_eng --> update : "Yes"
gw_eng ..> end_esc : "Unresolved"

update --> survey
survey --> end_ok
@enduml
```

## Pattern Notes

1. **Message Start Event** — `mxgraph.bpmn.event.messageStart` triggers when customer submits a ticket (email, chat, form)
2. **Auto-classification** — `mxgraph.bpmn.service_task` for AI/ML ticket classification; `mxgraph.bpmn.business_rule_task` for priority assignment rules
3. **Three-tier escalation** — Exclusive Gateway routes by priority: Low → self-service KB, Medium → agent, Critical → engineering
4. **Escalation path** — Tier 1 unresolved flows to Tier 2, Tier 2 unresolved flows to Tier 3 — progressive escalation through gateway "No" branches
5. **SLA timers** — `mxgraph.bpmn.event.timerCatching` at each tier monitors response time; timeout triggers `mxgraph.bpmn.event.escalationEnd` for SLA breach alerting
6. **Resolution flow** — All successful resolution paths converge to Update Ticket → Send Survey → Close, ensuring consistent customer feedback collection

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Script Task | `mxgraph.bpmn.script_task` | Automated classification scripts |
| Data Object | `mxgraph.bpmn.data2.dataObject` | Ticket/case documents |
| Error End | `mxgraph.bpmn.event.errorEnd` | Unrecoverable failure paths |
| Signal End | `mxgraph.bpmn.event.signalEnd` | Broadcast SLA breach events |
| Parallel Gateway | `mxgraph.bpmn.gateway2.parallel` | Concurrent task execution |
| Data Input | `mxgraph.bpmn.data2.dataInput` | External KB/CRM data feeds |
