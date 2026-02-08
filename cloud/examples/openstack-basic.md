# OpenStack Basic Infrastructure

Basic OpenStack deployment with Neutron networking, Nova compute, Cinder block storage, and Swift object storage.

## Key Elements

| Component | Stencil | Size | Color | Notes |
|-----------|---------|------|-------|-------|
| Network | container `rounded=1` | — | `#0D5FA6` border | Neutron blue, `fillColor=none` |
| Subnet | container `dashed=1` | — | `#0D5FA6` border | Nested inside network |
| Router | `mxgraph.openstack.neutron_router` | 50×50 | `fillColor=#0D5FA6` | Neutron blue |
| Floating IP | `mxgraph.openstack.neutron_floatingip` | 50×50 | `fillColor=#0D5FA6` | Neutron blue |
| Security Group | `mxgraph.openstack.neutron_securitygroup` | 50×50 | `fillColor=#0D5FA6` | Neutron blue |
| VM (Nova) | `mxgraph.openstack.nova_server` | 50×50 | `fillColor=#DA1A32` | Nova red |
| Volume (Cinder) | `mxgraph.openstack.cinder_volume` | 50×50 | `fillColor=#44B984` | Cinder green |
| Object Storage | `mxgraph.openstack.swift_container` | 50×50 | `fillColor=#F7A824` | Swift orange |

**All stencils are 53×53 native, displayed at 50×50.** Color-coded by service: Neutron=`#0D5FA6`, Nova=`#DA1A32`, Cinder=`#44B984`, Swift=`#F7A824`.

## Example

```drawio
<mxfile><diagram id="os-basic" name="OpenStack Basic"><mxGraphModel dx="960" dy="520" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="960" pageHeight="520" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="internet" value="Internet" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;fontSize=12;" vertex="1" parent="1"><mxGeometry x="40" y="170" width="100" height="60" as="geometry"/></mxCell>
  <mxCell id="fip" value="Floating IP" style="shape=mxgraph.openstack.neutron_floatingip;html=1;fillColor=#0D5FA6;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#0D5FA6;" vertex="1" parent="1"><mxGeometry x="225" y="80" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="router" value="Router" style="shape=mxgraph.openstack.neutron_router;html=1;fillColor=#0D5FA6;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#0D5FA6;" vertex="1" parent="1"><mxGeometry x="225" y="175" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="net" value="Internal Network" style="rounded=1;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;fillColor=none;strokeColor=#0D5FA6;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;spacingTop=5;fontSize=13;fontStyle=1;fontColor=#0D5FA6;arcSize=8;" vertex="1" parent="1"><mxGeometry x="380" y="30" width="530" height="290" as="geometry"/></mxCell>
  <mxCell id="subnet" value="Subnet 10.0.0.0/24" style="rounded=0;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;fillColor=none;strokeColor=#0D5FA6;strokeWidth=1;dashed=1;dashPattern=4 4;verticalAlign=top;align=left;spacingLeft=10;spacingTop=5;fontSize=11;fontColor=#0D5FA6;" vertex="1" parent="net"><mxGeometry x="20" y="40" width="490" height="230" as="geometry"/></mxCell>
  <mxCell id="sg" value="Security&#xa;Group" style="shape=mxgraph.openstack.neutron_securitygroup;html=1;fillColor=#0D5FA6;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#0D5FA6;" vertex="1" parent="subnet"><mxGeometry x="30" y="50" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vm1" value="Web Server" style="shape=mxgraph.openstack.nova_server;html=1;fillColor=#DA1A32;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#DA1A32;" vertex="1" parent="subnet"><mxGeometry x="170" y="50" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vm2" value="App Server" style="shape=mxgraph.openstack.nova_server;html=1;fillColor=#DA1A32;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#DA1A32;" vertex="1" parent="subnet"><mxGeometry x="340" y="50" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vol1" value="Volume 1" style="shape=mxgraph.openstack.cinder_volume;html=1;fillColor=#44B984;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#44B984;" vertex="1" parent="1"><mxGeometry x="570" y="390" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vol2" value="Volume 2" style="shape=mxgraph.openstack.cinder_volume;html=1;fillColor=#44B984;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#44B984;" vertex="1" parent="1"><mxGeometry x="720" y="390" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="swift" value="Object&#xa;Storage" style="shape=mxgraph.openstack.swift_container;html=1;fillColor=#F7A824;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#F7A824;" vertex="1" parent="1"><mxGeometry x="430" y="390" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#666666;" edge="1" parent="1" source="internet" target="router"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#0D5FA6;dashed=1;" edge="1" parent="1" source="fip" target="router"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#0D5FA6;entryX=0;entryY=0.5;" edge="1" parent="1" source="router" target="net"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#0D5FA6;dashed=1;" edge="1" parent="subnet" source="sg" target="vm1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#0D5FA6;dashed=1;exitX=1;exitY=0.3;entryX=0;entryY=0.5;" edge="1" parent="subnet" source="sg" target="vm2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#44B984;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" edge="1" parent="1" source="vm1" target="vol1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#44B984;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" edge="1" parent="1" source="vm2" target="vol2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e8" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#F7A824;dashed=1;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" edge="1" parent="1" source="vm2" target="swift"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="745" y="360"/><mxPoint x="455" y="360"/></Array></mxGeometry></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. OpenStack stencils use `shape=mxgraph.openstack.<name>` — all 18 shapes are 53×53 native size, all require `fillColor`
2. Color-coded by service: Neutron=`#0D5FA6` (blue), Nova=`#DA1A32` (red), Cinder=`#44B984` (green), Swift=`#F7A824` (orange)
3. Network hierarchy: Network container (`rounded=1;strokeColor=#0D5FA6`) → Subnet (`dashed=1`) → VMs + Security Group inside
4. Cross-container edges (VM→Volume) use `parent="1"` with explicit `exitX/exitY/entryX/entryY` to route through container borders
