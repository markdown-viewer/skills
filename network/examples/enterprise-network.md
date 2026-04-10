# Enterprise Network Diagram

Shows a multi-tier enterprise network with DMZ, internal zones, and security layers.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Edge Router | `mxgraph.cisco.routers.router` |
| PIX Firewall | `mxgraph.cisco.security.pix_firewall` |
| ASA 5500 | `mxgraph.cisco.misc.asa_5500` |
| L3 Switch | `mxgraph.cisco.switches.layer_3_switch` |
| Workgroup Switch | `mxgraph.cisco.switches.workgroup_switch` |
| Standard Host | `mxgraph.cisco.servers.standard_host` |
| Storage Server | `mxgraph.cisco.servers.storage_server` |
| Access Point | `mxgraph.cisco.misc.access_point` |
| Hub | `mxgraph.cisco.hubs_and_gateways.100baset_hub` |

## Network Tiers

| Tier | Role | Key Devices |
|------|------|-------------|
| Core | High-speed backbone | L3 switches |
| Distribution | Policy, security | PIX firewall, ASA, WAN routers |
| Access | End-user connectivity | Workgroup switches, APs, hubs |

## Example

Enterprise three-tier network with DMZ, server farm, and campus access:

```plantuml
@startuml
cloud "Internet" as inet

mxgraph.cisco.routers.router "Edge Router" as edge_rtr
mxgraph.cisco.security.pix_firewall "PIX Firewall" as pix_fw

rectangle "DMZ" {
  mxgraph.cisco.misc.asa_5500 "ASA 5500" as asa
  mxgraph.cisco.servers.standard_host "Web Server 1" as web1
  mxgraph.cisco.servers.standard_host "Web Server 2" as web2
}

rectangle "Server Farm" {
  mxgraph.cisco.switches.layer_3_switch "L3 Switch" as l3sw
  mxgraph.cisco.servers.standard_host "App Server" as app_srv
  mxgraph.cisco.servers.storage_server "Storage" as storage
}

rectangle "WAN" {
  mxgraph.cisco.routers.router "WAN Router" as wan_rtr
  cloud "Branch" as branch
}

rectangle "Campus A" {
  mxgraph.cisco.switches.workgroup_switch "Switch A" as sw_a
  mxgraph.cisco.misc.access_point "AP" as ap_a
  mxgraph.cisco.hubs_and_gateways.100baset_hub "Hub" as hub_a
}

rectangle "Campus B" {
  mxgraph.cisco.switches.workgroup_switch "Switch B" as sw_b
  mxgraph.cisco.misc.access_point "AP" as ap_b
  mxgraph.cisco.hubs_and_gateways.100baset_hub "Hub" as hub_b
}

inet -- edge_rtr
edge_rtr -- pix_fw
pix_fw -- asa
pix_fw -- l3sw
pix_fw -- wan_rtr
asa -- web1
asa -- web2
l3sw -- app_srv
l3sw -- storage
wan_rtr -- branch
l3sw -- sw_a
l3sw -- sw_b
sw_a -- ap_a
sw_a -- hub_a
sw_b -- ap_b
sw_b -- hub_b
@enduml
```

## Pattern Notes

1. **Three-tier hierarchy** — Internet → Edge Router → PIX Firewall → Distribution zones (DMZ, Server Farm, WAN) → Access zones (Campus A, Campus B)
2. **Zone containers** use `rectangle "Zone Name" { ... }` to group devices into functional areas — DMZ, Server Farm, WAN, and campus access zones
3. **DMZ zone** places ASA 5500 as the internal firewall protecting web servers
4. **Server Farm zone** contains L3 switch as the distribution hub connecting to app servers and storage
5. **WAN zone** uses router → cloud pattern to represent branch office connectivity
6. **Campus access zones** each contain a workgroup switch with access point and hub downstream — representing wired + wireless user segments
7. **All edges are bidirectional** — using `--` (no arrows) for physical network links
8. **Cisco stencil family** — all devices use `mxgraph.cisco.*` icons

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| VPN Gateway | `mxgraph.cisco.hubs_and_gateways.vpn_gateway` | Remote access VPN |
| Laptop | `mxgraph.cisco.computers_and_peripherals.laptop` | Mobile user endpoints |
| Printer | `mxgraph.cisco.computers_and_peripherals.printer` | Network printers |
| File Server | `mxgraph.cisco.servers.fileserver` | Shared file storage |
| Satellite | `mxgraph.cisco.wireless.satellite` | WAN backup link |
| Branch Office | `mxgraph.cisco.buildings.branch_office` | Remote site icon |

