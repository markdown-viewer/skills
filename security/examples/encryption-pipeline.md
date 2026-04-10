# Encryption Pipeline

End-to-end encryption architecture with KMS key hierarchy, certificate management, and secrets rotation.

## Key Elements

| Component | Stencil |
|-----------|---------|
| KMS | `mxgraph.aws4.key_management_service` |
| CloudHSM | `mxgraph.aws4.cloudhsm` |
| Secrets Manager | `mxgraph.aws4.secrets_manager` |
| Certificate Manager | `mxgraph.aws4.certificate_manager` |
| Private CA | `mxgraph.aws4.private_certificate_authority` |
| Encrypted Data | `mxgraph.aws4.encrypted_data` |
| S3 | `mxgraph.aws4.s3` |
| RDS | `mxgraph.aws4.rds` |

## Example

Data encryption at rest and in transit with centralized key management:

```plantuml
@startuml
left to right direction

rectangle "Key Management" {
  mxgraph.aws4.key_management_service "KMS\n(CMK)" as kms
  mxgraph.aws4.cloudhsm "CloudHSM\n(Root Key)" as hsm
  mxgraph.aws4.secrets_manager "Secrets\nManager" as secrets
}

rectangle "Certificate Authority" {
  mxgraph.aws4.private_certificate_authority "Private\nCA" as pca
  mxgraph.aws4.certificate_manager "ACM\nCertificates" as acm
}

rectangle "Protected Data" {
  mxgraph.aws4.s3 "S3 Bucket" as s3
  mxgraph.aws4.encrypted_data "Encrypted\nObjects" as enc_s3
  mxgraph.aws4.rds "RDS" as rds
  mxgraph.aws4.encrypted_data "Encrypted\nVolumes" as enc_rds
}

hsm --> kms : "root key"
kms --> s3 : "SSE-KMS"
s3 --> enc_s3
kms --> rds : "TDE"
rds --> enc_rds
secrets --> rds : "DB password"
pca --> acm : "issue certs"
acm --> s3 : "TLS in-transit"
@enduml
```

## Pattern Notes

1. **Key hierarchy**: CloudHSM holds root key → KMS holds customer master key → data keys generated per-resource
2. **SSE-KMS**: S3 server-side encryption with KMS-managed keys — automatic envelope encryption
3. **Secrets rotation**: Secrets Manager auto-rotates DB passwords on schedule, applications get latest via API
4. **Private CA**: issues internal TLS certificates for service-to-service mTLS without public trust chain

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| External Key Store | `mxgraph.aws4.key_management_service_external_key_store` | BYOK / external HSM |
| SSL Padlock | `mxgraph.aws4.ssl_padlock` | Visualizing TLS termination |
| Data Encryption Key | `mxgraph.aws4.data_encryption_key` | Envelope encryption detail |
| Payment Crypto | `mxgraph.aws4.payment_cryptography` | PCI payment key management |
| Signer | `mxgraph.aws4.signer` | Code signing verification |
| Macie | `mxgraph.aws4.macie` | Sensitive data discovery |
