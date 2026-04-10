# WAN Topology Diagram

Shows a wide area network connecting multiple remote sites through a central backbone.

## Key Elements

| Component | Stencil |
|-----------|---------|
| HQ Building | `mxgraph.cisco.buildings.generic_building` |
| Branch Office | `mxgraph.cisco.buildings.branch_office` |
| Telecommuter House | `mxgraph.cisco.buildings.telecommuter_house` |
| Edge Router | `mxgraph.cisco.routers.router` |
| PIX Firewall | `mxgraph.cisco.security.pix_firewall` |
| Ground Terminal | `mxgraph.cisco.wireless.ground_terminal` |
| Satellite Dish | `mxgraph.cisco.wireless.satellite_dish` |
| Satellite | `mxgraph.cisco.wireless.satellite` |
| VPN Gateway | `mxgraph.cisco.hubs_and_gateways.vpn_gateway` |

## WAN Connection Types

| Syntax | Use Case |
|--------|----------|
| `A -- B` | MPLS primary backbone |
| `A .. B` | Internet VPN / backup link |
| `A -- B : "label"` | Labeled leased line |

## Example

Enterprise WAN with headquarters, two branch offices, remote worker, and satellite site:

```plantuml
@startuml
cloud "MPLS / VPN" as mpls
cloud "Internet" as inet

rectangle "Headquarters" {
  mxgraph.cisco.buildings.generic_building "HQ" as hq_bld
  mxgraph.cisco.security.pix_firewall "Firewall" as hq_fw
  mxgraph.cisco.routers.router "Router" as hq_rtr
}

rectangle "Branch Office 1" {
  mxgraph.cisco.buildings.branch_office "Branch 1" as br1_bld
  mxgraph.cisco.routers.router "Router" as br1_rtr
}

rectangle "Branch Office 2" {
  mxgraph.cisco.buildings.branch_office "Branch 2" as br2_bld
  mxgraph.cisco.routers.router "Router" as br2_rtr
}

rectangle "Satellite Site" {
  mxgraph.cisco.wireless.satellite "Satellite" as sat
  mxgraph.cisco.wireless.satellite_dish "Dish" as sat_dish
  mxgraph.cisco.wireless.ground_terminal "Ground\nTerminal" as sat_gnd
}

rectangle "Remote Access" {
  mxgraph.cisco.buildings.telecommuter_house "Remote\nWorker" as remote
  mxgraph.cisco.hubs_and_gateways.vpn_gateway "VPN GW" as vpn_gw
}

hq_bld -- hq_fw
hq_fw -- hq_rtr
hq_rtr -- mpls
br1_bld -- br1_rtr
br1_rtr -- mpls
br2_bld -- br2_rtr
br2_rtr -- mpls
sat .. sat_dish
sat_dish -- sat_gnd
sat_gnd -- mpls
remote .. vpn_gw
vpn_gw .. inet
inet .. mpls
@enduml
```

## Pattern Notes

1. **Cisco stencil family** — WAN diagrams use `mxgraph.cisco.*` for all device icons including buildings, routers, firewalls, and satellite equipment
2. **MPLS/VPN cloud** at the center represents the WAN backbone using `cloud "MPLS / VPN"`. All site routers connect to this cloud. A separate Internet cloud is used for VPN-based remote access
3. **Solid links** (`--`) represent physical MPLS backbone connections — primary, reliable links
4. **Dashed links** (`..`) represent VPN tunnels over the Internet or wireless satellite segments — visually distinguishing logical overlay connections from physical circuits
5. **Building stencils** distinguish site types: `generic_building` for HQ, `branch_office` for branches, `telecommuter_house` for remote workers
6. **Zone containers** use `rectangle "Name" { ... }` to group each site's devices together
7. **All WAN links are bidirectional** — using `--` (no arrow) for physical links

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Layer 3 Switch | `mxgraph.cisco.switches.layer_3_switch` | Core switching at sites |
| ASA 5500 | `mxgraph.cisco.misc.asa_5500` | Advanced firewall appliance |
| Access Point | `mxgraph.cisco.misc.access_point` | Site wireless coverage |
| Workstation | `mxgraph.cisco.computers_and_peripherals.workstation` | Desktop endpoint |
| Standard Host | `mxgraph.cisco.servers.standard_host` | Site server |
| Storage Server | `mxgraph.cisco.servers.storage_server` | Remote site storage |

