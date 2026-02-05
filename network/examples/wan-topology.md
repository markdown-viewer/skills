# WAN Topology Diagram

Shows a wide area network connecting multiple remote sites through a central backbone.

## Key Elements

- **Central Router**: Core routing device connecting all sites
- **Branch Sites**: Remote office locations
- **MPLS/VPN Cloud**: WAN backbone representation
- **Edge Devices**: Routers and firewalls at each site
- **Building Icons**: `shape=mxgraph.cisco.buildings.generic_building`, `small_business`, `branch_office`
- **Satellite/Ground Terminal**: `shape=mxgraph.cisco.wireless.ground_terminal`

## WAN Connection Types

| Type | Visual | Use Case |
|------|--------|----------|
| MPLS | Solid thick line | Primary backbone |
| Internet VPN | Dashed line | Backup/remote access |
| Leased Line | Double line | Point-to-point |
| Satellite | Wave pattern | Remote locations |

## Example

Enterprise WAN with headquarters, branches, and remote workers:

```drawio
<mxfile><diagram id="wan-topology" name="WAN"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-hq" value="Headquarters" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#d5e8d4;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="300" y="40" width="200" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-dc" value="Data Center" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#dae8fc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="540" y="40" width="200" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-br1" value="Branch Office A" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#fff2cc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="380" width="180" height="160" as="geometry"/></mxCell>
  <mxCell id="zone-br2" value="Branch Office B" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#fff2cc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="310" y="440" width="180" height="160" as="geometry"/></mxCell>
  <mxCell id="zone-remote" value="Remote Site" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#f8cecc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="580" y="380" width="180" height="160" as="geometry"/></mxCell>
  <mxCell id="mpls-cloud" value="MPLS / WAN" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#036897;fillColor=#ffffff;fontSize=14;fontColor=#036897;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="310" y="260" width="180" height="120" as="geometry"/></mxCell>
  <mxCell id="hq-building" value="" style="shape=mxgraph.cisco.buildings.generic_building;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="355" y="70" width="70" height="100" as="geometry"/></mxCell>
  <mxCell id="dc-server1" value="" style="shape=mxgraph.cisco.servers.fileserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="570" y="100" width="40" height="60" as="geometry"/></mxCell>
  <mxCell id="dc-server2" value="" style="shape=mxgraph.cisco.servers.fileserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="620" y="100" width="40" height="60" as="geometry"/></mxCell>
  <mxCell id="dc-storage" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="670" y="90" width="50" height="75" as="geometry"/></mxCell>
  <mxCell id="hq-router" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="355" y="185" width="70" height="45" as="geometry"/></mxCell>
  <mxCell id="dc-switch" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="580" y="185" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="br1-building" value="" style="shape=mxgraph.cisco.buildings.small_business;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="95" y="415" width="60" height="50" as="geometry"/></mxCell>
  <mxCell id="br1-router" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="80" y="480" width="65" height="40" as="geometry"/></mxCell>
  <mxCell id="br2-building" value="" style="shape=mxgraph.cisco.buildings.small_business;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="365" y="475" width="60" height="50" as="geometry"/></mxCell>
  <mxCell id="br2-router" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="350" y="540" width="65" height="40" as="geometry"/></mxCell>
  <mxCell id="remote-terminal" value="" style="shape=mxgraph.cisco.wireless.ground_terminal;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="640" y="410" width="60" height="70" as="geometry"/></mxCell>
  <mxCell id="remote-house" value="" style="shape=mxgraph.cisco.buildings.telecommuter_house;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="620" y="490" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="link-hq-bld-router" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="hq-building" target="hq-router" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dc-server1" target="dc-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc-sw2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dc-server2" target="dc-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc-sw3" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dc-storage" target="dc-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-hq-mpls" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="hq-router" target="mpls-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc-mpls" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="dc-switch" target="mpls-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-br1-bld-router" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="br1-building" target="br1-router" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-br1-mpls" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="br1-router" target="mpls-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-br2-bld-router" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="br2-building" target="br2-router" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-br2-mpls" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="br2-router" target="mpls-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-remote-sat" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;dashed=1;" parent="1" source="remote-terminal" target="mpls-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-remote-house" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="remote-house" target="remote-terminal" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

