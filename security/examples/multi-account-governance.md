# Multi-account Governance

Organization-wide security governance with Control Tower, Organizations, and centralized Security Hub.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Organizations | `mxgraph.aws4.organizations` |
| Organizations Account | `mxgraph.aws4.organizations_account` |
| Organizations OU | `mxgraph.aws4.organizations_organizational_unit` |
| Control Tower | `mxgraph.aws4.control_tower` |
| Security Hub | `mxgraph.aws4.security_hub` |
| GuardDuty | `mxgraph.aws4.guardduty` |
| Config | `mxgraph.aws4.config` |
| CloudTrail | `mxgraph.aws4.cloudtrail` |

## Example

Landing zone with OU structure, guardrails, and centralized security monitoring:

```plantuml
@startuml
left to right direction

rectangle "Management Account" {
  mxgraph.aws4.organizations "Organizations" as org
  mxgraph.aws4.control_tower "Control\nTower" as ct
}

rectangle "Security OU" {
  mxgraph.aws4.organizations_account "Audit\nAccount" as audit
  mxgraph.aws4.organizations_account "Log Archive\nAccount" as logacc
  mxgraph.aws4.security_hub "Security\nHub" as hub
  mxgraph.aws4.cloudtrail "CloudTrail\n(Org)" as trail
}

rectangle "Workload OU" {
  mxgraph.aws4.organizations_account "Prod\nAccount" as prod
  mxgraph.aws4.organizations_account "Dev\nAccount" as dev
  mxgraph.aws4.guardduty "GuardDuty" as gd
  mxgraph.aws4.config "Config" as cfg
}

org --> ct
ct --> audit
ct --> logacc
ct --> prod
ct --> dev
gd ..> hub : "findings"
cfg ..> hub : "compliance"
trail ..> logacc : "org logs"
hub --> audit : "aggregate"
@enduml
```

## Pattern Notes

1. **Control Tower**: automated landing zone with pre-configured guardrails (preventive SCPs + detective Config rules)
2. **OU hierarchy**: Security OU (audit, log archive) + Workload OU (prod, dev) for blast radius isolation
3. **Delegated admin**: Security Hub in audit account aggregates findings from all workload accounts
4. **Org-wide CloudTrail**: single trail across all accounts, archived to dedicated log archive account

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Mgmt Account | `mxgraph.aws4.organizations_management_account` | Org root payer account |
| Firewall Manager | `mxgraph.aws4.firewall_manager` | Cross-account WAF/FW policies |
| Access Analyzer | `mxgraph.aws4.access_analyzer` | Cross-account access review |
| RAM | `mxgraph.aws4.resource_access_manager` | Sharing resources across accounts |
| Service Catalog | `mxgraph.aws4.service_catalog` | Governed self-service provisioning |
| Backup | `mxgraph.aws4.backup` | Org-wide backup policies |
