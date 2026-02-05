# LAN Topology Diagram

Shows a typical local area network with workstations, server, firewall, and Internet connection.

## Key Elements

- **Zone labels**: `rounded=1;strokeColor=none;fillColor=#BAC8D3;opacity=60` with zone name
- **Workstations**: `shape=mxgraph.networks.pc`
- **Switch**: `shape=mxgraph.networks.switch`
- **Wireless Hub**: `shape=mxgraph.networks.wireless_hub`
- **Server**: `shape=mxgraph.networks.server`
- **Firewall**: `shape=mxgraph.networks.firewall`
- **Cloud/Internet**: `shape=mxgraph.networks.cloud`
- **Devices**: `shape=mxgraph.networks.laptop`, `mobile`, `printer`, `scanner`, `storage`

## Connection Types

| Type | Style | Description |
|------|-------|-------------|
| Wired | `endArrow=none;strokeWidth=2` | Standard Ethernet |
| Wireless | `shape=mxgraph.networks.comm_link` | WiFi connection |
| Backbone | `strokeWidth=3;strokeColor=#23445D` | Main network backbone |

## Example

Small office LAN with wired and wireless clients:

```drawio
<mxfile><diagram id="lan-topology" name="LAN"><mxGraphModel dx="900" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-lan" value="Office LAN" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;align=center;" parent="1" vertex="1"><mxGeometry x="40" y="180" width="520" height="360" as="geometry"/></mxCell>
  <mxCell id="zone-dmz" value="DMZ" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#f8cecc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;align=center;" parent="1" vertex="1"><mxGeometry x="600" y="180" width="160" height="180" as="geometry"/></mxCell>
  <mxCell id="pc1" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="220" width="80" height="60" as="geometry"/></mxCell>
  <mxCell id="pc2" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="180" y="220" width="80" height="60" as="geometry"/></mxCell>
  <mxCell id="pc3" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="300" y="220" width="80" height="60" as="geometry"/></mxCell>
  <mxCell id="switch1" value="" style="shape=mxgraph.networks.switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="180" y="340" width="80" height="24" as="geometry"/></mxCell>
  <mxCell id="wap" value="" style="shape=mxgraph.networks.wireless_hub;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="180" y="400" width="80" height="70" as="geometry"/></mxCell>
  <mxCell id="laptop1" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="480" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="mobile1" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="300" y="460" width="40" height="80" as="geometry"/></mxCell>
  <mxCell id="printer1" value="" style="shape=mxgraph.networks.printer;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="420" y="220" width="80" height="80" as="geometry"/></mxCell>
  <mxCell id="server1" value="" style="shape=mxgraph.networks.server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="420" y="340" width="70" height="80" as="geometry"/></mxCell>
  <mxCell id="storage1" value="" style="shape=mxgraph.networks.storage;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="420" y="460" width="80" height="70" as="geometry"/></mxCell>
  <mxCell id="firewall1" value="" style="shape=mxgraph.networks.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="620" y="250" width="80" height="80" as="geometry"/></mxCell>
  <mxCell id="internet" value="Internet" style="shape=mxgraph.networks.cloud;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;fontSize=18;fontColor=#ffffff;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="580" y="40" width="180" height="100" as="geometry"/></mxCell>
  <mxCell id="link-pc1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;rounded=1;" parent="1" source="pc1" target="switch1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-pc2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;rounded=1;" parent="1" source="pc2" target="switch1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-pc3" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;rounded=1;" parent="1" source="pc3" target="switch1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-switch-wap" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;" parent="1" source="switch1" target="wap" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-switch-server" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;" parent="1" source="switch1" target="server1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-switch-printer" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;" parent="1" source="switch1" target="printer1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-server-storage" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;" parent="1" source="server1" target="storage1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-server-fw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;" parent="1" source="server1" target="firewall1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-internet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#000000;" parent="1" source="firewall1" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-laptop" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="laptop1" target="wap" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-mobile" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="mobile1" target="wap" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

