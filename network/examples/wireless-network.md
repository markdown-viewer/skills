# Wireless Network Diagram

Shows a wireless network topology with access points, controllers, and client devices.

## Key Elements

| Component | Stencil | fillColor | strokeColor |
|-----------|---------|-----------|-------------|
| Wireless Hub | `mxgraph.networks.wireless_hub` | `#CCCCCC` | `#6881B3` |
| Laptop | `mxgraph.networks.laptop` | `#CCCCCC` | `#6881B3` |
| Mobile | `mxgraph.networks.mobile` | `#CCCCCC` | `#6881B3` |
| Tablet | `mxgraph.networks.tablet` | `#CCCCCC` | `#6881B3` |
| PC | `mxgraph.networks.pc` | `#CCCCCC` | `#6881B3` |
| Switch | `mxgraph.networks.switch` | `#CCCCCC` | `#6881B3` |
| Router | `mxgraph.networks.router` | `#CCCCCC` | `#6881B3` |
| Firewall | `mxgraph.networks.firewall` | `#CCCCCC` | `#6881B3` |
| Server | `mxgraph.networks.server` | `#CCCCCC` | `#6881B3` |
| Cloud | `mxgraph.networks.cloud` | `#CCCCCC` | `#6881B3` |
| Printer | `mxgraph.networks.printer` | `#CCCCCC` | `#6881B3` |

- All devices share unified style: `fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2`
- Zone containers: `rounded=1;fillColor=none;strokeColor=#036897;strokeWidth=2;verticalAlign=top;arcSize=11` with zone name as label
- Zone label font: `fontColor=#6881B3;fontSize=16;fontFamily=Verdana`

**Cisco alternative stencils** (for enterprise wireless diagrams using Cisco icons):

| Component | Stencil | fillColor | strokeColor |
|-----------|---------|-----------|-------------|
| Access Point | `mxgraph.cisco.misc.access_point` | `#036897` | `#ffffff` |
| WLAN Controller | `mxgraph.cisco.wireless.wlan_controller` | `#036897` | `#ffffff` |
| Wireless Bridge | `mxgraph.cisco.wireless.wireless_bridge` | `#036897` | `#ffffff` |
| Radio Tower | `mxgraph.cisco.wireless.radio_tower` | `#036897` | `#ffffff` |

## Wireless Connection Styles

| Type | Style | Description |
|------|-------|-------------|
| WiFi Signal | `shape=mxgraph.networks.comm_link_edge;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none` | Wave/zigzag pattern for wireless links |
| Wired Backhaul | `edgeStyle=none;endArrow=none;endFill=0;strokeWidth=2` | AP-to-switch Ethernet uplink |
| Trunk/Uplink | `edgeStyle=none;endArrow=none;endFill=0;strokeWidth=3` | Switch-to-router backbone |

## Example

Enterprise wireless network with WLAN controller, multiple access points, and mixed client devices:

