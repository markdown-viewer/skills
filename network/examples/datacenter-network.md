# Data Center Network

Shows a Cisco-based data center with Spine-Leaf fabric, UCS compute, and SAN storage using Cisco 19 icons.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Nexus 9300 (Spine) | `mxgraph.cisco19.nexus_9300` |
| Nexus 5K (Leaf) | `mxgraph.cisco19.nexus_5k` |
| Fabric Interconnect | `mxgraph.cisco19.fabric_interconnect` |
| UCS Blade Chassis | `mxgraph.cisco19.ucs_5108_blade_chassis` |
| UCS C-Series Server | `mxgraph.cisco19.ucs_c_series_server` |
| FC Director MDS 9000 | `mxgraph.cisco19.fibre_channel_director_mds_9000` |
| Storage | `mxgraph.cisco19.storage` |
| Firewall | `mxgraph.cisco19.firewall` |
| Router | `mxgraph.cisco19.router` |
| L3 Switch | `mxgraph.cisco19.l3_switch` |
| Load Balancer | `mxgraph.cisco19.load_balancer` |

## Connection Types

| Syntax | Meaning |
|--------|---------|
| `--` | Physical link (Ethernet / FC, bidirectional) |
| `..` | Management / out-of-band link (dashed) |

## Example

Spine-Leaf fabric with UCS compute pods and SAN storage:

```plantuml
@startuml
mxgraph.cisco19.router "Border Router" as border
mxgraph.cisco19.firewall "DC Firewall" as fw

rectangle "Spine Layer" {
  mxgraph.cisco19.nexus_9300 "Spine-1" as sp1
  mxgraph.cisco19.nexus_9300 "Spine-2" as sp2
}

rectangle "Leaf Layer" {
  mxgraph.cisco19.nexus_5k "Leaf-1" as lf1
  mxgraph.cisco19.nexus_5k "Leaf-2" as lf2
  mxgraph.cisco19.nexus_5k "Leaf-3" as lf3
}

rectangle "Compute Pod A" {
  mxgraph.cisco19.fabric_interconnect "FI-A" as fia
  mxgraph.cisco19.ucs_5108_blade_chassis "Blade\nChassis 1" as blade1
  mxgraph.cisco19.ucs_5108_blade_chassis "Blade\nChassis 2" as blade2
}

rectangle "Compute Pod B" {
  mxgraph.cisco19.fabric_interconnect "FI-B" as fib
  mxgraph.cisco19.ucs_c_series_server "Rack\nServer 1" as rack1
  mxgraph.cisco19.ucs_c_series_server "Rack\nServer 2" as rack2
}

rectangle "SAN Storage" {
  mxgraph.cisco19.fibre_channel_director_mds_9000 "MDS 9000\nFC Director" as mds
  mxgraph.cisco19.storage "Primary\nStorage" as stor1
  mxgraph.cisco19.storage "Backup\nStorage" as stor2
}

' --- North-South ---
border -- fw
fw -- sp1
fw -- sp2

' --- Spine ↔ Leaf full mesh ---
sp1 -- lf1
sp1 -- lf2
sp1 -- lf3
sp2 -- lf1
sp2 -- lf2
sp2 -- lf3

' --- Leaf → Compute ---
lf1 -- fia
lf2 -- fib
fia -- blade1
fia -- blade2
fib -- rack1
fib -- rack2

' --- Leaf → SAN ---
lf3 -- mds
mds -- stor1
mds -- stor2

' --- Management ---
sp1 .. sp2
@enduml
```

## Pattern Notes

1. **`mxgraph.cisco19.*`** — modern Cisco icon set with data center equipment (Nexus, UCS, MDS); draw-uml auto-sets colors
2. **Spine-Leaf full mesh**: every Spine connects to every Leaf via `--`, providing equal-cost multi-path
3. **Compute Pods** use `rectangle` zones — Pod A has Fabric Interconnect + Blade Chassis, Pod B has FI + Rack Servers
4. **SAN zone** separated with FC Director (MDS 9000) connecting to storage arrays
5. **Management link** `sp1 .. sp2` dashed line for out-of-band/keepalive between spines
6. **North-South path**: Border Router → Firewall → Spine layer (dual-homed for redundancy)

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Nexus 7K | `mxgraph.cisco19.nexus_7k` | Core aggregation switch |
| Nexus 9500 | `mxgraph.cisco19.nexus_9500` | Modular spine switch |
| Blade Server | `mxgraph.cisco19.blade_server` | Individual blade unit |
| VPN Concentrator | `mxgraph.cisco19.vpn_concentrator` | Remote access VPN |
| WLC | `mxgraph.cisco19.wireless_lan_controller` | Centralized WLAN mgmt |
| UPS | `mxgraph.cisco19.ups` | Power backup unit |
