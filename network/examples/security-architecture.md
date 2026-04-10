# Network Security Architecture

Shows a defence-in-depth security architecture with layered perimeter, internal, and monitoring zones using Cisco SAFE icons.

## Key Elements

| Component | Stencil |
|-----------|---------|
| DDoS Protection | `mxgraph.cisco_safe.security_icons.ddos` |
| WAF | `mxgraph.cisco_safe.security_icons.waf` |
| NGFW | `mxgraph.cisco_safe.security_icons.ngfw` |
| IDS / IPS | `mxgraph.cisco_safe.security_icons.ids` |
| NGIPS | `mxgraph.cisco_safe.security_icons.ngips` |
| NAC | `mxgraph.cisco_safe.security_icons.nac` |
| VPN | `mxgraph.cisco_safe.security_icons.vpn` |
| ISE | `mxgraph.cisco_safe.security_icons.ise` |
| SIEM | `mxgraph.cisco_safe.security_icons.siem` |
| Log Management | `mxgraph.cisco_safe.security_icons.log_management` |
| Malware Sandbox | `mxgraph.cisco_safe.security_icons.malware_sandbox` |
| AMP | `mxgraph.cisco_safe.security_icons.amp` |
| Email Security | `mxgraph.cisco_safe.security_icons.email` |
| Firewall | `mxgraph.cisco_safe.security_icons.firewall` |
| UTM | `mxgraph.cisco_safe.security_icons.utm` |

## Connection Types

| Syntax | Meaning |
|--------|---------|
| `--` | Physical / primary link (solid, bidirectional) |
| `-->` | Directed traffic flow |
| `..>` | Inspection / analysis flow (dashed) |

## Example

Defence-in-depth architecture with perimeter, internal, and SOC monitoring layers:

```plantuml
@startuml
' --- External ---
mxgraph.networks.cloud "Internet" as inet
mxgraph.cisco19.router "Edge Router" as edge

rectangle "Perimeter Zone" {
  mxgraph.cisco_safe.security_icons.ddos "DDoS\nProtection" as ddos
  mxgraph.cisco_safe.security_icons.waf "WAF" as waf
  mxgraph.cisco_safe.security_icons.ngfw "NGFW" as ngfw
  mxgraph.cisco_safe.security_icons.vpn "VPN\nGateway" as vpn
}

rectangle "Internal Zone" {
  mxgraph.cisco_safe.security_icons.ngips "NGIPS" as ips
  mxgraph.cisco_safe.security_icons.nac "NAC" as nac
  mxgraph.cisco_safe.security_icons.ise "ISE" as ise
  mxgraph.cisco_safe.security_icons.email "Email\nSecurity" as email
  mxgraph.cisco_safe.security_icons.amp "AMP\nEndpoint" as amp
  mxgraph.cisco19.l3_switch "Core Switch" as sw
}

rectangle "SOC / Monitoring" {
  mxgraph.cisco_safe.security_icons.siem "SIEM" as siem
  mxgraph.cisco_safe.security_icons.log_management "Log\nManagement" as logs
  mxgraph.cisco_safe.security_icons.malware_sandbox "Malware\nSandbox" as sandbox
}

' --- Perimeter path ---
inet -- edge
edge --> ddos
ddos --> waf
waf --> ngfw
ngfw --> sw
vpn --> ngfw

' --- Internal security ---
sw --> ips
sw --> nac
nac -- ise
sw --> email
sw --> amp

' --- SOC feeds ---
ngfw ..> siem
ips ..> siem
nac ..> logs
email ..> sandbox
siem -- logs
@enduml
```

## Pattern Notes

1. **`mxgraph.cisco_safe.security_icons.*`** — dedicated security appliance icons from Cisco SAFE framework; draw-uml auto-sets colors
2. **Layered zones**: `rectangle "Perimeter Zone"`, `rectangle "Internal Zone"`, `rectangle "SOC / Monitoring"` map to defence-in-depth layers
3. **Directed flow** `-->` for traffic path through security appliances (DDoS → WAF → NGFW → core)
4. **Dashed flow** `..>` for inspection/telemetry feeds from appliances to SOC (NGFW → SIEM, IPS → SIEM)
5. **VPN ingress** enters through the NGFW — `vpn --> ngfw` represents remote-access or site-to-site termination
6. **NAC + ISE pair** bidirectional `--` since they exchange posture/authentication data
7. **Email → Sandbox** dashed `..>` for detonation analysis of suspicious attachments

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Talos | `mxgraph.cisco_safe.security_icons.talos` | Threat intelligence feed |
| IDS | `mxgraph.cisco_safe.security_icons.ids` | Intrusion detection system |
| Forensics | `mxgraph.cisco_safe.security_icons.inspection_forensics` | Forensic analysis |
| NBA | `mxgraph.cisco_safe.security_icons.nba` | Network behavior analysis |
| TrustSec | `mxgraph.cisco_safe.security_icons.trustsec` | Network segmentation policy |
| UTM | `mxgraph.cisco_safe.security_icons.utm` | Unified threat management |
