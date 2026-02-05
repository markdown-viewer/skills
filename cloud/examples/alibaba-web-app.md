# Alibaba Cloud Web Application Architecture

A typical 3-tier web application on Alibaba Cloud.

```drawio
<mxfile>
  <diagram name="Alibaba Web App">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="title" value="Alibaba Cloud Web Application" style="text;fontSize=20;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="400" y="20" width="400" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="users" value="Users" style="shape=mxgraph.alibaba_cloud.user;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="560" y="80" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="cdn" value="CDN" style="shape=mxgraph.alibaba_cloud.cdn_content_distribution_network;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="560" y="200" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="slb" value="SLB" style="shape=mxgraph.alibaba_cloud.clb_classic_load_balancer_01;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="560" y="320" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="vpc" value="VPC" style="rounded=1;arcSize=5;dashed=1;dashPattern=5 5;strokeColor=#FF6A00;fillColor=none;strokeWidth=2;verticalAlign=top;fontStyle=1;fontSize=14;" vertex="1" parent="1">
          <mxGeometry x="200" y="440" width="800" height="280" as="geometry"/>
        </mxCell>
        <mxCell id="ecs1" value="ECS 1" style="shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="400" y="500" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="ecs2" value="ECS 2" style="shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="560" y="500" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="ecs3" value="ECS 3" style="shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="720" y="500" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="rds" value="RDS MySQL" style="shape=mxgraph.alibaba_cloud.mysql;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="400" y="620" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="redis" value="Redis" style="shape=mxgraph.alibaba_cloud.redis_kvstore;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="560" y="620" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="oss" value="OSS" style="shape=mxgraph.alibaba_cloud.oss_object_storage_service;fillColor=#FF6A00;strokeColor=none;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="720" y="620" width="80" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="users" target="cdn">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="cdn" target="slb">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="slb" target="ecs1">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="slb" target="ecs2">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="slb" target="ecs3">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="ecs1" target="rds">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e7" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="ecs2" target="redis">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="e8" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="ecs3" target="oss">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/alibaba_cloud.md`:

- `mxgraph.alibaba_cloud.user`
- `mxgraph.alibaba_cloud.cdn_content_distribution_network`
- `mxgraph.alibaba_cloud.clb_classic_load_balancer_01`
- `mxgraph.alibaba_cloud.ecs_elastic_compute_service`
- `mxgraph.alibaba_cloud.mysql`
- `mxgraph.alibaba_cloud.redis_kvstore`
- `mxgraph.alibaba_cloud.oss_object_storage_service`
