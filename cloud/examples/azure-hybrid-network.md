# Azure Hybrid Network Architecture

On-premises data center connected to Azure VNet via Site-to-Site VPN.

## Key Elements

| Component | Stencil | fillColor |
|-----------|---------|-----------|
| User | `mxgraph.azure.user` | `#0078D4` |
| Computer | `mxgraph.azure.computer` | `#FF8C00` (on-prem) |
| Virtual Machine | `mxgraph.azure.virtual_machine` | `#0078D4` |
| VPN Gateway | `mxgraph.mscae.cloud.vpn_gateway2` | `#0078D4` |
| On-prem Gateway | `mxgraph.mscae.enterprise.gateway` | `#FF8C00` |
| Load Balancer | `mxgraph.mscae.cloud.azure_load_balancer_feature` | `#0078D4` |
| Firewall | `mxgraph.office.concepts.firewall` | `#D83B01` |
| Azure AD | `mxgraph.azure.azure_active_directory` | `#0078D4` |
| AD Server | `mxgraph.mscae.enterprise.server_directory` | `#FF8C00` |
| Storage | `mxgraph.azure.storage` | `#0078D4` |

**Stencil libraries:** `mxgraph.azure.*` (core), `mxgraph.mscae.cloud.*` / `mxgraph.mscae.enterprise.*` (infra), `mxgraph.office.concepts.*` (icons). No built-in group containers — use plain rectangles.

**Colors:** Azure Blue `#0078D4`, On-Premises `#FF8C00`, Security `#D83B01`, VNet `#5C2D91`, Subnet green `#7AA116` / blue `#147EBA`.

## Example

