# IBM Cloud Kubernetes Architecture

Containerized microservices on IBM Cloud Kubernetes Service with VPC, load balancer, registry, and PostgreSQL.

## Key Elements

| Component | Stencil | fillColor |
|-----------|---------|-----------|
| IBM Cloud | container + `mxgraph.ibm.cloudtag` | `strokeColor=#4376BB` |
| VPC | container + `mxgraph.ibm.vpctag` | `strokeColor=#4376BB` |
| Zone | container (dashed) + `mxgraph.ibm.zonetag` | `strokeColor=#919191;fillColor=#E0E0E0` |
| Subnet | container + `mxgraph.ibm.subnettag` | `strokeColor=#00882B;fillColor=#E6F0E2` |
| K8s Service | `mxgraph.ibm_cloud.ibm-cloud--kubernetes-service` | bg `#198038`, icon `#ffffff` |
| App LB | `mxgraph.ibm_cloud.load-balancer--application` | bg `#1192E8`, icon `#ffffff` |
| Container Registry | `mxgraph.ibm_cloud.cloud-registry` | bg `#198038`, icon `#ffffff` |
| Virtual Server | `mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc` | bg `#198038`, icon `#ffffff` |
| PostgreSQL | `mxgraph.ibm_cloud.database--postgresql` | bg `#0F62FE`, icon `#ffffff` |
| User | `mxgraph.ibm_cloud.user` | bg `#000000`, icon `#ffffff` |

**IBM Cloud node pattern:** 48×48 colored rect background + 24×24 white stencil icon (centered, offset 12,12). Label below via `verticalLabelPosition=bottom`.

**Container pattern:** `container=1;collapsible=0` with tag stencil in top-left corner (16×16). Zones use `dashed=1;dashPattern=1 3`.

## Example

