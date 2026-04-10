# Compliance Audit

Continuous compliance monitoring with Config rules, Audit Manager, and centralized audit trail.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Config | `mxgraph.aws4.config` |
| Audit Manager | `mxgraph.aws4.audit_manager` |
| CloudTrail | `mxgraph.aws4.cloudtrail` |
| CloudTrail Lake | `mxgraph.aws4.cloudtrail_cloudtrail_lake` |
| Security Lake | `mxgraph.aws4.security_lake` |
| S3 | `mxgraph.aws4.s3` |
| Lambda | `mxgraph.aws4.lambda_function` |

## Example

Continuous compliance with automated evidence collection and audit reporting:

```plantuml
@startuml
left to right direction

rectangle "Resource Monitoring" {
  mxgraph.aws4.config "Config\nRules" as cfg
  mxgraph.aws4.cloudtrail "CloudTrail" as trail
}

rectangle "Audit & Evidence" {
  mxgraph.aws4.audit_manager "Audit\nManager" as audit
  mxgraph.aws4.cloudtrail_cloudtrail_lake "CloudTrail\nLake" as lake
}

rectangle "Centralized Storage" {
  mxgraph.aws4.security_lake "Security\nLake" as slake
  mxgraph.aws4.s3 "Compliance\nReports (S3)" as s3
}

rectangle "Remediation" {
  mxgraph.aws4.lambda_function "Auto\nRemediate" as fn
}

cfg ..> audit : "compliance status"
trail ..> lake : "API events"
lake --> slake
cfg --> fn : "non-compliant"
audit --> s3 : "evidence"
slake --> s3 : "OCSF logs"
@enduml
```

## Pattern Notes

1. **Config Rules**: evaluates resource configurations against compliance policies (CIS, PCI-DSS, SOC2)
2. **Audit Manager**: collects evidence from Config, CloudTrail, and other sources for audit frameworks
3. **CloudTrail Lake**: SQL-queryable event storage for forensic investigation across accounts
4. **Security Lake**: normalizes logs to OCSF format from multiple sources into a single data lake

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Artifact | `mxgraph.aws4.artifact` | Compliance report downloads |
| Trusted Advisor | `mxgraph.aws4.trusted_advisor` | Best-practice recommendations |
| Well-Architected | `mxgraph.aws4.well_architected_tool` | Framework review assessments |
| License Manager | `mxgraph.aws4.license_manager` | Software license compliance |
| Backup Audit | `mxgraph.aws4.backup_audit_manager` | Backup policy compliance |
| SSM Compliance | `mxgraph.aws4.systems_manager_compliance` | Patch & config compliance |
