# Data Protection

Sensitive data discovery and classification with Macie, encryption enforcement, and access controls.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Macie | `mxgraph.aws4.macie` |
| KMS | `mxgraph.aws4.key_management_service` |
| Encrypted Data | `mxgraph.aws4.encrypted_data` |
| S3 | `mxgraph.aws4.s3` |
| Security Hub | `mxgraph.aws4.security_hub` |
| Lambda | `mxgraph.aws4.lambda_function` |
| Config | `mxgraph.aws4.config` |

## Example

PII discovery pipeline with automatic classification, encryption enforcement, and alerting:

```plantuml
@startuml
left to right direction

rectangle "Data Storage" {
  mxgraph.aws4.s3 "Customer\nData (S3)" as s3a
  mxgraph.aws4.s3 "Logs\nBucket" as s3b
  mxgraph.aws4.s3 "Uploads\nBucket" as s3c
}

rectangle "Discovery & Classification" {
  mxgraph.aws4.macie "Macie\nScanner" as macie
  mxgraph.aws4.config "Config\nRules" as cfg
}

rectangle "Protection" {
  mxgraph.aws4.key_management_service "KMS" as kms
  mxgraph.aws4.lambda_function "Auto\nEncrypt" as fn
  mxgraph.aws4.encrypted_data "Encrypted\nPII" as enc
}

rectangle "Alerting" {
  mxgraph.aws4.security_hub "Security\nHub" as hub
}

s3a --> macie
s3b --> macie
s3c --> macie
macie ..> hub : "PII found"
macie --> fn : "unencrypted PII"
cfg ..> hub : "policy violation"
fn --> kms : "encrypt"
fn --> enc
@enduml
```

## Pattern Notes

1. **Macie scanning**: ML-based discovery of PII (names, SSNs, credit cards) across all S3 buckets
2. **Auto-remediation**: Lambda auto-encrypts unprotected sensitive data when Macie detects it
3. **Config enforcement**: rules ensure S3 bucket encryption, public access block, and versioning are enabled
4. **Security Hub alerts**: centralized view of all data protection findings for security team triage

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| GuardDuty | `mxgraph.aws4.guardduty` | Threat detection on S3 access |
| Inspector | `mxgraph.aws4.inspector` | Vulnerability scanning |
| Access Analyzer | `mxgraph.aws4.access_analyzer` | Public/cross-account access audit |
| S3 Object Lock | `mxgraph.aws4.s3_object_lock` | WORM compliance for objects |
| Backup | `mxgraph.aws4.backup` | Automated data backup policy |
| Clean Rooms | `mxgraph.aws4.clean_rooms` | Privacy-safe data collaboration |
