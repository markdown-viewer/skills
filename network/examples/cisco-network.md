# Cisco Network Diagram

Shows a multi-branch WAN topology using Cisco network icons with firewalls and routers.

## Key Elements

- **Internet Cloud**: `ellipse;shape=cloud`
- **Cisco Router**: `shape=mxgraph.cisco.routers.router` (78×53)
- **Cisco Firewall**: `shape=mxgraph.cisco.security.firewall` (53×50)
- **Cisco Layer 3 Switch**: `shape=mxgraph.cisco.switches.layer_3_switch` (55×58)
- **Cisco Workgroup Switch**: `shape=mxgraph.cisco.switches.workgroup_switch` (55×38)
- **Cisco Workstation**: `shape=mxgraph.cisco.computers_and_peripherals.workstation` (53×39)
- **Cisco Laptop**: `shape=mxgraph.cisco.computers_and_peripherals.laptop` (57×38)
- **Cisco Printer**: `shape=mxgraph.cisco.computers_and_peripherals.printer` (57×22)
- **Cisco File Server**: `shape=mxgraph.cisco.servers.fileserver` (42×52)

## Cisco Style

| Property | Value | Description |
|----------|-------|-------------|
| fillColor | `#036897` | Cisco blue |
| strokeColor | `#ffffff` | White outline |
| strokeWidth | `2` | Border width |
| verticalLabelPosition | `bottom` | Label below icon |
| verticalAlign | `top` | Align label to top of label area |

**Zone backgrounds:** Use `rounded=1;strokeColor=none;fillColor=#BAC8D3;opacity=60` for site/zone grouping.

**Edge style:** Network links use `endArrow=none;endFill=0;strokeWidth=2` (no arrows, bidirectional). Use `strokeWidth=4;strokeColor=#23445D` for backbone links.

## Example

Multi-branch WAN with Internet core, HQ data center, and two branch offices connected via firewalls and routers:

