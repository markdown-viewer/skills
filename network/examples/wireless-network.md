# Wireless Network Diagram

Shows a wireless network topology with access points, controllers, and client devices.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Wireless Hub / AP | `mxgraph.networks.wireless_hub` |
| Laptop | `mxgraph.networks.laptop` |
| Mobile | `mxgraph.networks.mobile` |
| Tablet | `mxgraph.networks.tablet` |
| PC | `mxgraph.networks.pc` |
| Switch | `mxgraph.networks.switch` |
| Router | `mxgraph.networks.router` |
| Firewall | `mxgraph.networks.firewall` |
| Server | `mxgraph.networks.server` |
| Cloud | `mxgraph.networks.cloud` |
| Printer | `mxgraph.networks.printer` |

## Wireless Connection Styles

| Syntax | Description |
|--------|-------------|
| `A .. B` | WiFi wireless link (dashed) |
| `A -- B` | Wired Ethernet backhaul |

## Example

Enterprise wireless network with WLAN controller, multiple access points, and mixed client devices:

```plantuml
@startuml
mxgraph.networks.cloud "Internet" as inet
mxgraph.networks.firewall "Firewall" as fw
mxgraph.networks.router "Router" as rtr
mxgraph.networks.switch "Core Switch" as sw_core
mxgraph.networks.server "WLAN Controller\n/ RADIUS" as srv

rectangle "Floor 1 — WiFi Zone" {
  mxgraph.networks.wireless_hub "AP-1" as ap1
  mxgraph.networks.laptop "Laptop 1" as lap1
  mxgraph.networks.laptop "Laptop 2" as lap2
  mxgraph.networks.mobile "Mobile" as mob1
  mxgraph.networks.tablet "Tablet" as tab1
  mxgraph.networks.printer "Printer" as prn1
}

rectangle "Floor 2 — WiFi Zone" {
  mxgraph.networks.wireless_hub "AP-2" as ap2
  mxgraph.networks.laptop "Laptop 3" as lap3
  mxgraph.networks.mobile "Mobile 1" as mob2
  mxgraph.networks.mobile "Mobile 2" as mob3
  mxgraph.networks.pc "PC" as pc1
  mxgraph.networks.tablet "Tablet" as tab2
}

inet -- fw
fw -- rtr
rtr -- sw_core
sw_core -- srv
sw_core -- ap1
sw_core -- ap2
ap1 .. lap1
ap1 .. lap2
ap1 .. mob1
ap1 .. tab1
ap1 .. prn1
ap2 .. lap3
ap2 .. mob2
ap2 .. mob3
ap2 .. pc1
ap2 .. tab2
@enduml
```

## Pattern Notes

1. **`mxgraph.networks.*` stencil family** — wireless diagrams use the same networks library as LAN diagrams; draw-uml auto-sets colors
2. **Wireless connections** use `..` (dashed line) between `wireless_hub` and client devices to visually distinguish WiFi from wired
3. **Wired backhaul** from APs to core switch uses `--` (solid line) — solid vs dashed clearly separates wired and wireless segments
4. **Floor/zone containers** use `rectangle "Floor N — WiFi Zone" { ... }` to group each AP's coverage area with its client devices
5. **WLAN Controller / RADIUS server** connects to core switch via wired `--`, managing all APs centrally
6. **Star topology per AP** — each `wireless_hub` connects to multiple clients via `..` dashed links in a star pattern
7. **Backbone hierarchy**: Internet → Firewall → Router → Core Switch → APs, all wired `--` links

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Monitor | `mxgraph.networks.monitor` | Workstation display/kiosk |
| Scanner | `mxgraph.networks.scanner` | Wireless scanner device |
| NAS Filer | `mxgraph.networks.nas_filer` | Network attached storage |
| Hub | `mxgraph.networks.hub` | Wired backbone extension |
| Security Camera | `mxgraph.networks.security_camera` | Wireless IP camera |
| DVR | `mxgraph.networks.dvr` | Video recording unit |

