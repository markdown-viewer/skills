# Hybrid Cloud Network Diagram

Shows a hybrid cloud architecture connecting on-premise infrastructure with cloud services.

## Key Elements

| Component | Stencil | fillColor |
|-----------|---------|-----------|
| Edge Router | `mxgraph.cisco.routers.router` | `#036897` |
| PIX Firewall | `mxgraph.cisco.security.pix_firewall` | `#036897` |
| VPN Concentrator | `mxgraph.cisco_safe.architecture.vpn_concentrator` | `#036897` |
| Core Switch | `mxgraph.cisco.switches.layer_3_switch` | `#036897` |
| Server | `mxgraph.cisco.servers.standard_host` | `#036897` |
| Storage | `mxgraph.cisco.servers.storage_server` | `#036897` |
| Data Center | `mxgraph.cisco19.data_center` | `#036897` |
| Internet Cloud | `ellipse;shape=cloud` | `#ffffff` |

- All Cisco device icons: `strokeColor=#ffffff;strokeWidth=2`
- On-Premise zone: `rounded=1;fillColor=#E6E6E6;strokeColor=none` (gray background)
- Cloud zone: `rounded=1;dashed=1;dashPattern=8 8;fillColor=none;strokeColor=#0BA5C4` (blue dashed border)
- Zone labels: separate `text` cell with `fontStyle=1;fontColor=#23445D`

## Connection Types

| Type | Style | Use Case |
|------|-------|----------|
| Site-to-Site VPN | `dashed=1;strokeColor=#036897;strokeWidth=2` | Encrypted tunnel between sites |
| Direct Connect | `strokeColor=#036897;strokeWidth=3` | Dedicated private link |
| LAN Link | `strokeColor=#23445D;strokeWidth=2;endArrow=none;endFill=0` | Internal physical link |
| Internet | `strokeColor=#b85450;strokeWidth=1` | Public access path |

## Example

Enterprise hybrid cloud connecting on-premise data center to cloud services via VPN:

