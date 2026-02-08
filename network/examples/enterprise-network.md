# Enterprise Network Diagram

Shows a multi-tier enterprise network with DMZ, internal zones, and security layers.

## Key Elements

| Component | Stencil | fillColor |
|-----------|---------|-----------|
| Edge Router | `mxgraph.cisco.routers.router` | `#036897` |
| PIX Firewall | `mxgraph.cisco.security.pix_firewall` | `#036897` |
| ASA 5500 | `mxgraph.cisco.misc.asa_5500` | `#036897` |
| L3 Switch | `mxgraph.cisco.switches.layer_3_switch` | `#036897` |
| Workgroup Switch | `mxgraph.cisco.switches.workgroup_switch` | `#036897` |
| Standard Host | `mxgraph.cisco.servers.standard_host` | `#036897` |
| Storage Server | `mxgraph.cisco.servers.storage_server` | `#036897` |
| Access Point | `mxgraph.cisco.misc.access_point` | `#036897` |
| Hub | `mxgraph.cisco.hubs_and_gateways.100baset_hub` | `#036897` |
| Internet/Branch Cloud | `mxgraph.cisco.storage.cloud` | `#ffffff` |

- All Cisco device icons: `strokeColor=#ffffff;strokeWidth=2`
- Zone backgrounds: `rounded=1;fillColor=#BAC8D3;strokeColor=none;opacity=60`
- Zone labels: separate `text` cell with `fillColor=none;strokeColor=none;fontStyle=1;fontColor=#23445D`
- Bus bar backbone: `shape=line;strokeColor=#23445D` — horizontal line connecting tiers
- All edges: `endArrow=none;endFill=0` — no arrows, bidirectional physical links

## Network Tiers

| Tier | Role | Key Devices |
|------|------|-------------|
| Core | High-speed backbone | L3 switches, bus bar |
| Distribution | Policy, security | PIX firewall, ASA, WAN routers |
| Access | End-user connectivity | Workgroup switches, APs, hubs |

## Example

Enterprise three-tier network with DMZ, server farm, and campus access:

