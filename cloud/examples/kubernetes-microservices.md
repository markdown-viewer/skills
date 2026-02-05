# Kubernetes Microservices Architecture

A typical microservices deployment on Kubernetes with Ingress, Services, Deployments, and persistent storage.

```drawio
<mxfile>
  <diagram name="Kubernetes Microservices">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="title" value="Kubernetes Microservices Architecture" style="text;fontSize=20;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1"><mxGeometry x="350" y="20" width="500" height="30" as="geometry"/></mxCell>
        <mxCell id="users" value="Users" style="shape=mxgraph.kubernetes.user;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=12;" vertex="1" parent="1"><mxGeometry x="560" y="70" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="cluster" value="Kubernetes Cluster" style="rounded=1;arcSize=5;dashed=1;dashPattern=5 5;strokeColor=#326CE5;fillColor=none;strokeWidth=2;verticalAlign=top;fontStyle=1;fontSize=14;fontColor=#326CE5;" vertex="1" parent="1"><mxGeometry x="120" y="180" width="960" height="520" as="geometry"/></mxCell>
        <mxCell id="ingress" value="Ingress" style="shape=mxgraph.kubernetes.ing;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=12;" vertex="1" parent="1"><mxGeometry x="560" y="220" width="80" height="70" as="geometry"/></mxCell>
        <mxCell id="ns_prod" value="Namespace: production" style="rounded=1;arcSize=5;dashed=1;dashPattern=3 3;strokeColor=#82b366;fillColor=#d5e8d4;strokeWidth=1;verticalAlign=top;fontStyle=1;fontSize=12;fontColor=#82b366;" vertex="1" parent="1"><mxGeometry x="140" y="320" width="920" height="360" as="geometry"/></mxCell>
        <mxCell id="svc_frontend" value="frontend-svc" style="shape=mxgraph.kubernetes.svc;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="280" y="360" width="80" height="60" as="geometry"/></mxCell>
        <mxCell id="deploy_frontend" value="frontend" style="shape=mxgraph.kubernetes.deploy;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="280" y="460" width="80" height="70" as="geometry"/></mxCell>
        <mxCell id="pod_fe1" value="" style="shape=mxgraph.kubernetes.pod;fillColor=#326CE5;strokeColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="240" y="560" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="pod_fe2" value="" style="shape=mxgraph.kubernetes.pod;fillColor=#326CE5;strokeColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="300" y="560" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="svc_api" value="api-svc" style="shape=mxgraph.kubernetes.svc;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="560" y="360" width="80" height="60" as="geometry"/></mxCell>
        <mxCell id="deploy_api" value="api-server" style="shape=mxgraph.kubernetes.deploy;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="560" y="460" width="80" height="70" as="geometry"/></mxCell>
        <mxCell id="pod_api1" value="" style="shape=mxgraph.kubernetes.pod;fillColor=#326CE5;strokeColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="520" y="560" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="pod_api2" value="" style="shape=mxgraph.kubernetes.pod;fillColor=#326CE5;strokeColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="580" y="560" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="pod_api3" value="" style="shape=mxgraph.kubernetes.pod;fillColor=#326CE5;strokeColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="640" y="560" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="svc_db" value="postgres-svc" style="shape=mxgraph.kubernetes.svc;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="840" y="360" width="80" height="60" as="geometry"/></mxCell>
        <mxCell id="sts_db" value="postgres" style="shape=mxgraph.kubernetes.sts;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="840" y="460" width="80" height="70" as="geometry"/></mxCell>
        <mxCell id="pod_db" value="" style="shape=mxgraph.kubernetes.pod;fillColor=#326CE5;strokeColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="860" y="560" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="pvc" value="data-pvc" style="shape=mxgraph.kubernetes.pvc;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="960" y="560" width="70" height="50" as="geometry"/></mxCell>
        <mxCell id="cm" value="app-config" style="shape=mxgraph.kubernetes.cm;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="160" y="460" width="60" height="50" as="geometry"/></mxCell>
        <mxCell id="secret" value="db-secret" style="shape=mxgraph.kubernetes.secret;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="720" y="460" width="60" height="50" as="geometry"/></mxCell>
        <mxCell id="hpa" value="api-hpa" style="shape=mxgraph.kubernetes.hpa;fillColor=#326CE5;strokeColor=#ffffff;verticalLabelPosition=bottom;verticalAlign=top;fontSize=11;" vertex="1" parent="1"><mxGeometry x="460" y="460" width="80" height="50" as="geometry"/></mxCell>
        <mxCell id="e1" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="users" target="ingress"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="ingress" target="svc_frontend"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="ingress" target="svc_api"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="svc_frontend" target="deploy_frontend"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="svc_api" target="deploy_api"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;" edge="1" parent="1" source="svc_db" target="sts_db"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;dashed=1;" edge="1" parent="1" source="deploy_api" target="svc_db"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=2;dashed=1;" edge="1" parent="1" source="deploy_frontend" target="svc_api"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=1;dashed=1;" edge="1" parent="1" source="pod_db" target="pvc"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e10" style="edgeStyle=orthogonalEdgeStyle;rounded=1;strokeColor=#666666;strokeWidth=1;dashed=1;" edge="1" parent="1" source="hpa" target="deploy_api"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/kubernetes.md`:

| Component | Stencil |
|-----------|---------|
| User | `mxgraph.kubernetes.user` |
| Ingress | `mxgraph.kubernetes.ing` |
| Service | `mxgraph.kubernetes.svc` |
| Deployment | `mxgraph.kubernetes.deploy` |
| StatefulSet | `mxgraph.kubernetes.sts` |
| Pod | `mxgraph.kubernetes.pod` |
| ConfigMap | `mxgraph.kubernetes.cm` |
| Secret | `mxgraph.kubernetes.secret` |
| PVC | `mxgraph.kubernetes.pvc` |
| HPA | `mxgraph.kubernetes.hpa` |

## Kubernetes Color

Standard Kubernetes blue: `fillColor=#326CE5;strokeColor=#ffffff;`