```drawio
<mxfile>
  <diagram id="hc-1" name="Hybrid Cloud">
    <mxGraphModel dx="1100" dy="780" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="780" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- On-Premise Data Center zone -->
        <mxCell id="z1" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#E6E6E6;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="40" y="280" width="400" height="280" as="geometry"/></mxCell>
        <mxCell id="z1l" value="On-Premise Data Center" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="50" y="285" width="200" height="20" as="geometry"/></mxCell>
        <!-- Cloud zone -->
        <mxCell id="z2" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#0BA5C4;dashed=1;dashPattern=8 8;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="620" y="280" width="440" height="280" as="geometry"/></mxCell>
        <mxCell id="z2l" value="Cloud (IaaS)" style="text;html=1;strokeColor=none;fillColor=none;fontSize=14;fontColor=#0BA5C4;fontStyle=1" parent="1" vertex="1"><mxGeometry x="630" y="285" width="120" height="20" as="geometry"/></mxCell>
        <!-- Cloud sub-zones -->
        <mxCell id="z2a" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#D4E1F5;strokeColor=none;opacity=50" parent="1" vertex="1"><mxGeometry x="640" y="320" width="190" height="220" as="geometry"/></mxCell>
        <mxCell id="z2al" value="Compute" style="text;html=1;strokeColor=none;fillColor=none;fontSize=12;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="650" y="325" width="70" height="18" as="geometry"/></mxCell>
        <mxCell id="z2b" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#D5E8D4;strokeColor=none;opacity=50" parent="1" vertex="1"><mxGeometry x="850" y="320" width="190" height="220" as="geometry"/></mxCell>
        <mxCell id="z2bl" value="Storage / DB" style="text;html=1;strokeColor=none;fillColor=none;fontSize=12;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="860" y="325" width="90" height="18" as="geometry"/></mxCell>
        <!-- Internet cloud -->
        <mxCell id="n1" value="Internet" style="ellipse;shape=cloud;html=1;strokeColor=#23445D;fillColor=#ffffff;strokeWidth=2;fontSize=16;fontColor=#23445D;fontStyle=1" parent="1" vertex="1"><mxGeometry x="420" y="50" width="200" height="120" as="geometry"/></mxCell>
        <!-- On-Prem devices -->
        <mxCell id="n2" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="80" y="315" width="78" height="53" as="geometry"/></mxCell>
        <mxCell id="n3" value="" style="shape=mxgraph.cisco.security.pix_firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="200" y="318" width="77" height="51" as="geometry"/></mxCell>
        <mxCell id="n4" value="" style="shape=mxgraph.cisco_safe.architecture.vpn_concentrator;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="330" y="315" width="80" height="55" as="geometry"/></mxCell>
        <mxCell id="n5" value="" style="shape=mxgraph.cisco.switches.layer_3_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="180" y="410" width="64" height="64" as="geometry"/></mxCell>
        <mxCell id="n6" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="80" y="490" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n7" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="190" y="490" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n8" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="300" y="480" width="54" height="65" as="geometry"/></mxCell>
        <!-- Cloud devices -->
        <mxCell id="n9" value="" style="shape=mxgraph.cisco19.data_center;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="670" y="360" width="60" height="60" as="geometry"/></mxCell>
        <mxCell id="n10" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="680" y="455" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n11" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="760" y="455" width="43" height="50" as="geometry"/></mxCell>
        <mxCell id="n12" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="880" y="360" width="54" height="65" as="geometry"/></mxCell>
        <mxCell id="n13" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="960" y="360" width="54" height="65" as="geometry"/></mxCell>
        <mxCell id="n14" value="" style="shape=mxgraph.cisco_safe.architecture.vpn_concentrator;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="880" y="460" width="80" height="55" as="geometry"/></mxCell>
        <!-- Edges: On-Prem internal (LAN links, no arrows) -->
        <mxCell id="e1" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n2" target="n3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n3" target="n4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n3" target="n5" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n5" target="n6" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n5" target="n7" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n5" target="n8" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Edge: Router to Internet -->
        <mxCell id="e7" style="endArrow=none;html=1;strokeColor=#b85450;endFill=0;strokeWidth=1" parent="1" source="n2" target="n1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Edge: VPN tunnel (dashed) through Internet -->
        <mxCell id="e8" style="endArrow=blockThin;html=1;strokeColor=#036897;endFill=1;strokeWidth=2;dashed=1" parent="1" source="n4" target="n1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" style="endArrow=blockThin;html=1;strokeColor=#036897;endFill=1;strokeWidth=2;dashed=1" parent="1" source="n1" target="n14" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <!-- Cloud internal links -->
        <mxCell id="e10" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n14" target="n9" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e11" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n9" target="n10" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e12" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n9" target="n11" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e13" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n9" target="n12" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e14" style="endArrow=none;html=1;strokeColor=#23445D;endFill=0;strokeWidth=2" parent="1" source="n9" target="n13" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **Two contrasting zone styles** distinguish on-premise vs cloud: gray solid fill (`fillColor=#E6E6E6;strokeColor=none`) for on-prem, blue dashed border (`dashed=1;dashPattern=8 8;strokeColor=#0BA5C4;fillColor=none`) for cloud — matching the real-world fixtures pattern
2. **Cloud sub-zones** use light colored fills with opacity to group compute resources (`fillColor=#D4E1F5;opacity=50`) and storage/DB (`fillColor=#D5E8D4;opacity=50`) within the cloud boundary
3. **VPN tunnel** uses `dashed=1;strokeColor=#036897;strokeWidth=2` with directional arrows (`endArrow=blockThin;endFill=1`), visually distinct from solid LAN links. The tunnel path goes: on-prem VPN concentrator → Internet cloud → cloud VPN concentrator
4. **Internet link** uses `strokeColor=#b85450` (red-tinted) to distinguish public Internet access from private VPN and LAN connections
5. **Internal LAN links** are all `endArrow=none;endFill=0` (no arrows, bidirectional) with `strokeColor=#23445D;strokeWidth=2` — consistent with standard network diagram conventions
6. **VPN concentrator pair** — one on each side (`mxgraph.cisco_safe.architecture.vpn_concentrator`) at the boundary of on-prem and cloud zones, establishing the site-to-site tunnel endpoints
7. **On-prem topology**: Edge router → Firewall → VPN concentrator (for cloud) + L3 switch (for internal) → servers/storage. The firewall sits between the router and all internal resources
8. **Cloud topology**: VPN concentrator → Data center switch (`mxgraph.cisco19.data_center`) → compute servers + storage, keeping a similar hierarchical pattern to on-prem
9. **Zone labels** use separate `text` cells positioned at the top-left corner of each zone, not the zone cell's `value` attribute — preventing label overlap with child elements

