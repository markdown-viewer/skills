# Security Architecture

Security controls mapped across motivation (requirements), application (services), and technology (infrastructure).

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Motivation | `Motivation_Requirement`, `Motivation_Constraint`, `Motivation_Principle`, `Motivation_Goal` |
| Application | `Application_Component`, `Application_Service` |
| Technology | `Technology_Node`, `Technology_SystemSoftware`, `Technology_CommunicationNetwork` |

## Example

Zero-trust security model: security principles → requirements → controls across identity, network, and data layers:

```plantuml
@startuml
!include <archimate/Archimate>

rectangle "Security Principles" {
  Motivation_Goal(zeroTrust, "Zero Trust Security")
  Motivation_Principle(leastPriv, "Least Privilege")
  Motivation_Principle(defDepth, "Defense in Depth")
  Motivation_Principle(encrypt, "Encrypt Everything")
}

rectangle "Security Requirements" {
  Motivation_Requirement(mfa, "Multi-Factor Auth")
  Motivation_Requirement(rbac, "Role-Based Access")
  Motivation_Requirement(audit, "Audit Logging")
  Motivation_Requirement(tlsReq, "TLS Everywhere")
  Motivation_Constraint(compliance, "SOC2 Compliance")
}

rectangle "Identity & Access" {
  Application_Component(idp, "Identity Provider")
  Application_Service(authSvc, "Auth Service")
  Application_Service(policyEng, "Policy Engine")
}

rectangle "Network Security" {
  Technology_SystemSoftware(waf, "Web App Firewall")
  Technology_SystemSoftware(fw, "Network Firewall")
  Technology_CommunicationNetwork(vpn, "VPN Tunnel")
}

rectangle "Data Protection" {
  Technology_SystemSoftware(kms, "Key Mgmt Service")
  Technology_SystemSoftware(dlp, "Data Loss Prevention")
  Application_Component(siem, "SIEM Platform")
}

Rel_Aggregation(zeroTrust, leastPriv, "")
Rel_Aggregation(zeroTrust, defDepth, "")
Rel_Aggregation(zeroTrust, encrypt, "")

Rel_Influence(leastPriv, mfa, "drives")
Rel_Influence(leastPriv, rbac, "drives")
Rel_Influence(defDepth, audit, "drives")
Rel_Influence(encrypt, tlsReq, "drives")

Rel_Realization(authSvc, mfa, "")
Rel_Realization(policyEng, rbac, "")
Rel_Realization(siem, audit, "")
Rel_Realization(kms, tlsReq, "")
Rel_Assignment(idp, authSvc, "")

Rel_Serving(waf, authSvc, "protects")
Rel_Serving(fw, vpn, "secures")
Rel_Serving(dlp, siem, "feeds")
Rel_Association(compliance, audit, "mandates")
@enduml
```

## Pattern Notes

1. **Motivation → Implementation** — Goals decompose into Principles (`Rel_Aggregation`), Principles influence Requirements (`Rel_Influence`), Controls realize Requirements (`Rel_Realization`)
2. **Constraint** — `Motivation_Constraint` for external compliance mandates (SOC2) that link to requirements
3. **Three security domains** — Identity & Access, Network Security, Data Protection each in their own rectangle
4. **Cross-layer traceability** — From high-level goal (Zero Trust) down to specific technology controls (WAF, KMS, DLP), fully traceable through ArchiMate relationships
5. **Serving** — `Rel_Serving` shows technology components protecting/serving application services
