# Citrix Network Diagram

Shows a Citrix Virtual Apps and Desktops infrastructure with NetScaler Gateway.

## Key Elements

| Stencil | Alias suggestion |
|---------|-----------------|
| `mxgraph.citrix2.netscaler_gateway` | nsg |
| `mxgraph.citrix2.storefront` | sf |
| `mxgraph.citrix2.delivery_controller` | dc1, dc2 |
| `mxgraph.citrix2.vda` | vda1, vda2 |
| `mxgraph.citrix2.hypervisor_xenserver` | xen1, xen2 |
| `mxgraph.citrix2.director` | dir |
| `mxgraph.citrix2.citrix_license_server` | lic |
| `mxgraph.citrix2.site_database` | sitedb |
| `mxgraph.citrix2.external_users` | ext |
| `mxgraph.citrix2.laptop` | lap |
| `mxgraph.citrix2.tablet` | tab |
| `mxgraph.citrix2.firewall` | fw_ext, fw_int |
| `mxgraph.citrix2.windows_app` | winapp |
| `mxgraph.citrix2.linux_app` | linapp |
| `mxgraph.citrix2.virtual_desktop` | vdesk |

## Connection Types

| Syntax | Meaning |
|--------|---------|
| `--` | Wired / primary link (solid, bidirectional) |
| `..` | Secondary / backup path (dashed) |

## Example

Citrix Virtual Apps and Desktops deployment with DMZ, internal network, and data center zones:

```plantuml
@startuml
' --- External clients ---
mxgraph.citrix2.external_users "External\nUsers" as ext
mxgraph.citrix2.laptop "Laptop" as lap
mxgraph.citrix2.tablet "Mobile" as tab
mxgraph.citrix2.firewall "Firewall" as fw_ext

rectangle "DMZ" {
  mxgraph.citrix2.netscaler_gateway "NetScaler\nGateway" as nsg
  mxgraph.citrix2.storefront "StoreFront" as sf
  mxgraph.citrix2.firewall "Firewall" as fw_int
}

rectangle "Internal Network" {
  mxgraph.citrix2.delivery_controller "Delivery\nController 1" as dc1
  mxgraph.citrix2.delivery_controller "Delivery\nController 2" as dc2
  mxgraph.citrix2.director "Director" as dir
  mxgraph.citrix2.citrix_license_server "License\nServer" as lic
  mxgraph.citrix2.site_database "Site\nDatabase" as sitedb
  mxgraph.citrix2.hypervisor_xenserver "XenServer 1" as xen1
  mxgraph.citrix2.hypervisor_xenserver "XenServer 2" as xen2
  mxgraph.citrix2.vda "VDA" as vda1
  mxgraph.citrix2.vda "VDA" as vda2
  mxgraph.citrix2.vda "VDA" as vda3
  mxgraph.citrix2.windows_app "Windows\nApps" as winapp
  mxgraph.citrix2.linux_app "Linux\nApps" as linapp
  mxgraph.citrix2.virtual_desktop "Virtual\nDesktop" as vdesk
}

' --- External → Firewall ---
ext -- fw_ext
lap -- fw_ext
tab -- fw_ext

' --- Firewall → DMZ ---
fw_ext -- nsg
fw_ext -- sf
nsg -- dc1
sf -- fw_int
fw_int .. dc1

' --- Internal links ---
dc1 -- dc2
dc2 -- dir
dc1 -- lic
dc2 -- sitedb
dc1 -- xen1
dc2 -- xen2
xen1 -- vda1
xen1 -- vda2
xen2 -- vda3
vda1 -- winapp
vda2 -- linapp
vda3 -- vdesk
@enduml
```

## Pattern Notes

1. **`mxgraph.citrix2.*` stencil family** — all Citrix infrastructure icons; draw-uml auto-sets default colors
2. **No arrows**: all network links use `--` (solid, bidirectional)
3. **Dashed = secondary path**: use `..` for backup/fallback connections (e.g. internal firewall → controller)
4. **Zone containers**: `rectangle "DMZ" { ... }` and `rectangle "Internal Network" { ... }` separate security zones
5. **Layered layout**: Clients → Firewall → DMZ (NetScaler + StoreFront) → Internal Firewall → Delivery Controllers → Hypervisors → VDAs → Apps
6. **HA pair**: two `delivery_controller` and two `hypervisor_xenserver` for redundancy
## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Cloud Connector | `mxgraph.citrix2.cloud_connector` | Citrix Cloud communication |
| HDX | `mxgraph.citrix2.hdx` | HDX protocol indicator |
| Machine Catalog | `mxgraph.citrix2.machine_catalog` | VM catalog management |
| Provisioning Svr | `mxgraph.citrix2.citrix_provisioning_server` | PVS image streaming |
| App Layering | `mxgraph.citrix2.citrix_app_layering` | App layer management |
| DaaS | `mxgraph.citrix2.daas` | Desktop-as-a-Service |
