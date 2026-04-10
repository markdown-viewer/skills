# LAN Topology Diagram

Shows a typical local area network with workstations, server, firewall, and Internet connection.

## Key Elements

| Component | Stencil |
|-----------|---------|
| PC | `mxgraph.networks.pc` |
| Laptop | `mxgraph.networks.laptop` |
| Switch | `mxgraph.networks.switch` |
| Wireless Hub | `mxgraph.networks.wireless_hub` |
| Server | `mxgraph.networks.server` |
| Printer | `mxgraph.networks.printer` |
| Firewall | `mxgraph.networks.firewall` |
| Cloud | `mxgraph.networks.cloud` |
| Mobile | `mxgraph.networks.mobile` |

## Connection Types

| Syntax | Description |
|--------|-------------|
| `A -- B` | Wired Ethernet link |
| `A .. B` | Wireless WiFi link |

## Example

Small office LAN with wired and wireless segments:

```plantuml
@startuml
mxgraph.networks.cloud "Internet" as inet
mxgraph.networks.firewall "Firewall" as fw
mxgraph.networks.switch "Core Switch" as sw_core

rectangle "Wired Segment" {
  mxgraph.networks.switch "Switch" as sw1
  mxgraph.networks.pc "PC 1" as pc1
  mxgraph.networks.pc "PC 2" as pc2
  mxgraph.networks.pc "PC 3" as pc3
  mxgraph.networks.server "Server" as srv
  mxgraph.networks.printer "Printer" as prn
}

rectangle "Wireless Segment" {
  mxgraph.networks.wireless_hub "AP" as ap
  mxgraph.networks.laptop "Laptop 1" as lap1
  mxgraph.networks.laptop "Laptop 2" as lap2
  mxgraph.networks.mobile "Mobile 1" as mob1
  mxgraph.networks.mobile "Mobile 2" as mob2
}

inet -- fw
fw -- sw_core
sw_core -- sw1
sw_core -- ap
sw1 -- pc1
sw1 -- pc2
sw1 -- pc3
sw1 -- srv
sw1 -- prn
ap .. lap1
ap .. lap2
ap .. mob1
ap .. mob2
@enduml
```

## Pattern Notes

1. **`mxgraph.networks.*` stencil family** — all LAN diagrams use this library for unified device icons
2. **Zone containers** use `rectangle "Zone Name" { ... }` to group devices into network segments
3. **Wired connections** use `--` (solid line, no arrow) for bidirectional Ethernet links
4. **Wireless connections** use `..` (dashed line) to visually distinguish WiFi links from wired connections
5. **Two-segment topology**: Core switch splits into wired segment (switch → PCs/server/printer) and wireless segment (AP → laptops/mobiles), each inside its own zone container
6. **Firewall placement**: Single firewall between Internet cloud and core switch — the standard small office pattern
7. **No arrows**: All physical network links are bidirectional (`--` not `-->`)

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Router | `mxgraph.networks.router` | Gateway device |
| NAS Filer | `mxgraph.networks.nas_filer` | Network attached storage |
| Hub | `mxgraph.networks.hub` | Legacy hub device |
| Tablet | `mxgraph.networks.tablet` | Wireless tablet client |
| Monitor | `mxgraph.networks.monitor` | Workstation display |
| Security Camera | `mxgraph.networks.security_camera` | IP surveillance camera |

