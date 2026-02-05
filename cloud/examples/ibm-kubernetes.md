# IBM Cloud Kubernetes Architecture

A containerized application running on IBM Cloud Kubernetes Service.

```drawio
<mxfile>
  <diagram name="IBM Kubernetes">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="title" value="IBM Cloud Kubernetes Architecture" style="text;fontSize=20;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1"><mxGeometry x="380" y="20" width="440" height="30" as="geometry"/></mxCell>
        <mxCell id="cloud" value="IBM Cloud" style="shape=mxgraph.ibm_cloud.ibm-cloud;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="560" y="80" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="vpc" value="VPC" style="rounded=1;arcSize=5;dashed=1;dashPattern=5 5;strokeColor=#0F62FE;fillColor=none;strokeWidth=2;verticalAlign=top;fontStyle=1;fontSize=14;" vertex="1" parent="1"><mxGeometry x="200" y="200" width="800" height="400" as="geometry"/></mxCell>
        <mxCell id="vpc_icon" value="VPC" style="shape=mxgraph.ibm_cloud.ibm-cloud--vpc;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="220" y="220" width="60" height="60" as="geometry"/></mxCell>
        <mxCell id="k8s" value="Kubernetes&#xa;Service" style="shape=mxgraph.ibm_cloud.ibm-cloud--kubernetes-service;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="360" y="300" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="vs1" value="Worker 1" style="shape=mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="520" y="260" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="vs2" value="Worker 2" style="shape=mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="680" y="260" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="vs3" value="Worker 3" style="shape=mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="840" y="260" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="storage" value="Block&#xa;Storage" style="shape=mxgraph.ibm_cloud.block-storage;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="520" y="420" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="pg" value="PostgreSQL" style="shape=mxgraph.ibm_cloud.database--postgresql;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="680" y="420" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="redis" value="Redis" style="shape=mxgraph.ibm_cloud.database--redis;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="840" y="420" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="kp" value="Key Protect" style="shape=mxgraph.ibm_cloud.ibm-cloud--key-protect;fillColor=#0F62FE;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1"><mxGeometry x="360" y="420" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="cloud" target="vpc_icon"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="k8s" target="vs1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="k8s" target="vs2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="k8s" target="vs3"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="vs1" target="storage"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="vs2" target="pg"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="vs3" target="redis"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="k8s" target="kp"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/ibm_cloud.md`:

- `mxgraph.ibm_cloud.ibm-cloud`
- `mxgraph.ibm_cloud.ibm-cloud--vpc`
- `mxgraph.ibm_cloud.ibm-cloud--kubernetes-service`
- `mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc`
- `mxgraph.ibm_cloud.block-storage`
- `mxgraph.ibm_cloud.database--postgresql`
- `mxgraph.ibm_cloud.database--redis`
- `mxgraph.ibm_cloud.ibm-cloud--key-protect`
