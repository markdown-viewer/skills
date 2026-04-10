# Threat Detection

Automated threat detection and investigation with GuardDuty, Detective, and Security Hub.

## Key Elements

| Component | Stencil |
|-----------|---------|
| GuardDuty | `mxgraph.aws4.guardduty` |
| Detective | `mxgraph.aws4.detective` |
| Security Hub | `mxgraph.aws4.security_hub` |
| Security Hub Finding | `mxgraph.aws4.security_hub_finding` |
| Inspector | `mxgraph.aws4.inspector` |
| CloudTrail | `mxgraph.aws4.cloudtrail` |
| Lambda | `mxgraph.aws4.lambda_function` |

## Example

Automated threat detection pipeline with centralized findings and investigation:

```plantuml
@startuml
left to right direction

rectangle "Detection Sources" {
  mxgraph.aws4.guardduty "GuardDuty" as gd
  mxgraph.aws4.inspector "Inspector" as insp
  mxgraph.aws4.cloudtrail "CloudTrail" as trail
}

rectangle "Aggregation" {
  mxgraph.aws4.security_hub "Security\nHub" as hub
  mxgraph.aws4.security_hub_finding "Findings" as findings
}

rectangle "Investigation" {
  mxgraph.aws4.detective "Detective" as det
}

rectangle "Response" {
  mxgraph.aws4.lambda_function "Auto\nRemediate" as fn
  mxgraph.aws4.security_incident_response "Incident\nResponse" as ir
}

gd ..> hub : "findings"
insp ..> hub : "CVEs"
trail ..> hub : "events"
hub --> findings
findings --> det : "investigate"
findings --> fn : "auto-fix"
findings --> ir : "escalate"
@enduml
```

## Pattern Notes

1. **GuardDuty**: ML-based threat detection on VPC flow logs, DNS logs, and CloudTrail events
2. **Inspector**: scans EC2 instances and Lambda functions for known CVEs and network exposure
3. **Security Hub**: aggregates findings from all detection services into normalized ASFF format
4. **Detective**: graph-based investigation — traces suspicious activity across resources and time

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Macie | `mxgraph.aws4.macie` | Sensitive data scanning (S3) |
| Config | `mxgraph.aws4.config` | Configuration compliance checks |
| CloudWatch | `mxgraph.aws4.cloudwatch` | Metric alarms & dashboards |
| SNS | `mxgraph.aws4.sns` | Alert notification delivery |
| EventBridge | `mxgraph.aws4.eventbridge` | Finding event routing |
| Audit Manager | `mxgraph.aws4.audit_manager` | Compliance evidence collection |
