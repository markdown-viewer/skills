---
name: network
description: Create network topology diagrams using Draw.io XML format with industry-standard device icons. Best for LAN/WAN diagrams, enterprise networks, cloud infrastructure, and vendor-specific diagrams (Cisco, Arista, Fortinet). Built on Draw.io with specialized network stencils. NOT for abstract dependency graphs (use graphviz) or simple flowcharts (use mermaid).
author: Network diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Network Topology Diagram Generator

**Quick Start:** Choose topology type → Add network devices (routers, switches, firewalls) → Connect with appropriate link types → Add labels and zones → Wrap in ` ```drawio ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```drawio ` code fence. NEVER use ` ```xml ` — it will NOT render as a diagram.

## Critical Rules
### Rule 1: Device Stencils Require fillColor
Many device stencils have no default color. Always add `fillColor`/`strokeColor` to make them visible:
```
style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;"
```
**Preset Color Palette:** Blue(`#dae8fc`,`#6c8ebf`) Green(`#d5e8d4`,`#82b366`) Orange(`#ffe6cc`,`#d79b00`) Red(`#f8cecc`,`#b85450`) Purple(`#e1d5e7`,`#9673a6`) Yellow(`#fff2cc`,`#d6b656`) Gray(`#f5f5f5`,`#666666`)

**Exception:** Edge/link stencils (e.g., `mxgraph.networks.comm_link`) should NOT have `fillColor`/`strokeColor` — they are connectors, not devices.

### Rule 2: Check Stencil Names Before Use
Before using stencils, check [stencils/README.md](../drawio/stencils/README.md) to find correct shape names. Use exact names like `mxgraph.cisco.routers.router`.

### Rule 3: Root Cells Required
- `<mxCell id="0"/>` — Root cell (required)
- `<mxCell id="1" parent="0"/>` — Default parent (required)
- Missing root cells → Diagram won't render

### Rule 4: Device Stencil Labels Below
When adding labels to device stencils, place them below the stencil for better readability:
```
style="...;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;"
```

## Network Diagram Types

| Type | Purpose | Key Shapes | Example |
|------|---------|------------|---------|
| LAN | Local network topology | Switch, PC, Server | [lan-topology.md](examples/lan-topology.md) |
| WAN | Wide area network | Router, Cloud, Firewall | [wan-topology.md](examples/wan-topology.md) |
| Enterprise | Corporate infrastructure | Multiple zones, DMZ | [enterprise-network.md](examples/enterprise-network.md) |
| Cisco | Cisco-specific icons | Cisco shapes | [cisco-network.md](examples/cisco-network.md) |
| Wireless | WiFi network | AP, Controller | [wireless-network.md](examples/wireless-network.md) |
| Cloud Hybrid | On-premise + Cloud | VPN, Gateway | [hybrid-cloud.md](examples/hybrid-cloud.md) |
| Citrix | Virtual Apps/Desktops | NetScaler, VDA, XenServer | [citrix-network.md](examples/citrix-network.md) |

## Common Network Shapes

### Basic Network Shapes (`mxgraph.networks.*`)

| Shape | Style | Description |
|-------|-------|-------------|
| PC | `shape=mxgraph.networks.pc` | Desktop computer |
| Laptop | `shape=mxgraph.networks.laptop` | Laptop computer |
| Server | `shape=mxgraph.networks.server` | Server machine |
| Switch | `shape=mxgraph.networks.switch` | Network switch |
| Router | `shape=mxgraph.networks.router` | Network router |
| Firewall | `shape=mxgraph.networks.firewall` | Firewall device |
| Cloud | `shape=mxgraph.networks.cloud` | Internet/Cloud |
| Wireless Hub | `shape=mxgraph.networks.wireless_hub` | WiFi access point |
| Storage | `shape=mxgraph.networks.storage` | Storage device |
| Printer | `shape=mxgraph.networks.printer` | Network printer |
| Mobile | `shape=mxgraph.networks.mobile` | Mobile device |
| Scanner | `shape=mxgraph.networks.scanner` | Network scanner |

### Cisco Network Shapes (`mxgraph.cisco.*`)

