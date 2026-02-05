# Cisco Network Diagram

Shows a multi-branch WAN topology using Cisco network icons with firewalls and routers.

## Key Elements

- **Internet Cloud**: `ellipse;shape=cloud`
- **Cisco Router**: `shape=mxgraph.cisco.routers.router`
- **Cisco Firewall**: `shape=mxgraph.cisco.security.firewall`
- **Cisco Workstation**: `shape=mxgraph.cisco.computers_and_peripherals.workstation`
- **Cisco Laptop**: `shape=mxgraph.cisco.computers_and_peripherals.laptop`
- **Cisco Printer**: `shape=mxgraph.cisco.computers_and_peripherals.printer`

## Cisco Style

| Property | Value | Description |
|----------|-------|-------------|
| fillColor | `#036897` | Cisco blue |
| strokeColor | `#ffffff` | White outline |
| strokeWidth | `2` | Border width |

## Example

Multi-branch WAN with four sites connected via firewalls:

```drawio
<mxfile><diagram id="cisco-wan" name="Cisco WAN"><mxGraphModel dx="900" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-hq" value="Headquarters" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="60" width="280" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-br1" value="Branch 1" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="580" y="60" width="200" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-br2" value="Branch 2" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="380" width="200" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-br3" value="Branch 3" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="580" y="380" width="200" height="200" as="geometry"/></mxCell>
  <mxCell id="internet" value="Internet" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#23445D;fillColor=#ffffff;fontSize=16;fontColor=#23445D;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="340" y="250" width="140" height="100" as="geometry"/></mxCell>
  <mxCell id="fw-hq" value="PIX" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;" parent="1" vertex="1"><mxGeometry x="260" y="155" width="29" height="50" as="geometry"/></mxCell>
  <mxCell id="fw-br1" value="PIX" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;" parent="1" vertex="1"><mxGeometry x="530" y="155" width="29" height="50" as="geometry"/></mxCell>
  <mxCell id="fw-br2" value="PIX" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;" parent="1" vertex="1"><mxGeometry x="260" y="400" width="29" height="50" as="geometry"/></mxCell>
  <mxCell id="fw-br3" value="PIX" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;" parent="1" vertex="1"><mxGeometry x="530" y="400" width="29" height="50" as="geometry"/></mxCell>
  <mxCell id="router-hq" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="140" y="150" width="70" height="48" as="geometry"/></mxCell>
  <mxCell id="router-br1" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="620" y="150" width="70" height="48" as="geometry"/></mxCell>
  <mxCell id="router-br2" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="90" y="450" width="70" height="48" as="geometry"/></mxCell>
  <mxCell id="router-br3" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="660" y="450" width="70" height="48" as="geometry"/></mxCell>
  <mxCell id="ws-hq1" value="" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="55" y="90" width="65" height="50" as="geometry"/></mxCell>
  <mxCell id="ws-hq2" value="" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="55" y="160" width="65" height="45" as="geometry"/></mxCell>
  <mxCell id="ws-br1" value="" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="700" y="90" width="65" height="50" as="geometry"/></mxCell>
  <mxCell id="laptop-br1" value="" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="700" y="160" width="65" height="45" as="geometry"/></mxCell>
  <mxCell id="ws-br2" value="" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="55" y="515" width="65" height="50" as="geometry"/></mxCell>
  <mxCell id="ws-br3" value="" style="shape=mxgraph.cisco.computers_and_peripherals.workstation;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="700" y="515" width="65" height="50" as="geometry"/></mxCell>
  <mxCell id="printer-hq" value="" style="shape=mxgraph.cisco.computers_and_peripherals.printer;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="150" y="220" width="70" height="26" as="geometry"/></mxCell>
  <mxCell id="link-ws-hq1" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="ws-hq1" target="router-hq" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ws-hq2" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="ws-hq2" target="router-hq" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-printer-hq" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="printer-hq" target="router-hq" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-router-fw-hq" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="router-hq" target="fw-hq" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-inet-hq" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="fw-hq" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ws-br1" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="ws-br1" target="router-br1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-laptop-br1" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="laptop-br1" target="router-br1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-router-fw-br1" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="router-br1" target="fw-br1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-inet-br1" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="fw-br1" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ws-br2" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="ws-br2" target="router-br2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-router-fw-br2" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="router-br2" target="fw-br2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-inet-br2" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="fw-br2" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ws-br3" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="ws-br3" target="router-br3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-router-fw-br3" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="router-br3" target="fw-br3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-inet-br3" style="endArrow=none;html=1;strokeWidth=1;" parent="1" source="fw-br3" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