```drawio
<mxfile>
  <diagram id="wifi-1" name="Wireless Network">
    <mxGraphModel dx="1100" dy="760" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="760" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- Zone: Floor 1 -->
        <mxCell id="z1" value="Floor 1 — WiFi Zone" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#036897;strokeWidth=2;verticalAlign=top;fontColor=#6881B3;fontSize=16;fontFamily=Verdana;arcSize=11" parent="1" vertex="1"><mxGeometry x="40" y="390" width="480" height="330" as="geometry"/></mxCell>
        <!-- Zone: Floor 2 -->
        <mxCell id="z2" value="Floor 2 — WiFi Zone" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#036897;strokeWidth=2;verticalAlign=top;fontColor=#6881B3;fontSize=16;fontFamily=Verdana;arcSize=11" parent="1" vertex="1"><mxGeometry x="580" y="390" width="480" height="330" as="geometry"/></mxCell>
        <!-- Internet Cloud -->
        <mxCell id="inet" value="Internet" style="shape=mxgraph.networks.cloud;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;fontColor=#0066CC;fontSize=14" parent="1" vertex="1"><mxGeometry x="450" y="20" width="140" height="80" as="geometry"/></mxCell>
        <!-- Firewall -->
        <mxCell id="fw" value="" style="shape=mxgraph.networks.firewall;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="480" y="130" width="80" height="70" as="geometry"/></mxCell>
        <!-- Core Router -->
        <mxCell id="rtr" value="" style="shape=mxgraph.networks.router;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="470" y="230" width="100" height="29" as="geometry"/></mxCell>
        <!-- Core Switch -->
        <mxCell id="sw-core" value="" style="shape=mxgraph.networks.switch;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="470" y="300" width="100" height="30" as="geometry"/></mxCell>
        <!-- Server (WLAN Controller / DHCP / RADIUS) -->
        <mxCell id="srv" value="" style="shape=mxgraph.networks.server;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="870" y="220" width="44" height="60" as="geometry"/></mxCell>
        <mxCell id="srv-lbl" value="WLAN Controller&#xa;/ RADIUS" style="text;html=1;strokeColor=none;fillColor=none;fontSize=11;fontColor=#6881B3;align=center" parent="1" vertex="1"><mxGeometry x="840" y="280" width="110" height="30" as="geometry"/></mxCell>
        <!-- Floor 1: AP1 -->
        <mxCell id="ap1" value="" style="shape=mxgraph.networks.wireless_hub;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="200" y="430" width="80" height="50" as="geometry"/></mxCell>
        <mxCell id="ap1-lbl" value="AP-1" style="text;html=1;strokeColor=none;fillColor=none;fontSize=11;fontColor=#6881B3;fontStyle=1;align=center" parent="1" vertex="1"><mxGeometry x="210" y="415" width="60" height="18" as="geometry"/></mxCell>
        <!-- Floor 1: Client devices -->
        <mxCell id="lap1" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="70" y="540" width="70" height="45" as="geometry"/></mxCell>
        <mxCell id="lap2" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="170" y="540" width="70" height="45" as="geometry"/></mxCell>
        <mxCell id="mob1" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="270" y="540" width="30" height="55" as="geometry"/></mxCell>
        <mxCell id="tab1" value="" style="shape=mxgraph.networks.tablet;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="340" y="545" width="60" height="42" as="geometry"/></mxCell>
        <!-- Floor 1: Printer (wireless) -->
        <mxCell id="prn1" value="" style="shape=mxgraph.networks.printer;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="430" y="530" width="50" height="55" as="geometry"/></mxCell>
        <!-- Floor 2: AP2 -->
        <mxCell id="ap2" value="" style="shape=mxgraph.networks.wireless_hub;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="760" y="430" width="80" height="50" as="geometry"/></mxCell>
        <mxCell id="ap2-lbl" value="AP-2" style="text;html=1;strokeColor=none;fillColor=none;fontSize=11;fontColor=#6881B3;fontStyle=1;align=center" parent="1" vertex="1"><mxGeometry x="770" y="415" width="60" height="18" as="geometry"/></mxCell>
        <!-- Floor 2: Client devices -->
        <mxCell id="lap3" value="" style="shape=mxgraph.networks.laptop;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="630" y="540" width="70" height="45" as="geometry"/></mxCell>
        <mxCell id="mob2" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="730" y="540" width="30" height="55" as="geometry"/></mxCell>
        <mxCell id="mob3" value="" style="shape=mxgraph.networks.mobile;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="800" y="540" width="30" height="55" as="geometry"/></mxCell>
        <mxCell id="pc1" value="" style="shape=mxgraph.networks.pc;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="870" y="530" width="60" height="70" as="geometry"/></mxCell>
        <mxCell id="tab2" value="" style="shape=mxgraph.networks.tablet;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="960" y="545" width="60" height="42" as="geometry"/></mxCell>
        <!-- Edges: Internet → Firewall → Router → Core Switch -->
        <mxCell id="e1" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="inet" target="fw" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="fw" target="rtr" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=3" parent="1" source="rtr" target="sw-core" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Core Switch → Server (wired) -->
        <mxCell id="e4" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="sw-core" target="srv" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Core Switch → AP1 (wired backhaul) -->
        <mxCell id="e5" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="sw-core" target="ap1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Core Switch → AP2 (wired backhaul) -->
        <mxCell id="e6" style="edgeStyle=none;endArrow=none;html=1;endFill=0;strokeWidth=2" parent="1" source="sw-core" target="ap2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- AP1 → wireless clients (comm_link_edge for WiFi) -->
        <mxCell id="w1" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap1" target="lap1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w2" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap1" target="lap2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w3" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap1" target="mob1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w4" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap1" target="tab1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w5" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap1" target="prn1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- AP2 → wireless clients (comm_link_edge for WiFi) -->
        <mxCell id="w6" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap2" target="lap3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w7" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap2" target="mob2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w8" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap2" target="mob3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w9" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap2" target="pc1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="w10" style="shape=mxgraph.networks.comm_link_edge;html=1;fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2;endArrow=none" parent="1" source="ap2" target="tab2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **`mxgraph.networks.*` stencil family** — wireless diagrams use the same networks library as LAN diagrams. Unified device style: `fillColor=#CCCCCC;strokeColor=#6881B3;strokeWidth=2`
2. **Wireless connections** use the special edge shape `shape=mxgraph.networks.comm_link_edge` with `fillColor=#CCCCCC;strokeColor=#6881B3`, rendering a zigzag/wave pattern between `wireless_hub` and client devices (laptops, mobiles, tablets, printers)
3. **Wired backhaul** from APs to the core switch uses plain edges: `edgeStyle=none;endArrow=none;endFill=0;strokeWidth=2` — solid line vs zigzag clearly distinguishes wired from wireless segments
4. **Floor/zone containers** separate each AP's coverage area — `rounded=1;fillColor=none;strokeColor=#036897;strokeWidth=2;arcSize=11` with descriptive zone names. Each AP sits at the top of its zone with clients below
5. **WLAN Controller / RADIUS server** connects to the core switch via wired link, managing all APs centrally. Label uses a separate `text` cell below the server icon
6. **AP labels** use small `text` cells (`fontSize=11;fontStyle=1`) positioned above each `wireless_hub` — providing AP identifiers without cluttering the device icon
7. **Star topology per AP** — each `wireless_hub` connects to multiple clients via `comm_link_edge` zigzag links in a star pattern. All wireless links are bidirectional (`endArrow=none`)
8. **Backbone hierarchy**: Internet → Firewall → Router → Core Switch → APs, with `strokeWidth=3` for the trunk uplink (router↔switch) and `strokeWidth=2` for all other links

