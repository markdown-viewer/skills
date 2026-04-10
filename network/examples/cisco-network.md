# Cisco Network Diagram

Shows a multi-branch WAN topology using Cisco network icons with firewalls and routers.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Router | `mxgraph.cisco.routers.router` |
| Firewall | `mxgraph.cisco.security.firewall` |
| Layer 3 Switch | `mxgraph.cisco.switches.layer_3_switch` |
| Workgroup Switch | `mxgraph.cisco.switches.workgroup_switch` |
| Workstation | `mxgraph.cisco.computers_and_peripherals.workstation` |
| Laptop | `mxgraph.cisco.computers_and_peripherals.laptop` |
| Printer | `mxgraph.cisco.computers_and_peripherals.printer` |
| File Server | `mxgraph.cisco.servers.fileserver` |

## Connection Types

| Syntax | Use Case |
|--------|----------|
| `A -- B` | Physical LAN/WAN link (bidirectional) |
| `A -- B` (inside zones) | Internal device connections |

## Example

Multi-branch WAN with Internet core, HQ data center, and two branch offices connected via firewalls and routers:

```plantuml
@startuml
cloud "Internet" as internet

rectangle "HQ Data Center" {
  mxgraph.cisco.routers.router "Core Router" as router_hq
  mxgraph.cisco.security.firewall "Firewall" as fw_hq
  mxgraph.cisco.switches.layer_3_switch "L3 Switch" as l3switch
  mxgraph.cisco.servers.fileserver "File Server" as server1
  mxgraph.cisco.servers.fileserver "App Server" as server2
  mxgraph.cisco.computers_and_peripherals.workstation "User" as ws_hq1
  mxgraph.cisco.computers_and_peripherals.workstation "User" as ws_hq2
  mxgraph.cisco.computers_and_peripherals.printer "Printer" as printer_hq
}

rectangle "Branch Office 1" {
  mxgraph.cisco.routers.router "Router" as router_b1
  mxgraph.cisco.security.firewall "Firewall" as fw_b1
  mxgraph.cisco.switches.workgroup_switch "Switch" as switch_b1
  mxgraph.cisco.computers_and_peripherals.laptop "User" as laptop_b1
  mxgraph.cisco.computers_and_peripherals.workstation "User" as ws_b1
}

rectangle "Branch Office 2" {
  mxgraph.cisco.routers.router "Router" as router_b2
  mxgraph.cisco.security.firewall "Firewall" as fw_b2
  mxgraph.cisco.switches.workgroup_switch "Switch" as switch_b2
  mxgraph.cisco.computers_and_peripherals.laptop "User" as laptop_b2
  mxgraph.cisco.computers_and_peripherals.printer "Printer" as printer_b2
}

internet -- router_hq
internet -- router_b1
internet -- router_b2
router_hq -- fw_hq
fw_hq -- l3switch
l3switch -- server1
l3switch -- server2
l3switch -- ws_hq1
l3switch -- ws_hq2
l3switch -- printer_hq
router_b1 -- fw_b1
fw_b1 -- switch_b1
switch_b1 -- laptop_b1
switch_b1 -- ws_b1
router_b2 -- fw_b2
fw_b2 -- switch_b2
switch_b2 -- laptop_b2
switch_b2 -- printer_b2
@enduml
```

## Pattern Notes

1. **Cisco stencil family** — all devices use `mxgraph.cisco.*` icons (routers, switches, firewalls, servers, peripherals)
2. **No arrows**: Network links use `--` for bidirectional physical connections
3. **Zone grouping**: `rectangle "Zone Name" { ... }` groups each site's devices — HQ, Branch 1, Branch 2
4. **Cloud shape**: `cloud "Internet"` for the Internet backbone at the top
5. **Layered layout**: Top-down: Internet → Router → Firewall → Switch → End devices
6. **Consistent topology per site**: Each site follows Router → Firewall → Switch → endpoints pattern

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Access Point | `mxgraph.cisco.misc.access_point` | Wireless connectivity |
| VPN Gateway | `mxgraph.cisco.hubs_and_gateways.vpn_gateway` | Site-to-site VPN |
| Standard Host | `mxgraph.cisco.servers.standard_host` | Generic server icon |
| ASA 5500 | `mxgraph.cisco.misc.asa_5500` | Advanced firewall appliance |
| Storage Server | `mxgraph.cisco.servers.storage_server` | NAS/SAN storage |
| Satellite Dish | `mxgraph.cisco.wireless.satellite_dish` | WAN satellite link |