```drawio
<mxfile>
  <diagram id="ent-1" name="Enterprise Network">
    <mxGraphModel dx="1050" dy="860" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1050" pageHeight="860" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="z1" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="40" y="330" width="230" height="200" as="geometry"/></mxCell>
        <mxCell id="z1l" value="DMZ" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="50" y="335" width="50" height="20" as="geometry"/></mxCell>
        <mxCell id="z2" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="320" y="330" width="280" height="200" as="geometry"/></mxCell>
        <mxCell id="z2l" value="Server Farm" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="330" y="335" width="100" height="20" as="geometry"/></mxCell>
        <mxCell id="z3" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="650" y="330" width="230" height="200" as="geometry"/></mxCell>
        <mxCell id="z3l" value="WAN" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="660" y="335" width="50" height="20" as="geometry"/></mxCell>
        <mxCell id="z4" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="40" y="620" width="380" height="210" as="geometry"/></mxCell>
        <mxCell id="z4l" value="Campus A" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="50" y="625" width="90" height="20" as="geometry"/></mxCell>
        <mxCell id="z5" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="470" y="620" width="380" height="210" as="geometry"/></mxCell>
        <mxCell id="z5l" value="Campus B" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="480" y="625" width="90" height="20" as="geometry"/></mxCell>
        <mxCell id="n1" value="Internet" style="shape=mxgraph.cisco.storage.cloud;html=1;strokeColor=#23445D;fillColor=#ffffff;strokeWidth=2;fontSize=16;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="360" y="20" width="170" height="95" as="geometry"/></mxCell>
        <mxCell id="n2" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="406" y="150" width="78" height="53" as="geometry"/></mxCell>
        <mxCell id="n3" value="" style="shape=mxgraph.cisco.security.pix_firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="407" y="240" width="77" height="51" as="geometry"/></mxCell>
        <mxCell id="bus1" value="" style="line;html=1;strokeColor=#23445D" parent="1" vertex="1"><mxGeometry x="70" y="310" width="790" height="10" as="geometry"/></mxCell>
        <mxCell id="n4" value="" style="shape=mxgraph.cisco.misc.asa_5500;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="110" y="375" width="80" height="55" as="geometry"/></mxCell>
        <mxCell id="n5" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="70" y="465" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n6" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="190" y="465" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n7" value="" style="shape=mxgraph.cisco.switches.layer_3_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="428" y="370" width="64" height="64" as="geometry"/></mxCell>
        <mxCell id="n8" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="365" y="465" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n9" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="500" y="455" width="54" height="65" as="geometry"/></mxCell>
        <mxCell id="n10" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="726" y="370" width="78" height="53" as="geometry"/></mxCell>
        <mxCell id="n11" value="Branch" style="shape=mxgraph.cisco.storage.cloud;html=1;strokeColor=#23445D;fillColor=#ffffff;strokeWidth=2;fontSize=12;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="700" y="455" width="120" height="65" as="geometry"/></mxCell>
        <mxCell id="bus2" value="" style="line;html=1;strokeColor=#23445D" parent="1" vertex="1"><mxGeometry x="70" y="580" width="790" height="10" as="geometry"/></mxCell>
        <mxCell id="n12" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="150" y="660" width="101" height="50" as="geometry"/></mxCell>
        <mxCell id="n13" value="" style="shape=mxgraph.cisco.misc.access_point;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="80" y="750" width="75" height="34" as="geometry"/></mxCell>
        <mxCell id="n14" value="" style="shape=mxgraph.cisco.hubs_and_gateways.100baset_hub;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="240" y="745" width="90" height="45" as="geometry"/></mxCell>
        <mxCell id="n15" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="580" y="660" width="101" height="50" as="geometry"/></mxCell>
        <mxCell id="n16" value="" style="shape=mxgraph.cisco.misc.access_point;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="510" y="750" width="75" height="34" as="geometry"/></mxCell>
        <mxCell id="n17" value="" style="shape=mxgraph.cisco.hubs_and_gateways.100baset_hub;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="670" y="745" width="90" height="45" as="geometry"/></mxCell>
        <mxCell id="e1" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n1" target="n2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n2" target="n3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=4" parent="1" source="n3" target="bus1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="bus1" target="n4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="bus1" target="n7" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="bus1" target="n10" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n4" target="n5" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n4" target="n6" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n7" target="n8" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e10" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n7" target="n9" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e11" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n10" target="n11" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e12" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=4" parent="1" source="n7" target="bus2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e13" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="bus2" target="n12" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e14" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="bus2" target="n15" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e15" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n12" target="n13" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e16" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n12" target="n14" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e17" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n15" target="n16" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e18" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n15" target="n17" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **Zone backgrounds** are drawn first (lowest z-order) — `rounded=1;fillColor=#BAC8D3;opacity=60;strokeColor=none`. Zone labels use separate `text` cells positioned at the zone's top-left corner
2. **Bus bar backbone** uses `shape=line` as a horizontal bar connecting tiers. Core bus bar and distribution bus bar physically separate the three-tier hierarchy
3. **Uplinks to bus bars** use `strokeWidth=4` (thicker) to visually distinguish backbone connections from branch links (`strokeWidth=2`)
4. **All edges are bidirectional** — `endArrow=none;endFill=0` with `strokeColor=#23445D`. No directional arrows on physical network links
5. **DMZ zone** places ASA 5500 as the internal firewall between core bus bar and web servers. PIX firewall sits at the Internet edge above the core bus bar
6. **Server Farm zone** connects through L3 switch to both core (upward) and distribution (downward) bus bars, serving as the distribution hub
7. **WAN zone** uses router → cloud pattern to represent branch office connectivity
8. **Campus access zones** each contain a workgroup switch with access point and hub downstream — representing wired + wireless user segments
9. **Consistent Cisco icon style**: `fillColor=#036897;strokeColor=#ffffff;strokeWidth=2` across all device stencils. Cloud shapes use inverted style: `fillColor=#ffffff;strokeColor=#23445D`

