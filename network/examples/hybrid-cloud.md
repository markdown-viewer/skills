# Hybrid Cloud Network Diagram

Shows a hybrid cloud architecture connecting on-premise infrastructure with cloud services.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Edge Router | `mxgraph.cisco.routers.router` |
| PIX Firewall | `mxgraph.cisco.security.pix_firewall` |
| VPN Concentrator | `mxgraph.cisco_safe.architecture.vpn_concentrator` |
| Core Switch | `mxgraph.cisco.switches.layer_3_switch` |
| Server | `mxgraph.cisco.servers.standard_host` |
| Storage | `mxgraph.cisco.servers.storage_server` |
| Data Center | `mxgraph.cisco19.data_center` |

## Connection Types

| Syntax | Use Case |
|--------|----------|
| `A .. B` | Site-to-Site VPN tunnel |
| `A -- B` | Internal LAN link |
| `A ..> B` | Directed VPN flow |

## Example

Enterprise hybrid cloud connecting on-premise data center to cloud services via VPN:

```plantuml
@startuml
cloud "Internet" as inet

rectangle "On-Premise Data Center" {
  mxgraph.cisco.routers.router "Router" as onprem_rtr
  mxgraph.cisco.security.pix_firewall "Firewall" as onprem_fw
  mxgraph.cisco_safe.architecture.vpn_concentrator "VPN" as onprem_vpn
  mxgraph.cisco.switches.layer_3_switch "L3 Switch" as onprem_sw
  mxgraph.cisco.servers.standard_host "Server 1" as srv1
  mxgraph.cisco.servers.standard_host "Server 2" as srv2
  mxgraph.cisco.servers.storage_server "Storage" as nas
}

rectangle "Cloud (IaaS)" {
  rectangle "Compute" {
    mxgraph.cisco19.data_center "Data Center" as cloud_dc
    mxgraph.cisco.servers.standard_host "VM 1" as vm1
    mxgraph.cisco.servers.standard_host "VM 2" as vm2
  }
  rectangle "Storage / DB" {
    mxgraph.cisco.servers.storage_server "Cloud\nStorage 1" as cs1
    mxgraph.cisco.servers.storage_server "Cloud\nStorage 2" as cs2
    mxgraph.cisco_safe.architecture.vpn_concentrator "VPN" as cloud_vpn
  }
}

onprem_rtr -- onprem_fw
onprem_fw -- onprem_vpn
onprem_fw -- onprem_sw
onprem_sw -- srv1
onprem_sw -- srv2
onprem_sw -- nas
onprem_rtr -- inet
onprem_vpn ..> inet
inet ..> cloud_vpn
cloud_vpn -- cloud_dc
cloud_dc -- vm1
cloud_dc -- vm2
cloud_dc -- cs1
cloud_dc -- cs2
@enduml
```

## Pattern Notes

1. **Two contrasting zones** — `rectangle "On-Premise Data Center" { ... }` for on-prem and `rectangle "Cloud (IaaS)" { ... }` for cloud, clearly separating the two environments
2. **Cloud sub-zones** use nested `rectangle` containers to group compute resources and storage/DB within the cloud boundary
3. **VPN tunnel** uses `..>` (dashed with arrow) for directed VPN flow through Internet, visually distinct from solid `--` LAN links
4. **VPN concentrator pair** — one on each side at the boundary of on-prem and cloud zones, establishing site-to-site tunnel endpoints
5. **Internal LAN links** use `--` (solid, no arrows) for bidirectional physical connections
6. **On-prem topology**: Router → Firewall → VPN concentrator (for cloud) + L3 switch (for internal) → servers/storage
7. **Cloud topology**: VPN concentrator → Data center → VMs + storage, keeping a similar hierarchical pattern to on-prem
## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Access Point | `mxgraph.cisco.misc.access_point` | On-prem wireless |
| Branch Office | `mxgraph.cisco.buildings.branch_office` | Remote site icon |
| ASA 5500 | `mxgraph.cisco.misc.asa_5500` | Next-gen firewall |
| Workgroup Switch | `mxgraph.cisco.switches.workgroup_switch` | Access layer switch |
| Generic Building | `mxgraph.cisco.buildings.generic_building` | HQ/datacenter icon |
| Laptop | `mxgraph.cisco.computers_and_peripherals.laptop` | Endpoint device |
