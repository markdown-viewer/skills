---
name: security
description: Create security architecture diagrams using PlantUML syntax with identity, encryption, firewall, and compliance stencil icons. Best for IAM flows, zero-trust architectures, encryption pipelines, compliance auditing, and threat detection. NOT for general cloud infra (use cloud skill) or general software modeling (use uml).
metadata:
  author: Security diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Security Architecture Diagram Generator

**Quick Start:** Define trust boundaries → Place identity/encryption/firewall icons → Connect with access flows → Group into security zones → Wrap in ` ```plantuml ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use `left to right direction` for access flows (User → AuthN → AuthZ → Resource)
- Use `mxgraph.aws4.*` stencil syntax for security service icons
- Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`
- Use `rectangle "Trust Boundary" { ... }` for security zones
- Directed flows use `-->`, audit/async flows use `..>` (dashed)

**Full stencil reference:** See [stencils/README.md](../uml/stencils/README.md) for 9500+ available icons.

## Mxgraph Stencil Syntax

```
mxgraph.aws4.<icon> "Label" as <alias>
```

### Identity & Access Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| IAM | `identity_and_access_management`, `identity_access_management_iam_roles_anywhere` | Identity policies & roles |
| SSO/Directory | `cognito`, `ad_connector`, `directory_service`, `cloud_directory` | User authentication & federation |
| STS | `sts`, `sts_alternate` | Temporary security credentials |
| Organizations | `organizations`, `organizations_account`, `organizations_organizational_unit` | Multi-account governance |

### Encryption & Secrets Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| KMS | `key_management_service`, `key_management_service_external_key_store` | Key management & encryption |
| Secrets | `secrets_manager` | Secrets rotation & storage |
| Certificates | `certificate_manager`, `private_certificate_authority` | TLS certificate lifecycle |
| HSM | `cloudhsm` | Hardware security module |
| Encryption | `encrypted_data` | Encrypted data at rest |

### Network Security Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| Firewall | `network_firewall`, `network_firewall_endpoints`, `firewall_manager` | Network traffic filtering |
| WAF | `generic_firewall` | Web application firewall |
| Shield | `shield`, `shield_shield_advanced`, `shield2` | DDoS protection |
| Security Group | `security_group`, `group_security_group` | Instance-level firewall |

### Threat Detection & Compliance Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| Detection | `guardduty`, `detective`, `inspector` | Threat detection & investigation |
| Data Protection | `macie` | Sensitive data discovery |
| Compliance | `security_hub`, `security_hub_finding`, `audit_manager`, `config` | Compliance posture & audit |
| Logging | `cloudtrail`, `cloudtrail_cloudtrail_lake`, `security_lake` | Audit trail & log aggregation |
| Governance | `control_tower`, `organizations` | Multi-account governance |
| Incident | `security_incident_response` | Incident management |

### Connection Types

| Syntax | Meaning | Use Case |
|--------|---------|----------|
| `A --> B` | Solid arrow | Auth flow / access request |
| `A ..> B` | Dashed arrow | Audit event / async detection |
| `A -- B` | Solid line | Trust relationship |
| `A --> B : "label"` | Labeled connection | Describe protocol or credential |

### Quick Example

```plantuml
@startuml
left to right direction
mxgraph.aws4.users "Users" as users
mxgraph.aws4.cognito "Cognito" as auth
mxgraph.aws4.identity_and_access_management "IAM" as iam

rectangle "Protected Resources" {
  mxgraph.aws4.s3 "Data (S3)" as s3
  mxgraph.aws4.encrypted_data "Encrypted" as enc
}

users --> auth : "login"
auth --> iam : "token"
iam --> s3
s3 --> enc
@enduml
```

## Security Architecture Types

| Type | Purpose | Key Stencils | Example |
|------|---------|--------------|---------|
| IAM & AuthN | Identity and authentication | `cognito`, `identity_and_access_management`, `sts` | [iam-authn.md](examples/iam-authn.md) |
| Encryption Pipeline | Data encryption at rest/in-transit | `key_management_service`, `certificate_manager`, `secrets_manager` | [encryption-pipeline.md](examples/encryption-pipeline.md) |
| Network Security | Perimeter defense & firewalls | `network_firewall`, `shield`, `security_group` | [network-security.md](examples/network-security.md) |
| Threat Detection | Automated threat response | `guardduty`, `detective`, `security_hub` | [threat-detection.md](examples/threat-detection.md) |
| Compliance Audit | Governance & audit trail | `config`, `audit_manager`, `cloudtrail`, `security_lake` | [compliance-audit.md](examples/compliance-audit.md) |
| Zero Trust | Zero-trust access model | `cognito`, `identity_and_access_management`, `network_firewall` | [zero-trust.md](examples/zero-trust.md) |
| Data Protection | Sensitive data classification | `macie`, `encrypted_data`, `key_management_service` | [data-protection.md](examples/data-protection.md) |
| Multi-account Gov | Organization-wide security | `organizations`, `control_tower`, `security_hub` | [multi-account-governance.md](examples/multi-account-governance.md) |
