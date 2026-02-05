---
name: network
description: Create network topology diagrams using drawio XML format with industry-standard device icons. Best for LAN/WAN diagrams, enterprise networks, cloud infrastructure, and vendor-specific diagrams (Cisco, Arista, Fortinet). Built on drawio with specialized network stencils. NOT for abstract dependency graphs (use graphviz) or simple flowcharts (use mermaid).
author: Network diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Network Topology Diagram Generator

**Quick Start:** Choose topology type → Add network devices (routers, switches, firewalls) → Connect with appropriate link types → Add labels and zones → Wrap in ` ```drawio ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```drawio ` code fence. NEVER use ` ```xml ` — it will NOT render as a diagram.

## Critical Rules

> 🔗 **This is a drawio-derived skill.** All structure, layout, and edge routing rules inherit from [drawio SKILL.md](../drawio/SKILL.md). Read the base rules first.

**Network-specific additions:**
- Check [stencils/README.md](../drawio/stencils/README.md) for exact device stencil names (e.g., `mxgraph.cisco.routers.router`)
- Device stencils require `fillColor`/`strokeColor`; edge/link stencils (e.g., `mxgraph.networks.comm_link`) do NOT
- Use `fillColor=none;` for network zones/segments to avoid covering child devices

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
