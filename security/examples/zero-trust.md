# Zero Trust

Zero-trust access architecture — verify every request, never trust by network location.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Cognito | `mxgraph.aws4.cognito` |
| IAM | `mxgraph.aws4.identity_and_access_management` |
| Network Firewall | `mxgraph.aws4.network_firewall` |
| API Gateway | `mxgraph.aws4.api_gateway` |
| Lambda | `mxgraph.aws4.lambda_function` |
| KMS | `mxgraph.aws4.key_management_service` |
| CloudTrail | `mxgraph.aws4.cloudtrail` |

## Example

Zero-trust API access with identity verification, encryption, and continuous logging:

```plantuml
@startuml
left to right direction

mxgraph.aws4.users "Client\nApp" as client

rectangle "Identity Verification" {
  mxgraph.aws4.cognito "Cognito\n(MFA)" as auth
  mxgraph.aws4.identity_and_access_management "IAM\nPolicy" as iam
}

rectangle "Network Micro-segmentation" {
  mxgraph.aws4.network_firewall "Network\nFirewall" as nfw
  mxgraph.aws4.api_gateway "API\nGateway" as apigw
}

rectangle "Protected Service" {
  mxgraph.aws4.lambda_function "Service\nLambda" as fn
  mxgraph.aws4.key_management_service "KMS\nEncryption" as kms
  mxgraph.aws4.encrypted_data "Encrypted\nData" as enc
}

mxgraph.aws4.cloudtrail "Audit\nLog" as trail

client --> auth : "MFA login"
auth --> iam : "JWT + role"
iam --> nfw : "signed request"
nfw --> apigw
apigw --> fn
fn --> kms : "decrypt"
kms --> enc
fn ..> trail : "audit"
apigw ..> trail : "audit"
@enduml
```

## Pattern Notes

1. **Verify explicitly**: every request requires MFA-backed identity — no implicit trust from VPN or network
2. **Least privilege**: IAM policies scoped to specific API actions, resources, and conditions (IP, time)
3. **Micro-segmentation**: Network Firewall + API Gateway enforce per-service access boundaries
4. **Continuous audit**: CloudTrail logs every API call for post-hoc verification and anomaly detection

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Verified Access | `mxgraph.aws4.verified_access` | Per-request app access checks |
| Verified Perms | `mxgraph.aws4.verified_permissions` | Cedar-based fine-grained authz |
| WAF | `mxgraph.aws4.waf` | L7 request inspection |
| Private CA | `mxgraph.aws4.private_certificate_authority` | mTLS certificate issuance |
| STS | `mxgraph.aws4.sts` | Federated temp credentials |
| VPC Lattice | `mxgraph.aws4.vpc_lattice` | Service-to-service networking |
