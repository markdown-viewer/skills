# LAN Topology Diagram

Shows a typical local area network with workstations, server, firewall, and Internet connection.

## Key Elements

| Component | Stencil | fillColor | strokeColor |
|-----------|---------|-----------|-------------|
| PC | `mxgraph.networks.pc` | `#CCCCCC` | `#6881B3` |
| Laptop | `mxgraph.networks.laptop` | `#CCCCCC` | `#6881B3` |
| Switch | `mxgraph.networks.switch` | `#CCCCCC` | `#6881B3` |
| Wireless Hub | `mxgraph.networks.wireless_hub` | `#CCCCCC` | `#6881B3` |
| Server | `mxgraph.networks.server` | `#CCCCCC` | `#6881B3` |
| Printer | `mxgraph.networks.printer` | `#CCCCCC` | `#6881B3` |
| Storage | `mxgraph.networks.storage` | `#CCCCCC` | `#6881B3` |
| Firewall | `mxgraph.networks.firewall` | `#CCCCCC` | `#6881B3` |
| Cloud | `mxgraph.networks.cloud` | `#CCCCCC` | `#6881B3` |
| Mobile | `mxgraph.networks.mobile` | `#CCCCCC` | `#6881B3` |

- All devices share unified style: `fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2`
- Zone containers: `rounded=1;fillColor=none;strokeColor=#036897;strokeWidth=2;verticalAlign=top` with zone name as label
- Zone label font: `fontColor=#6881B3;fontSize=28;fontFamily=Verdana`

## Connection Types

| Type | Style | Description |
|------|-------|-------------|
| Wired LAN | `edgeStyle=none;endArrow=none;endFill=0;strokeWidth=2` | Standard Ethernet |
| Wireless | `shape=mxgraph.networks.comm_link_edge;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none` | WiFi link |
| Backbone | `edgeStyle=orthogonalEdgeStyle;endArrow=none;endFill=0;strokeWidth=2` | Hub-to-router uplink |

## Example

Small office LAN with wired and wireless segments:

```drawio
<mxfile>
  <diagram id="lan-1" name="LAN Topology">
    <mxGraphModel dx="1050" dy="720" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1050" pageHeight="720" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- Zone: Wired Segment -->
        <mxCell id="z1" value="Wired Segment" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#036897;strokeWidth=2;verticalAlign=top;fontColor=#6881B3;fontSize=16;fontFamily=Verdana;arcSize=11" parent="1" vertex="1"><mxGeometry x="40" y="300" width="440" height="260" as="geometry"/></mxCell>
        <!-- Zone: Wireless Segment -->
        <mxCell id="z2" value="Wireless Segment" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#036897;strokeWidth=2;verticalAlign=top;fontColor=#6881B3;fontSize=16;fontFamily=Verdana;arcSize=11" parent="1" vertex="1"><mxGeometry x="530" y="300" width="440" height="260" as="geometry"/></mxCell>
        <!-- Internet Cloud -->
        <mxCell id="n1" value="Internet" style="shape=mxgraph.networks.cloud;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;fontColor=#0066CC;fontSize=14" parent="1" vertex="1"><mxGeometry x="415" y="20" width="140" height="80" as="geometry"/></mxCell>
        <!-- Firewall -->
        <mxCell id="n2" value="" style="shape=mxgraph.networks.firewall;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="440" y="140" width="80" height="70" as="geometry"/></mxCell>
        <!-- Core Switch -->
        <mxCell id="n3" value="" style="shape=mxgraph.networks.switch;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="430" y="245" width="100" height="30" as="geometry"/></mxCell>
        <!-- Wired: Switch -->
        <mxCell id="n4" value="" style="shape=mxgraph.networks.switch;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="195" y="340" width="100" height="30" as="geometry"/></mxCell>
        <!-- Wired: PCs -->
        <mxCell id="n5" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="70" y="430" width="60" height="70" as="geometry"/></mxCell>
        <mxCell id="n6" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="160" y="430" width="60" height="70" as="geometry"/></mxCell>
        <mxCell id="n7" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="250" y="430" width="60" height="70" as="geometry"/></mxCell>
        <!-- Wired: Server + Printer -->
        <mxCell id="n8" value="" style="shape=mxgraph.networks.server;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="350" y="430" width="44" height="60" as="geometry"/></mxCell>
        <mxCell id="n9" value="" style="shape=mxgraph.networks.printer;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="410" y="430" width="50" height="55" as="geometry"/></mxCell>
        <!-- Wireless: Hub -->
        <mxCell id="n10" value="" style="shape=mxgraph.networks.wireless_hub;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="695" y="330" width="80" height="50" as="geometry"/></mxCell>
        <!-- Wireless: Devices -->
        <mxCell id="n11" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="560" y="445" width="70" height="45" as="geometry"/></mxCell>
        <mxCell id="n12" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="660" y="445" width="70" height="45" as="geometry"/></mxCell>
        <mxCell id="n13" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="770" y="445" width="30" height="55" as="geometry"/></mxCell>
        <mxCell id="n14" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="840" y="445" width="30" height="55" as="geometry"/></mxCell>
        <!-- Edges: Internet → Firewall → Core Switch -->
        <mxCell id="e1" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n1" target="n2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n2" target="n3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Core Switch → Wired Switch + Wireless Hub -->
        <mxCell id="e3" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n3" target="n4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n3" target="n10" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Wired Switch → endpoints -->
        <mxCell id="e5" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n4" target="n5" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n4" target="n6" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n4" target="n7" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n4" target="n8" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="n4" target="n9" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Wireless Hub → endpoints (comm_link_edge for WiFi) -->
        <mxCell id="e10" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="n10" target="n11" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e11" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="n10" target="n12" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e12" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="n10" target="n13" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e13" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="n10" target="n14" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **`mxgraph.networks.*` stencil family** — all LAN diagrams use this library, not `mxgraph.cisco.*`. Unified device style: `fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2`
2. **Zone containers** use `rounded=1;fillColor=none;strokeColor=#036897;strokeWidth=2;arcSize=11` with zone name as the cell's `value`. Label text uses `fontColor=#6881B3;fontFamily=Verdana;verticalAlign=top`
3. **Wired connections** use plain edges with `edgeStyle=none;endArrow=none;endFill=0;strokeWidth=2` — all bidirectional, no arrows
4. **Wireless connections** use the special edge shape `mxgraph.networks.comm_link_edge` with `fillColor=#CCCCCC;strokeColor=#6881B3`, rendering a zigzag/wave pattern between wireless_hub and mobile/laptop devices
5. **Two-segment topology**: Core switch splits into wired segment (switch → PCs/server/printer) and wireless segment (wireless_hub → laptops/mobiles), each inside its own zone container
6. **Firewall placement**: Single `mxgraph.networks.firewall` between Internet cloud and core switch — the standard small office pattern
7. **Cloud shape**: `mxgraph.networks.cloud` with `fontColor=#0066CC` for the "Internet" label, matching the networks stencil palette rather than Cisco coloring
8. **No bus bar backbone** in this stencil family — devices connect directly through switches/hubs using star topology, unlike Cisco-style diagrams that use `shape=line` horizontal bus bars

