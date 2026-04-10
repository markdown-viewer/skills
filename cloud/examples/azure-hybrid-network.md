# Azure Hybrid Network Architecture

On-premises data center connected to Azure VNet via Site-to-Site VPN.

## Key Elements

| Component | Stencil |
|-----------|---------|
| User | `mxgraph.azure.user` |
| Computer | `mxgraph.azure.computer` |
| Virtual Machine | `mxgraph.azure.virtual_machine` |
| VPN Gateway | `mxgraph.mscae.cloud.vpn_gateway2` |
| On-prem Gateway | `mxgraph.mscae.enterprise.gateway` |
| Load Balancer | `mxgraph.mscae.cloud.azure_load_balancer_feature` |
| Firewall | `mxgraph.office.concepts.firewall` |
| Azure AD | `mxgraph.azure.azure_active_directory` |
| AD Server | `mxgraph.mscae.enterprise.server_directory` |
| Storage | `mxgraph.azure.storage` |

## Example

```plantuml
@startuml
left to right direction

mxgraph.azure.user "Users" as users

rectangle "On-Premises Data Center" {
  mxgraph.azure.computer "Workstation 1" as pc1
  mxgraph.azure.computer "Workstation 2" as pc2
  mxgraph.office.concepts.firewall "Firewall" as fw
  mxgraph.mscae.enterprise.gateway "Gateway" as onprem_gw
  mxgraph.mscae.enterprise.server_directory "AD Server" as ad_server
}

cloud "Azure Cloud" {
  mxgraph.azure.azure_active_directory "Azure AD" as aad

  rectangle "VNet (10.0.0.0/16)" {
    rectangle "Gateway Subnet" {
      mxgraph.mscae.cloud.vpn_gateway2 "VPN Gateway" as vpn_gw
    }

    rectangle "Frontend Subnet" {
      mxgraph.mscae.cloud.azure_load_balancer_feature "Load Balancer" as lb
      mxgraph.azure.virtual_machine "Web VM 1" as vm1
      mxgraph.azure.virtual_machine "Web VM 2" as vm2
    }

    rectangle "Backend Subnet" {
      mxgraph.azure.virtual_machine "App VM 1" as vm3
      mxgraph.azure.virtual_machine "App VM 2" as vm4
      mxgraph.azure.storage "Azure Storage" as storage
    }
  }
}

' On-prem traffic
users --> pc1
pc1 --> fw
pc2 --> fw
fw --> onprem_gw

' Site-to-Site VPN tunnel
onprem_gw ..> vpn_gw : Site-to-Site VPN

' Azure internal
vpn_gw --> lb
lb --> vm1
lb --> vm2
vm1 --> vm3
vm2 --> vm4
vm3 --> storage

' AD Sync
ad_server ..> aad : AD Sync
@enduml
```

## Pattern Notes

1. **Three stencil libraries**: `mxgraph.azure.*`, `mxgraph.mscae.*`, `mxgraph.office.*` — pick correct prefix per component
2. **VPN tunnel**: `..>` for cross-cloud Site-to-Site VPN connection
3. **AD Sync**: `..>` dashed link for directory synchronization across environments
4. **Nested subnets**: VNet → Gateway/Frontend/Backend subnets as nested rectangles

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| NSG | `mxgraph.mscae.cloud.nsg` | Network Security Group |
| ExpressRoute | `mxgraph.mscae.cloud.expressroute` | Dedicated private link |
| App Gateway | `mxgraph.mscae.cloud.application_gateway` | L7 load balancer / WAF |
| Key Vault | `mxgraph.mscae.cloud.key_vault` | Secret management |
| SQL Database | `mxgraph.azure.sql_database` | Managed SQL service |
| Monitor | `mxgraph.mscae.cloud.monitor` | Azure Monitor |
