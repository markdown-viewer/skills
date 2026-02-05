# OpenStack Basic Infrastructure

A basic OpenStack deployment with compute, network, and storage.

```drawio
<mxfile>
  <diagram name="OpenStack Basic">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="title" value="OpenStack Infrastructure" style="text;fontSize=20;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1"><mxGeometry x="420" y="20" width="360" height="30" as="geometry"/></mxCell>
        <mxCell id="ext_net" value="External&#xa;Network" style="shape=mxgraph.openstack.neutron_net;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="560" y="80" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="router" value="Router" style="shape=mxgraph.openstack.neutron_router;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="560" y="200" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="sg" value="Security&#xa;Group" style="shape=mxgraph.openstack.neutron_securitygroup;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="720" y="200" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="private" value="Private Network" style="rounded=1;arcSize=5;dashed=1;dashPattern=5 5;strokeColor=#ED1944;fillColor=none;strokeWidth=2;verticalAlign=top;fontStyle=1;fontSize=14;" vertex="1" parent="1"><mxGeometry x="200" y="320" width="800" height="300" as="geometry"/></mxCell>
        <mxCell id="subnet" value="Subnet" style="shape=mxgraph.openstack.neutron_subnet;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="560" y="360" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="server1" value="Web Server" style="shape=mxgraph.openstack.nova_server;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="320" y="480" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="server2" value="App Server" style="shape=mxgraph.openstack.nova_server;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="560" y="480" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="server3" value="DB Server" style="shape=mxgraph.openstack.nova_server;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="800" y="480" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="fip1" value="Floating IP" style="shape=mxgraph.openstack.neutron_floatingip;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="320" y="360" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="vol" value="Volume" style="shape=mxgraph.openstack.cinder_volume;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="920" y="480" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="swift" value="Swift&#xa;Container" style="shape=mxgraph.openstack.swift_container;fillColor=#ED1944;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="920" y="360" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="ext_net" target="router"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="router" target="subnet"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="subnet" target="server1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="subnet" target="server2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="subnet" target="server3"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="fip1" target="server1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="server3" target="vol"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="server2" target="swift"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;dashed=1;" edge="1" parent="1" source="sg" target="server1"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/openstack.md`:

- `mxgraph.openstack.neutron_net`
- `mxgraph.openstack.neutron_router`
- `mxgraph.openstack.neutron_securitygroup`
- `mxgraph.openstack.neutron_subnet`
- `mxgraph.openstack.neutron_floatingip`
- `mxgraph.openstack.nova_server`
- `mxgraph.openstack.cinder_volume`
- `mxgraph.openstack.swift_container`