```drawio
<mxfile><diagram id="azure-hybrid" name="Azure Hybrid Network"><mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="800" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="onprem" value="On-Premises Data Center" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=0;strokeColor=#FF8C00;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=14;fontStyle=1;fontColor=#FF8C00;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="1"><mxGeometry x="140" y="40" width="260" height="680" as="geometry"/></mxCell>
  <mxCell id="pc1" value="Workstation 1" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#FF8C00;shape=mxgraph.azure.computer;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="onprem"><mxGeometry x="30" y="70" width="50" height="45" as="geometry"/></mxCell>
  <mxCell id="pc2" value="Workstation 2" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#FF8C00;shape=mxgraph.azure.computer;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="onprem"><mxGeometry x="30" y="200" width="50" height="45" as="geometry"/></mxCell>
  <mxCell id="ad-server" value="AD Server" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#FF8C00;shape=mxgraph.mscae.enterprise.server_directory;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="onprem"><mxGeometry x="35" y="400" width="40" height="50" as="geometry"/></mxCell>
  <mxCell id="fw" value="Firewall" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#D83B01;shape=mxgraph.office.concepts.firewall;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="onprem"><mxGeometry x="155" y="180" width="47" height="43" as="geometry"/></mxCell>
  <mxCell id="onprem-gw" value="Gateway" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#FF8C00;shape=mxgraph.mscae.enterprise.gateway;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="onprem"><mxGeometry x="155" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="azure-cloud" value="Azure Cloud" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=0;strokeColor=#0078D4;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=14;fontStyle=1;fontColor=#0078D4;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="1"><mxGeometry x="560" y="40" width="600" height="680" as="geometry"/></mxCell>
  <mxCell id="aad" value="Azure Active&#xa;Directory" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.azure_active_directory;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="azure-cloud"><mxGeometry x="60" y="30" width="48" height="50" as="geometry"/></mxCell>
  <mxCell id="vnet" value="Virtual Network (10.0.0.0/16)" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#5C2D91;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#5C2D91;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="azure-cloud"><mxGeometry x="20" y="120" width="560" height="530" as="geometry"/></mxCell>
  <mxCell id="gw-subnet" value="Gateway Subnet" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#7AA116;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontSize=11;fontColor=#7AA116;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="vnet"><mxGeometry x="20" y="40" width="130" height="160" as="geometry"/></mxCell>
  <mxCell id="vpn-gw" value="VPN&#xa;Gateway" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.mscae.cloud.vpn_gateway2;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="gw-subnet"><mxGeometry x="43" y="50" width="45" height="50" as="geometry"/></mxCell>
  <mxCell id="fe-subnet" value="Frontend Subnet" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#7AA116;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontSize=11;fontColor=#7AA116;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="vnet"><mxGeometry x="180" y="40" width="350" height="170" as="geometry"/></mxCell>
  <mxCell id="lb" value="Load Balancer" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.mscae.cloud.azure_load_balancer_feature;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="fe-subnet"><mxGeometry x="145" y="5" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vm1" value="Web VM 1" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.virtual_machine;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="fe-subnet"><mxGeometry x="40" y="100" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="vm2" value="Web VM 2" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.virtual_machine;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="fe-subnet"><mxGeometry x="260" y="100" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="be-subnet" value="Backend Subnet" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#147EBA;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontSize=11;fontColor=#147EBA;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="vnet"><mxGeometry x="180" y="250" width="350" height="160" as="geometry"/></mxCell>
  <mxCell id="vm3" value="App VM 1" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.virtual_machine;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="be-subnet"><mxGeometry x="40" y="60" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="vm4" value="App VM 2" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.virtual_machine;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="be-subnet"><mxGeometry x="260" y="60" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="storage" value="Azure&#xa;Storage" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.storage;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="vnet"><mxGeometry x="430" y="320" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="users" value="Users" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;strokeColor=none;fillColor=#0078D4;shape=mxgraph.azure.user;aspect=fixed;fontSize=12;fontColor=#232F3E;align=center;" vertex="1" parent="1"><mxGeometry x="40" y="290" width="48" height="50" as="geometry"/></mxCell>
  <mxCell id="link-users-pc1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF8C00;" edge="1" parent="1" source="users" target="pc1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-pc1-fw" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF8C00;" edge="1" parent="1" source="pc1" target="fw"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-pc2-fw" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF8C00;" edge="1" parent="1" source="pc2" target="fw"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-gw" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#D83B01;" edge="1" parent="1" source="fw" target="onprem-gw"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vpn" value="Site-to-Site VPN" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;startArrow=classic;endArrow=classic;strokeWidth=3;strokeColor=#0078D4;dashed=1;fontSize=11;fontColor=#0078D4;labelBackgroundColor=#FFFFFF;" edge="1" parent="1" source="onprem-gw" target="vpn-gw"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vpn-lb" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0078D4;" edge="1" parent="1" source="vpn-gw" target="lb"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lb-vm1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0078D4;" edge="1" parent="1" source="lb" target="vm1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lb-vm2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0078D4;" edge="1" parent="1" source="lb" target="vm2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vm1-vm3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#505050;" edge="1" parent="1" source="vm1" target="vm3"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vm2-vm4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#505050;" edge="1" parent="1" source="vm2" target="vm4"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vm3-stor" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0078D4;" edge="1" parent="1" source="vm3" target="storage"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ad-sync" value="AD Sync" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;startArrow=classic;endArrow=classic;strokeWidth=2;strokeColor=#5C2D91;dashed=1;fontSize=11;fontColor=#5C2D91;labelBackgroundColor=#FFFFFF;" edge="1" parent="1" source="ad-server" target="aad"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="470" y="465"/><mxPoint x="470" y="95"/></Array></mxGeometry></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. **Three stencil libraries**: `mxgraph.azure.*`, `mxgraph.mscae.*`, `mxgraph.office.*` — check correct prefix
2. **fillColor required**: Use `#0078D4` for Azure, `#FF8C00` for on-prem, `#D83B01` for firewall
3. **VPN tunnel**: Bidirectional dashed edge (`startArrow=classic;endArrow=classic;dashed=1`)
4. **AD Sync**: Purple dashed edge (`#5C2D91`) with waypoints routed through the gap between containers
5. **No group containers**: Use plain rectangles for VNet/subnet boundaries
