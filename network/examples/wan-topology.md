# WAN Topology Diagram

Shows a wide area network connecting multiple remote sites through a central backbone.

## Key Elements

| Component | Stencil | fillColor | strokeColor |
|-----------|---------|-----------|-------------|
| HQ Building | `mxgraph.cisco.buildings.generic_building` | `#036897` | `#ffffff` |
| Branch Office | `mxgraph.cisco.buildings.branch_office` | `#036897` | `#ffffff` |
| Telecommuter House | `mxgraph.cisco.buildings.telecommuter_house` | `#036897` | `#ffffff` |
| Edge Router | `mxgraph.cisco.routers.router` | `#036897` | `#ffffff` |
| PIX Firewall | `mxgraph.cisco.security.pix_firewall` | `#036897` | `#ffffff` |
| Ground Terminal | `mxgraph.cisco.wireless.ground_terminal` | `#036897` | `#ffffff` |
| Satellite Dish | `mxgraph.cisco.wireless.satellite_dish` | `#036897` | `#ffffff` |
| Satellite | `mxgraph.cisco.wireless.satellite` | `#036897` | `#ffffff` |
| VPN Gateway | `mxgraph.cisco.hubs_and_gateways.vpn_gateway` | `#036897` | `#ffffff` |
| MPLS/Internet Cloud | `mxgraph.cisco.storage.cloud` | `#ffffff` | `#23445D` |

- All Cisco device icons: `fillColor=#036897;strokeColor=#ffffff;strokeWidth=2`
- Cloud shapes use inverted palette: `fillColor=#ffffff;strokeColor=#23445D;strokeWidth=2`
- Zone backgrounds: `rounded=1;fillColor=#BAC8D3;strokeColor=none;opacity=60`
- Zone labels: separate `text` cell with `fillColor=none;strokeColor=none;fontStyle=1;fontColor=#23445D`

## WAN Connection Types

| Type | Style | Use Case |
|------|-------|----------|
| MPLS Primary | `endArrow=none;strokeWidth=3;strokeColor=#036897` | Primary backbone |
| Internet VPN | `endArrow=none;strokeWidth=2;dashed=1;strokeColor=#23445D` | Backup/remote access |
| Leased Line | `endArrow=none;strokeWidth=2;strokeColor=#23445D` | Point-to-point |
| Satellite Link | `endArrow=none;strokeWidth=2;dashed=1;dashPattern=8 4;strokeColor=#6881B3` | Remote locations |

## Example

Enterprise WAN with headquarters, two branch offices, remote worker, and satellite site:

