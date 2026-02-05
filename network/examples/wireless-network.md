# Wireless Network Diagram

Shows a wireless network topology with access points, controllers, and client devices.

## Key Elements

- **Wireless Router**: `shape=mxgraph.networks.wireless_hub`
- **Access Point**: `shape=mxgraph.cisco.misc.access_point`
- **WLAN Controller**: `shape=mxgraph.cisco.wireless.wlan_controller`
- **Laptop/Mobile**: `shape=mxgraph.networks.laptop`, `mobile`
- **Wireless Link**: `shape=mxgraph.networks.comm_link` (wave pattern)

## Wireless Connection Styles

| Type | Style | Description |
|------|-------|-------------|
| WiFi Signal | `shape=mxgraph.networks.comm_link` | Wave pattern for wireless |
| Wired Backhaul | `endArrow=none;strokeWidth=2` | AP to switch connection |
| Mesh Link | `dashed=1;strokeColor=#00AA00` | AP-to-AP mesh |

## Example

Enterprise wireless network with multiple access points:

```drawio
<mxfile><diagram id="wireless-network" name="Wireless"><mxGraphModel dx="900" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-core" value="Core Network" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#dae8fc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="280" y="40" width="240" height="140" as="geometry"/></mxCell>
  <mxCell id="zone-floor1" value="Floor 1" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#d5e8d4;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="240" width="320" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-floor2" value="Floor 2" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#fff2cc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="440" y="240" width="320" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-outdoor" value="Outdoor" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#f8cecc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="240" y="480" width="320" height="140" as="geometry"/></mxCell>
  <mxCell id="internet" value="Internet" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#23445D;fillColor=#ffffff;fontSize=14;fontColor=#23445D;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="340" y="60" width="120" height="70" as="geometry"/></mxCell>
  <mxCell id="firewall" value="" style="shape=mxgraph.networks.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="300" y="75" width="30" height="40" as="geometry"/></mxCell>
  <mxCell id="core-switch" value="" style="shape=mxgraph.networks.switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="360" y="200" width="80" height="24" as="geometry"/></mxCell>
  <mxCell id="wlan-ctrl" value="WLAN&#xa;Controller" style="shape=mxgraph.cisco.wireless.wlan_controller;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;fontSize=10;" parent="1" vertex="1"><mxGeometry x="470" y="70" width="40" height="45" as="geometry"/></mxCell>
  <mxCell id="ap1" value="AP-1" style="shape=mxgraph.cisco.misc.access_point;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;fontSize=10;" parent="1" vertex="1"><mxGeometry x="80" y="280" width="60" height="30" as="geometry"/></mxCell>
  <mxCell id="ap2" value="AP-2" style="shape=mxgraph.cisco.misc.access_point;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;fontSize=10;" parent="1" vertex="1"><mxGeometry x="260" y="280" width="60" height="30" as="geometry"/></mxCell>
  <mxCell id="ap3" value="AP-3" style="shape=mxgraph.cisco.misc.access_point;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;fontSize=10;" parent="1" vertex="1"><mxGeometry x="480" y="280" width="60" height="30" as="geometry"/></mxCell>
  <mxCell id="ap4" value="AP-4" style="shape=mxgraph.cisco.misc.access_point;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;fontSize=10;" parent="1" vertex="1"><mxGeometry x="660" y="280" width="60" height="30" as="geometry"/></mxCell>
  <mxCell id="ap-outdoor" value="Outdoor AP" style="shape=mxgraph.cisco.misc.mesh_ap;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;fontSize=10;" parent="1" vertex="1"><mxGeometry x="370" y="510" width="60" height="40" as="geometry"/></mxCell>
  <mxCell id="laptop1" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="370" width="70" height="45" as="geometry"/></mxCell>
  <mxCell id="laptop2" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="160" y="380" width="70" height="45" as="geometry"/></mxCell>
  <mxCell id="mobile1" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="280" y="360" width="30" height="55" as="geometry"/></mxCell>
  <mxCell id="laptop3" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="470" y="370" width="70" height="45" as="geometry"/></mxCell>
  <mxCell id="mobile2" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="560" y="370" width="30" height="55" as="geometry"/></mxCell>
  <mxCell id="laptop4" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="640" y="380" width="70" height="45" as="geometry"/></mxCell>
  <mxCell id="mobile-outdoor" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="290" y="540" width="30" height="55" as="geometry"/></mxCell>
  <mxCell id="laptop-outdoor" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="470" y="550" width="70" height="45" as="geometry"/></mxCell>
  <mxCell id="link-fw-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="firewall" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="firewall" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ctrl-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="wlan-ctrl" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ap1-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="ap1" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ap2-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="ap2" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ap3-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="ap3" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ap4-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="ap4" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ap-out-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="ap-outdoor" target="core-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-l1" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="laptop1" target="ap1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-l2" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="laptop2" target="ap1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-m1" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="mobile1" target="ap2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-l3" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="laptop3" target="ap3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-m2" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="mobile2" target="ap3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-l4" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="laptop4" target="ap4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-out-m" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="mobile-outdoor" target="ap-outdoor" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="wifi-out-l" value="" style="shape=mxgraph.networks.comm_link;html=1;strokeWidth=2;endArrow=none;" parent="1" source="laptop-outdoor" target="ap-outdoor" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

