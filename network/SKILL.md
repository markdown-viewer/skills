---
name: network
description: Create network topology diagrams using PlantUML syntax with industry-standard device icons. Best for LAN/WAN diagrams, enterprise networks, cloud infrastructure, and vendor-specific diagrams (Cisco, Citrix, etc.). Uses mxgraph stencil icons for network devices with auto-layout. NOT for general software modeling (use uml) or cloud service architecture (use cloud).
metadata:
  author: Network diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Network Topology Diagram Generator

**Quick Start:** Choose topology type → Declare stencil icons for network devices → Connect with arrow syntax → Group into zones with `rectangle` or `package` → Wrap in ` ```plantuml ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use `mxgraph.*` stencil syntax for network device icons (routers, switches, firewalls, etc.)
- Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`
- Use `rectangle "Zone" { ... }` or `package "Zone" { ... }` to group devices into network zones
- Use `cloud "Name" { ... }` for cloud/Internet shapes
- Bidirectional physical links use `--` (no arrow); directed flows use `-->`
- Dashed lines for VPN/wireless/logical links use `..` or `..>`
- Use `skinparam` for global styling

**Full stencil reference:** See [stencils/README.md](../uml/stencils/README.md) for 9500+ available icons.

## Mxgraph Stencil Syntax

```
mxgraph.<namespace>.<icon> "Label" as <alias>
mxgraph.<namespace>.<icon> "Label" as <alias> #color
mxgraph.<namespace>.<icon> <alias>
```

### Common Network Stencil Families

| Family | Prefix | Typical Icons |
|--------|--------|---------------|
| Networks | `mxgraph.networks.*` | `switch`, `router`, `firewall`, `server`, `pc`, `laptop`, `wireless_hub`, `cloud` |
| Cisco | `mxgraph.cisco.*` | `routers.router`, `switches.layer_3_switch`, `security.firewall`, `servers.fileserver` |
| Cisco 19 | `mxgraph.cisco19.*` | `nexus_9300`, `nexus_5k`, `fabric_interconnect`, `ucs_5108_blade_chassis`, `storage` |
| Cisco SAFE | `mxgraph.cisco_safe.security_icons.*` | `ngfw`, `waf`, `ids`, `siem`, `nac`, `vpn`, `ddos`, `malware_sandbox` |
| Citrix | `mxgraph.citrix2.*` | `netscaler_gateway`, `storefront`, `delivery_controller`, `vda` |

### Connection Types

| Syntax | Meaning | Use Case |
|--------|---------|----------|
| `A -- B` | Solid line, no arrow | Physical Ethernet / LAN link |
| `A --> B` | Solid line with arrow | Directed traffic flow |
| `A .. B` | Dashed line, no arrow | VPN tunnel / wireless link |
| `A ..> B` | Dashed line with arrow | Directed VPN / logical flow |
| `A -- B : "label"` | Labeled connection | Link description |

### Quick Example

```plantuml
@startuml
mxgraph.networks.cloud "Internet" as inet
mxgraph.networks.firewall "Firewall" as fw
mxgraph.networks.router "Router" as rtr
mxgraph.networks.switch "Switch" as sw

rectangle "Office LAN" {
  mxgraph.networks.pc "PC 1" as pc1
  mxgraph.networks.pc "PC 2" as pc2
  mxgraph.networks.server "Server" as srv
}

inet -- fw
fw -- rtr
rtr -- sw
sw -- pc1
sw -- pc2
sw -- srv
@enduml
```

## Network Diagram Types

| Type | Purpose | Key Stencils | Example |
|------|---------|--------------|---------|
| LAN | Local network topology | `mxgraph.networks.*` | [lan-topology.md](examples/lan-topology.md) |
| WAN | Wide area network | `mxgraph.cisco.*` | [wan-topology.md](examples/wan-topology.md) |
| Enterprise | Corporate infrastructure | `mxgraph.cisco.*` | [enterprise-network.md](examples/enterprise-network.md) |
| Cisco | Cisco-specific icons | `mxgraph.cisco.*` | [cisco-network.md](examples/cisco-network.md) |
| Wireless | WiFi network | `mxgraph.networks.*` | [wireless-network.md](examples/wireless-network.md) |
| Cloud Hybrid | On-premise + Cloud | `mxgraph.cisco.*` | [hybrid-cloud.md](examples/hybrid-cloud.md) |
| Citrix | Virtual Apps/Desktops | `mxgraph.citrix2.*` | [citrix-network.md](examples/citrix-network.md) |
| Security | Defence-in-depth | `mxgraph.cisco_safe.security_icons.*` | [security-architecture.md](examples/security-architecture.md) |
| Data Center | Spine-Leaf / UCS / SAN | `mxgraph.cisco19.*` | [datacenter-network.md](examples/datacenter-network.md) |