```drawio
<mxfile><diagram id="cisco-network" name="Cisco WAN"><mxGraphModel dx="1100" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="800" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-hq" value="HQ Data Center" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;align=center;" vertex="1" parent="1"><mxGeometry x="40" y="280" width="400" height="340" as="geometry"/></mxCell>
  <mxCell id="zone-branch1" value="Branch Office 1" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;align=center;" vertex="1" parent="1"><mxGeometry x="560" y="280" width="260" height="340" as="geometry"/></mxCell>
  <mxCell id="zone-branch2" value="Branch Office 2" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;align=center;" vertex="1" parent="1"><mxGeometry x="880" y="280" width="260" height="340" as="geometry"/></mxCell>
  <mxCell id="internet" value="Internet" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#036897;strokeWidth=2;fontSize=18;fontColor=#036897;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="440" y="40" width="200" height="120" as="geometry"/></mxCell>
  <mxCell id="fw-hq" value="Firewall" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="210" y="300" width="53" height="50" as="geometry"/></mxCell>
  <mxCell id="router-hq" value="Core Router" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="200" y="200" width="78" height="53" as="geometry"/></mxCell>
  <mxCell id="l3switch" value="L3 Switch" style="shape=mxgraph.cisco.switches.layer_3_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="205" y="420" width="55" height="58" as="geometry"/></mxCell>
  <mxCell id="server1" value="File Server" style="shape=mxgraph.cisco.servers.fileserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="60" y="420" width="42" height="52" as="geometry"/></mxCell>
  <mxCell id="server2" value="App Server" style="shape=mxgraph.cisco.servers.fileserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="340" y="420" width="42" height="52" as="geometry"/></mxCell>
  <mxCell id="ws-hq1" value="User" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="60" y="540" width="53" height="39" as="geometry"/></mxCell>
  <mxCell id="ws-hq2" value="User" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="210" y="540" width="53" height="39" as="geometry"/></mxCell>
  <mxCell id="printer-hq" value="Printer" style="shape=mxgraph.cisco.computers_and_peripherals.printer;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="340" y="548" width="57" height="22" as="geometry"/></mxCell>
  <mxCell id="fw-b1" value="Firewall" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="660" y="300" width="53" height="50" as="geometry"/></mxCell>
  <mxCell id="router-b1" value="Router" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="650" y="200" width="78" height="53" as="geometry"/></mxCell>
  <mxCell id="switch-b1" value="Switch" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="660" y="420" width="55" height="38" as="geometry"/></mxCell>
  <mxCell id="laptop-b1" value="User" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="580" y="530" width="57" height="38" as="geometry"/></mxCell>
  <mxCell id="ws-b1" value="User" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="720" y="530" width="53" height="39" as="geometry"/></mxCell>
  <mxCell id="fw-b2" value="Firewall" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="980" y="300" width="53" height="50" as="geometry"/></mxCell>
  <mxCell id="router-b2" value="Router" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="970" y="200" width="78" height="53" as="geometry"/></mxCell>
  <mxCell id="switch-b2" value="Switch" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="980" y="420" width="55" height="38" as="geometry"/></mxCell>
  <mxCell id="laptop-b2" value="User" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="900" y="530" width="57" height="38" as="geometry"/></mxCell>
  <mxCell id="printer-b2" value="Printer" style="shape=mxgraph.cisco.computers_and_peripherals.printer;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;" vertex="1" parent="1"><mxGeometry x="1040" y="538" width="57" height="22" as="geometry"/></mxCell>
  <mxCell id="link-inet-hq" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=4;strokeColor=#23445D;rounded=1;exitX=0.25;exitY=1;entryX=0.5;entryY=0;" edge="1" parent="1" source="internet" target="router-hq"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-inet-b1" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=4;strokeColor=#23445D;rounded=1;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" edge="1" parent="1" source="internet" target="router-b1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-inet-b2" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=4;strokeColor=#23445D;rounded=1;exitX=0.75;exitY=1;entryX=0.5;entryY=0;" edge="1" parent="1" source="internet" target="router-b2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-hq-rtr-fw" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="router-hq" target="fw-hq"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-hq-fw-sw" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="fw-hq" target="l3switch"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-srv1" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="l3switch" target="server1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-srv2" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="l3switch" target="server2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-ws1" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="l3switch" target="ws-hq1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-ws2" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="l3switch" target="ws-hq2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-printer" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="l3switch" target="printer-hq"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b1-rtr-fw" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="router-b1" target="fw-b1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b1-fw-sw" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="fw-b1" target="switch-b1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b1-sw-lap" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="switch-b1" target="laptop-b1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b1-sw-ws" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="switch-b1" target="ws-b1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b2-rtr-fw" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="router-b2" target="fw-b2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b2-fw-sw" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="fw-b2" target="switch-b2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b2-sw-lap" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="switch-b2" target="laptop-b2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-b2-sw-prt" style="edgeStyle=orthogonalEdgeStyle;html=1;endArrow=none;endFill=0;strokeWidth=2;strokeColor=#23445D;" edge="1" parent="1" source="switch-b2" target="printer-b2"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. **Cisco blue**: All device stencils use `fillColor=#036897;strokeColor=#ffffff;strokeWidth=2`
2. **No arrows**: Network links use `endArrow=none;endFill=0` — connections are bidirectional
3. **Backbone links**: WAN/Internet backbone uses thicker `strokeWidth=4;strokeColor=#23445D`
4. **Zone grouping**: Semi-transparent boxes (`opacity=60;fillColor=#BAC8D3`) define site boundaries
5. **Labels below**: Device labels use `verticalLabelPosition=bottom;verticalAlign=top`
6. **Cloud shape**: Internet cloud uses standard `ellipse;shape=cloud` with Cisco blue stroke, not `mxgraph.cisco.storage.cloud`
7. **Layered layout**: Top-down: Internet → Router → Firewall → Switch → End devices