| Category | Shape | Style |
|----------|-------|-------|
| Switches | Workgroup Switch | `shape=mxgraph.cisco.switches.workgroup_switch` |
| Switches | Layer 3 Switch | `shape=mxgraph.cisco.switches.layer_3_switch` |
| Routers | Router | `shape=mxgraph.cisco.routers.router` |
| Security | PIX Firewall | `shape=mxgraph.cisco.security.pix_firewall` |
| Security | ASA Firewall | `shape=mxgraph.cisco.misc.asa_5500` |
| Servers | File Server | `shape=mxgraph.cisco.servers.fileserver` |
| Servers | Storage Server | `shape=mxgraph.cisco.servers.storage_server` |
| Servers | Communications Server | `shape=mxgraph.cisco.servers.communications_server` |
| Computers | Workstation | `shape=mxgraph.cisco.computers_and_peripherals.workstation` |
| Computers | Laptop | `shape=mxgraph.cisco.computers_and_peripherals.laptop` |
| Storage | Cloud | `shape=mxgraph.cisco.storage.cloud` |
| Misc | Access Point | `shape=mxgraph.cisco.misc.access_point` |
| Hubs | 100BaseT Hub | `shape=mxgraph.cisco.hubs_and_gateways.100baset_hub` |

### Citrix Network Shapes (`mxgraph.citrix.*`)

| Shape | Style | Description |
|-------|-------|-------------|
| Laptop | `shape=mxgraph.citrix.laptop_2` | Citrix client laptop |
| Desktop | `shape=mxgraph.citrix.desktop` | Desktop client |
| Router | `shape=mxgraph.citrix.router` | Citrix router |
| Firewall | `shape=mxgraph.citrix.firewall` | Citrix firewall |
| XenApp Server | `shape=mxgraph.citrix.xenapp_server` | XenApp server |
| Chassis | `shape=mxgraph.citrix.chassis` | Server chassis |

## Common Style Reference

- **Device Colors:** Primary(`#10739E`, fill) Secondary(`#ffffff`, stroke) Accent(`#FFB366`, label)
- **Zone Colors:** LAN(`#BAC8D3`, 60% opacity) WAN(`#FFD470`) DMZ(`#f8cecc`) Cloud(`#d5e8d4`) Private(`#dae8fc`)
- **Connection Styles:** Wired(`strokeWidth=2;endArrow=none`) Wireless(`dashed=1;strokeWidth=2`) Encrypted(`strokeColor=#00AA00`)
- **Label Styles:** Device(`fontSize=14;fontStyle=1`) Zone(`fontSize=14;verticalAlign=top`)

## Network Topology Patterns

### Star Topology
Central device (switch/router) with all other devices connected to it.

### Bus Topology
All devices connected to a single backbone cable.

### Ring Topology
Devices connected in a circular fashion.

### Mesh Topology
Every device connected to every other device.

### Hierarchical/Tree
Three-tier architecture: Core → Distribution → Access layers.

## Draw.io XML Syntax Examples

### Example 1: Network Device with Label
```drawio
<mxfile><diagram name="Device" id="dev"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/><mxCell id="router1" value="Core Router" style="shape=mxgraph.networks.router;html=1;fillColor=#036897;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;" parent="1" vertex="1"><mxGeometry x="100" y="100" width="80" height="55" as="geometry"/></mxCell></root></mxGraphModel></diagram></mxfile>
```

### Example 2: Network Zone (Background Region)
```drawio
<mxfile><diagram name="Zone" id="zone"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/><mxCell id="zone1" value="DMZ" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#f8cecc;opacity=60;verticalAlign=top;fontSize=14;" parent="1" vertex="1"><mxGeometry x="50" y="50" width="200" height="150" as="geometry"/></mxCell></root></mxGraphModel></diagram></mxfile>
```

### Example 3: Network Connection
```drawio
<mxfile><diagram name="Connection" id="conn"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/><mxCell id="sw1" value="" style="shape=mxgraph.networks.switch;html=1;fillColor=#036897;strokeColor=#ffffff;" parent="1" vertex="1"><mxGeometry x="50" y="100" width="80" height="25" as="geometry"/></mxCell><mxCell id="pc1" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#036897;strokeColor=#ffffff;" parent="1" vertex="1"><mxGeometry x="200" y="85" width="60" height="50" as="geometry"/></mxCell><mxCell id="link1" style="edgeStyle=none;html=1;endArrow=none;strokeWidth=2;" parent="1" source="sw1" target="pc1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell></root></mxGraphModel></diagram></mxfile>
```

## Best Practices

1. **Use Zones:** Group related devices in colored zones for clarity
2. **Label Everything:** Add meaningful labels to devices and connections
3. **Layer Properly:** Place zones first (lowest z-order), then devices, then connections
4. **Consistent Icons:** Use the same icon family (Cisco OR generic, not mixed)
5. **Show Traffic Flow:** Use arrows to indicate data flow direction when relevant
6. **Include Legend:** Add a legend for complex diagrams with many device types
