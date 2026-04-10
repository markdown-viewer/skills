# Approval Workflow

Multi-level document approval with escalation, parallel review, and auto-approval rules.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Start Event | `mxgraph.bpmn.event.start` |
| End Event | `mxgraph.bpmn.event.end` |
| Exclusive Gateway | `mxgraph.bpmn.gateway2.exclusive` |
| Inclusive Gateway | `mxgraph.bpmn.gateway2.inclusive` |
| Parallel Gateway | `mxgraph.bpmn.gateway2.parallel` |
| Timer Intermediate | `mxgraph.bpmn.event.timerCatching` |
| Escalation End | `mxgraph.bpmn.event.escalationEnd` |
| User Task | `mxgraph.bpmn.user_task` |
| Business Rule Task | `mxgraph.bpmn.business_rule_task` |

## Example

Expense report: auto-approve small amounts, manager review for medium, manager + finance for large:

```plantuml
@startuml
left to right direction

mxgraph.bpmn.event.start "Submit\nExpense" as start
mxgraph.bpmn.business_rule_task "Check\nAmount" as check_rule

mxgraph.bpmn.gateway2.exclusive "Amount\nLevel?" as gw_amount

rectangle "Auto\nApprove" as auto_approve

rectangle "Manager\nPool" {
  mxgraph.bpmn.user_task "Manager\nReview" as mgr_review
  mxgraph.bpmn.gateway2.exclusive "Manager\nDecision?" as gw_mgr
}

rectangle "Finance Pool" {
  mxgraph.bpmn.user_task "Finance\nReview" as fin_review
  mxgraph.bpmn.gateway2.exclusive "Finance\nDecision?" as gw_fin
}

mxgraph.bpmn.event.timerCatching "SLA\n48h" as timer
rectangle "Escalate to\nDirector" as escalate

rectangle "Process\nReimbursement" as reimburse
rectangle "Notify\nRejection" as reject_notify
mxgraph.bpmn.event.end "Approved" as end_ok
mxgraph.bpmn.event.end "Rejected" as end_fail
mxgraph.bpmn.event.escalationEnd "Escalated" as end_esc

start --> check_rule
check_rule --> gw_amount
gw_amount --> auto_approve : "< $100"
gw_amount --> mgr_review : "$100-$5000"
gw_amount --> fin_review : "> $5000"

auto_approve --> reimburse

mgr_review --> timer
timer --> escalate
escalate --> end_esc

mgr_review --> gw_mgr
gw_mgr --> reimburse : "Approve"
gw_mgr --> reject_notify : "Reject"
gw_mgr --> fin_review : "Escalate"

fin_review --> gw_fin
gw_fin --> reimburse : "Approve"
gw_fin --> reject_notify : "Reject"

reimburse --> end_ok
reject_notify --> end_fail
@enduml
```

## Pattern Notes

1. **Business Rule Task** — `mxgraph.bpmn.business_rule_task` checks expense amount against thresholds to route automatically
2. **Three-way routing** — Exclusive Gateway routes to auto-approve (<$100), manager review ($100-$5000), or finance review (>$5000)
3. **Pool containers** — `rectangle "Manager Pool" { ... }` groups reviewer tasks into organizational lanes
4. **SLA Timer** — `mxgraph.bpmn.event.timerCatching` triggers escalation if manager doesn't respond within 48 hours
5. **Escalation End** — `mxgraph.bpmn.event.escalationEnd` for the escalation path, distinct from normal and error endings
6. **Cross-pool escalation** — manager gateway can escalate to finance pool via `gw_mgr --> fin_review : "Escalate"`

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Script Task | `mxgraph.bpmn.script_task` | Automated script execution steps |
| Service Task | `mxgraph.bpmn.service_task` | External system API calls |
| Manual Task | `mxgraph.bpmn.manual_task` | Physical/offline approval tasks |
| Message Start | `mxgraph.bpmn.event.messageStart` | Email or form submission triggers |
| Error End | `mxgraph.bpmn.event.errorEnd` | Exception termination paths |
| Data Object | `mxgraph.bpmn.data2.dataObject` | Expense report documents |