```drawio
<mxfile><diagram id="ibm-k8s" name="IBM Cloud K8s"><mxGraphModel dx="1050" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1050" pageHeight="680" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="cloud" value="IBM Cloud" style="html=1;whiteSpace=wrap;container=1;collapsible=0;expand=0;recursiveResize=0;strokeColor=#4376BB;fillColor=none;strokeWidth=3;verticalAlign=top;align=left;spacingLeft=40;spacingTop=5;fontSize=13;fontStyle=1;fontColor=#4376BB;" vertex="1" parent="1"><mxGeometry x="40" y="40" width="960" height="580" as="geometry"/></mxCell>
  <mxCell id="cloud-tag" value="" style="shape=mxgraph.ibm.cloudtag;fillColor=#4376BB;html=1;strokeColor=none;" vertex="1" parent="cloud"><mxGeometry x="5" y="5" width="16" height="16" as="geometry"/></mxCell>
  <mxCell id="vpc" value="VPC" style="html=1;whiteSpace=wrap;container=1;collapsible=0;expand=0;recursiveResize=0;strokeColor=#4376BB;fillColor=none;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=40;spacingTop=5;fontSize=12;fontStyle=1;fontColor=#4376BB;" vertex="1" parent="cloud"><mxGeometry x="20" y="60" width="920" height="490" as="geometry"/></mxCell>
  <mxCell id="vpc-tag" value="" style="shape=mxgraph.ibm.vpctag;fillColor=#4376BB;html=1;strokeColor=none;" vertex="1" parent="vpc"><mxGeometry x="5" y="5" width="16" height="16" as="geometry"/></mxCell>
  <mxCell id="zone" value="Zone 1" style="html=1;whiteSpace=wrap;container=1;collapsible=0;expand=0;recursiveResize=0;strokeColor=#919191;fillColor=#E0E0E0;strokeWidth=1;dashed=1;dashPattern=1 3;verticalAlign=top;align=left;spacingLeft=40;spacingTop=5;fontSize=12;fontColor=#919191;" vertex="1" parent="vpc"><mxGeometry x="20" y="50" width="880" height="420" as="geometry"/></mxCell>
  <mxCell id="zone-tag" value="" style="shape=mxgraph.ibm.zonetag;fillColor=#919191;html=1;strokeColor=none;" vertex="1" parent="zone"><mxGeometry x="5" y="5" width="16" height="16" as="geometry"/></mxCell>
  <mxCell id="subnet-pub" value="Public Subnet" style="html=1;whiteSpace=wrap;container=1;collapsible=0;expand=0;recursiveResize=0;strokeColor=#00882B;fillColor=#E6F0E2;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=40;spacingTop=5;fontSize=11;fontColor=#00882B;" vertex="1" parent="zone"><mxGeometry x="20" y="40" width="200" height="360" as="geometry"/></mxCell>
  <mxCell id="subnet-pub-tag" value="" style="shape=mxgraph.ibm.subnettag;fillColor=#00882B;html=1;strokeColor=none;" vertex="1" parent="subnet-pub"><mxGeometry x="5" y="5" width="16" height="16" as="geometry"/></mxCell>
  <mxCell id="subnet-priv" value="Private Subnet" style="html=1;whiteSpace=wrap;container=1;collapsible=0;expand=0;recursiveResize=0;strokeColor=#00882B;fillColor=#E6F0E2;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=40;spacingTop=5;fontSize=11;fontColor=#00882B;" vertex="1" parent="zone"><mxGeometry x="280" y="40" width="580" height="360" as="geometry"/></mxCell>
  <mxCell id="subnet-priv-tag" value="" style="shape=mxgraph.ibm.subnettag;fillColor=#00882B;html=1;strokeColor=none;" vertex="1" parent="subnet-priv"><mxGeometry x="5" y="5" width="16" height="16" as="geometry"/></mxCell>
  <mxCell id="lb-bg" value="App LB" style="shape=rect;fillColor=#1192E8;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#1192E8;" vertex="1" parent="subnet-pub"><mxGeometry x="76" y="60" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="lb-icon" value="" style="shape=mxgraph.ibm_cloud.load-balancer--application;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="lb-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="k8s-bg" value="Kubernetes&#xa;Service" style="shape=rect;fillColor=#198038;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#198038;" vertex="1" parent="subnet-priv"><mxGeometry x="60" y="60" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="k8s-icon" value="" style="shape=mxgraph.ibm_cloud.ibm-cloud--kubernetes-service;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="k8s-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="vs1-bg" value="Worker 1" style="shape=rect;fillColor=#198038;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#198038;" vertex="1" parent="subnet-priv"><mxGeometry x="60" y="200" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="vs1-icon" value="" style="shape=mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="vs1-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="vs2-bg" value="Worker 2" style="shape=rect;fillColor=#198038;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#198038;" vertex="1" parent="subnet-priv"><mxGeometry x="180" y="200" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="vs2-icon" value="" style="shape=mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="vs2-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="reg-bg" value="Container&#xa;Registry" style="shape=rect;fillColor=#198038;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#198038;" vertex="1" parent="subnet-priv"><mxGeometry x="340" y="60" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="reg-icon" value="" style="shape=mxgraph.ibm_cloud.cloud-registry;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="reg-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="db-bg" value="PostgreSQL" style="shape=rect;fillColor=#0F62FE;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#0F62FE;" vertex="1" parent="subnet-priv"><mxGeometry x="470" y="140" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="db-icon" value="" style="shape=mxgraph.ibm_cloud.database--postgresql;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="db-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="user-bg" value="User" style="shape=rect;fillColor=#000000;strokeColor=none;aspect=fixed;html=1;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#000000;" vertex="1" parent="1"><mxGeometry x="126" y="300" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="user-icon" value="" style="shape=mxgraph.ibm_cloud.user;fillColor=#ffffff;strokeColor=none;html=1;part=1;movable=0;resizable=0;rotatable=0;" vertex="1" parent="user-bg"><mxGeometry x="12" y="12" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#4376BB;" edge="1" parent="1" source="user-bg" target="lb-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#4376BB;" edge="1" parent="1" source="lb-bg" target="k8s-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#198038;exitX=0.5;exitY=1;entryX=0.25;entryY=0;" edge="1" parent="1" source="k8s-bg" target="vs1-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#198038;exitX=0.5;exitY=1;entryX=0.25;entryY=0;" edge="1" parent="1" source="k8s-bg" target="vs2-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#198038;" edge="1" parent="1" source="k8s-bg" target="reg-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0F62FE;exitX=1;exitY=0.5;" edge="1" parent="1" source="vs1-bg" target="db-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0F62FE;exitX=1;exitY=0.5;" edge="1" parent="1" source="vs2-bg" target="db-bg"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. IBM Cloud nodes: 48×48 colored rect + 24×24 white stencil icon (offset 12,12). Colors by category: Compute `#198038`, Network `#1192E8`, Data `#0F62FE`, Actor `#000000`
2. Containers use tag stencils (`mxgraph.ibm.cloudtag/vpctag/zonetag/subnettag`) at 16×16 in top-left corner
3. Container hierarchy: IBM Cloud → VPC → Zone (dashed, `#E0E0E0` fill) → Subnet (`#E6F0E2` fill)
4. Edges colored by target category; `strokeWidth=2` with `endArrow=classic`