```drawio
<mxfile>
  <diagram id="wan-1" name="WAN Topology">
    <mxGraphModel dx="1100" dy="780" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="780" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- Zone: Headquarters -->
        <mxCell id="z1" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="40" y="40" width="260" height="300" as="geometry"/></mxCell>
        <mxCell id="z1l" value="Headquarters" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="50" y="45" width="120" height="20" as="geometry"/></mxCell>
        <!-- Zone: Branch 1 -->
        <mxCell id="z2" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="40" y="530" width="220" height="210" as="geometry"/></mxCell>
        <mxCell id="z2l" value="Branch Office 1" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="50" y="535" width="130" height="20" as="geometry"/></mxCell>
        <!-- Zone: Branch 2 -->
        <mxCell id="z3" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="390" y="530" width="220" height="210" as="geometry"/></mxCell>
        <mxCell id="z3l" value="Branch Office 2" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="400" y="535" width="130" height="20" as="geometry"/></mxCell>
        <!-- Zone: Remote Site -->
        <mxCell id="z4" value="" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#BAC8D3;opacity=60;" parent="1" vertex="1"><mxGeometry x="800" y="40" width="260" height="300" as="geometry"/></mxCell>
        <mxCell id="z4l" value="Satellite Site" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="810" y="45" width="110" height="20" as="geometry"/></mxCell>
        <!-- MPLS/VPN Cloud -->
        <mxCell id="mpls" value="MPLS / VPN" style="shape=mxgraph.cisco.storage.cloud;html=1;strokeColor=#23445D;fillColor=#ffffff;strokeWidth=2;fontSize=16;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="420" y="280" width="200" height="120" as="geometry"/></mxCell>
        <!-- Internet Cloud -->
        <mxCell id="inet" value="Internet" style="shape=mxgraph.cisco.storage.cloud;html=1;strokeColor=#23445D;fillColor=#ffffff;strokeWidth=2;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="730" y="530" width="160" height="90" as="geometry"/></mxCell>
        <!-- HQ devices -->
        <mxCell id="hq-bld" value="HQ" style="shape=mxgraph.cisco.buildings.generic_building;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;fontColor=#23445D;fontSize=12;fontStyle=1" parent="1" vertex="1"><mxGeometry x="110" y="80" width="56" height="85" as="geometry"/></mxCell>
        <mxCell id="hq-fw" value="" style="shape=mxgraph.cisco.security.pix_firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="130" y="210" width="48" height="33" as="geometry"/></mxCell>
        <mxCell id="hq-rtr" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="128" y="270" width="49" height="33" as="geometry"/></mxCell>
        <!-- Branch 1 devices -->
        <mxCell id="br1-bld" value="Branch 1" style="shape=mxgraph.cisco.buildings.branch_office;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;fontColor=#23445D;fontSize=12;fontStyle=1" parent="1" vertex="1"><mxGeometry x="80" y="570" width="33" height="48" as="geometry"/></mxCell>
        <mxCell id="br1-rtr" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="130" y="660" width="49" height="33" as="geometry"/></mxCell>
        <!-- Branch 2 devices -->
        <mxCell id="br2-bld" value="Branch 2" style="shape=mxgraph.cisco.buildings.branch_office;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;fontColor=#23445D;fontSize=12;fontStyle=1" parent="1" vertex="1"><mxGeometry x="430" y="570" width="33" height="48" as="geometry"/></mxCell>
        <mxCell id="br2-rtr" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="480" y="660" width="49" height="33" as="geometry"/></mxCell>
        <!-- Satellite site devices -->
        <mxCell id="sat" value="" style="shape=mxgraph.cisco.wireless.satellite;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="888" y="80" width="85" height="28" as="geometry"/></mxCell>
        <mxCell id="sat-dish" value="" style="shape=mxgraph.cisco.wireless.satellite_dish;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="900" y="150" width="62" height="46" as="geometry"/></mxCell>
        <mxCell id="sat-gnd" value="" style="shape=mxgraph.cisco.wireless.ground_terminal;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="880" y="230" width="62" height="76" as="geometry"/></mxCell>
        <!-- Remote worker -->
        <mxCell id="remote" value="Remote&#xa;Worker" style="shape=mxgraph.cisco.buildings.telecommuter_house;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;fontColor=#23445D;fontSize=12;fontStyle=1" parent="1" vertex="1"><mxGeometry x="800" y="620" width="65" height="55" as="geometry"/></mxCell>
        <mxCell id="vpn-gw" value="" style="shape=mxgraph.cisco.hubs_and_gateways.vpn_gateway;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="950" y="640" width="58" height="30" as="geometry"/></mxCell>
        <!-- Edges: HQ internal -->
        <mxCell id="e1" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="hq-bld" target="hq-fw" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="hq-fw" target="hq-rtr" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- HQ Router → MPLS (primary, thick) -->
        <mxCell id="e3" style="endArrow=none;html=1;strokeColor=#036897;endFill=0;strokeWidth=3" parent="1" source="hq-rtr" target="mpls" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Branch 1 → MPLS -->
        <mxCell id="e4" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="br1-bld" target="br1-rtr" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" style="endArrow=none;html=1;strokeColor=#036897;endFill=0;strokeWidth=3" parent="1" source="br1-rtr" target="mpls" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Branch 2 → MPLS -->
        <mxCell id="e6" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="br2-bld" target="br2-rtr" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" style="endArrow=none;html=1;strokeColor=#036897;endFill=0;strokeWidth=3" parent="1" source="br2-rtr" target="mpls" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Satellite link (dashed) -->
        <mxCell id="e8" style="endArrow=none;html=1;strokeColor=#6881B3;endFill=0;strokeWidth=2;dashed=1;dashPattern=8 4" parent="1" source="sat" target="sat-dish" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="sat-dish" target="sat-gnd" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e10" style="endArrow=none;html=1;strokeColor=#036897;endFill=0;strokeWidth=3" parent="1" source="sat-gnd" target="mpls" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Internet VPN (dashed) -->
        <mxCell id="e11" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2;dashed=1" parent="1" source="remote" target="vpn-gw" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e12" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2;dashed=1" parent="1" source="vpn-gw" target="inet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e13" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2;dashed=1" parent="1" source="inet" target="mpls" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **Cisco stencil family** — WAN diagrams use `mxgraph.cisco.*` for all device icons. Unified device style: `fillColor=#036897;strokeColor=#ffffff;strokeWidth=2`. Cloud shapes use inverted style: `fillColor=#ffffff;strokeColor=#23445D`
2. **Zone backgrounds** are drawn first (lowest z-order) — `rounded=1;fillColor=#BAC8D3;opacity=60;strokeColor=none`. Zone labels use separate `text` cells positioned at the zone's top-left corner with `fontStyle=1;fontColor=#23445D`
3. **MPLS/VPN cloud** at the center represents the WAN backbone using `mxgraph.cisco.storage.cloud`. All site routers connect to this cloud. A separate Internet cloud is used for VPN-based remote access
4. **Connection line weights** differentiate link types: `strokeWidth=3` for MPLS primary backbone links, `strokeWidth=2` for internal links and secondary connections
5. **Dashed lines** (`dashed=1`) represent VPN tunnels over the Internet — visually distinguishing logical overlay connections from physical MPLS circuits
6. **Satellite links** use `dashed=1;dashPattern=8 4` with lighter color `strokeColor=#6881B3` for the wireless segment (satellite ↔ dish), then solid lines for the wired ground segment
7. **Building stencils** distinguish site types: `generic_building` for HQ, `branch_office` for branches, `telecommuter_house` for remote workers — all with `verticalLabelPosition=bottom` for labels below icons
8. **All edges are bidirectional** — `endArrow=none;endFill=0`. WAN physical topology links have no directional arrows

