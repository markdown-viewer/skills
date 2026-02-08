# Kubernetes Microservices Architecture

Microservices on Kubernetes with Ingress, Services, Deployments, StatefulSet, HPA, and persistent storage.

## Key Elements

| Component | Stencil | Size | Notes |
|-----------|---------|------|-------|
| Cluster | container `rounded=1` | — | Blue border `#326CE5`, label top |
| Namespace | container `dashed=1` | — | Gray border, `fillColor=none` |
| Ingress | `mxgraph.kubernetes.ing` | 50×46 | `fillColor=#326CE5` |
| Service | `mxgraph.kubernetes.svc` | 50×38 | `fillColor=#326CE5` |
| Deployment | `mxgraph.kubernetes.deploy` | 50×42 | `fillColor=#326CE5` |
| StatefulSet | `mxgraph.kubernetes.sts` | 50×41 | `fillColor=#326CE5` |
| Pod | `mxgraph.kubernetes.pod` | 32×32 | `fillColor=#326CE5` |
| HPA | `mxgraph.kubernetes.hpa` | 50×29 | `fillColor=#326CE5` |
| ConfigMap | `mxgraph.kubernetes.cm` | 40×35 | `fillColor=#326CE5` |
| Secret | `mxgraph.kubernetes.secret` | 40×36 | `fillColor=#326CE5` |
| PVC | `mxgraph.kubernetes.pvc` | 40×24 | `fillColor=#326CE5` |
| User | `mxgraph.kubernetes.user` | 45×45 | `fillColor=#326CE5` |

**Icon pattern:** `shape=mxgraph.kubernetes.<name>;fillColor=#326CE5` with `verticalLabelPosition=bottom;verticalAlign=top` for labels below. All stencils only require `fillColor`.

## Example

```drawio
<mxfile><diagram id="k8s-micro" name="K8s Microservices"><mxGraphModel dx="1100" dy="720" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="720" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="cluster" value="Kubernetes Cluster" style="rounded=1;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;fillColor=none;strokeColor=#326CE5;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;spacingTop=5;fontSize=14;fontStyle=1;fontColor=#326CE5;arcSize=8;" vertex="1" parent="1"><mxGeometry x="170" y="40" width="890" height="640" as="geometry"/></mxCell>
  <mxCell id="ns" value="namespace: production" style="rounded=0;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;fillColor=none;strokeColor=#999999;strokeWidth=1;dashed=1;dashPattern=4 4;verticalAlign=top;align=left;spacingLeft=10;spacingTop=5;fontSize=12;fontColor=#999999;" vertex="1" parent="cluster"><mxGeometry x="20" y="40" width="850" height="580" as="geometry"/></mxCell>
  <mxCell id="ingress" value="Ingress" style="shape=mxgraph.kubernetes.ing;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="30" y="60" width="50" height="46" as="geometry"/></mxCell>
  <mxCell id="svc-api" value="api-svc" style="shape=mxgraph.kubernetes.svc;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="180" y="40" width="50" height="38" as="geometry"/></mxCell>
  <mxCell id="svc-web" value="web-svc" style="shape=mxgraph.kubernetes.svc;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="180" y="140" width="50" height="38" as="geometry"/></mxCell>
  <mxCell id="deploy-api" value="api-deploy" style="shape=mxgraph.kubernetes.deploy;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="350" y="35" width="50" height="42" as="geometry"/></mxCell>
  <mxCell id="deploy-web" value="web-deploy" style="shape=mxgraph.kubernetes.deploy;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="350" y="138" width="50" height="42" as="geometry"/></mxCell>
  <mxCell id="hpa-api" value="HPA" style="shape=mxgraph.kubernetes.hpa;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="350" y="105" width="50" height="29" as="geometry"/></mxCell>
  <mxCell id="pod-api1" value="api-1" style="shape=mxgraph.kubernetes.pod;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="510" y="25" width="32" height="32" as="geometry"/></mxCell>
  <mxCell id="pod-api2" value="api-2" style="shape=mxgraph.kubernetes.pod;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="510" y="85" width="32" height="32" as="geometry"/></mxCell>
  <mxCell id="pod-web1" value="web-1" style="shape=mxgraph.kubernetes.pod;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="510" y="145" width="32" height="32" as="geometry"/></mxCell>
  <mxCell id="pod-web2" value="web-2" style="shape=mxgraph.kubernetes.pod;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="510" y="205" width="32" height="32" as="geometry"/></mxCell>
  <mxCell id="svc-db" value="db-svc" style="shape=mxgraph.kubernetes.svc;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="350" y="290" width="50" height="38" as="geometry"/></mxCell>
  <mxCell id="sts-db" value="db-statefulset" style="shape=mxgraph.kubernetes.sts;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=11;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="510" y="288" width="50" height="41" as="geometry"/></mxCell>
  <mxCell id="pod-db" value="db-0" style="shape=mxgraph.kubernetes.pod;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="650" y="295" width="32" height="32" as="geometry"/></mxCell>
  <mxCell id="pvc" value="db-pvc" style="shape=mxgraph.kubernetes.pvc;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="740" y="297" width="40" height="24" as="geometry"/></mxCell>
  <mxCell id="cm" value="app-config" style="shape=mxgraph.kubernetes.cm;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="350" y="430" width="40" height="35" as="geometry"/></mxCell>
  <mxCell id="sec" value="db-secret" style="shape=mxgraph.kubernetes.secret;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=10;fontColor=#326CE5;" vertex="1" parent="ns"><mxGeometry x="510" y="430" width="40" height="36" as="geometry"/></mxCell>
  <mxCell id="user" value="User" style="shape=mxgraph.kubernetes.user;html=1;fillColor=#326CE5;verticalLabelPosition=bottom;verticalAlign=top;align=center;fontSize=12;fontColor=#326CE5;" vertex="1" parent="1"><mxGeometry x="50" y="148" width="45" height="45" as="geometry"/></mxCell>
  <mxCell id="e-user-ing" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#326CE5;" edge="1" parent="1" source="user" target="ingress"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-ing-svc1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=1;exitY=0.25;entryX=0;entryY=0.5;" edge="1" parent="ns" source="ingress" target="svc-api"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-ing-svc2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=1;exitY=0.75;entryX=0;entryY=0.5;" edge="1" parent="ns" source="ingress" target="svc-web"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-svc1-dep1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;" edge="1" parent="ns" source="svc-api" target="deploy-api"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-svc2-dep2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;" edge="1" parent="ns" source="svc-web" target="deploy-web"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-dep1-pod1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=1;exitY=0.25;entryX=0;entryY=0.5;" edge="1" parent="ns" source="deploy-api" target="pod-api1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-dep1-pod2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=1;exitY=0.75;entryX=0;entryY=0.5;" edge="1" parent="ns" source="deploy-api" target="pod-api2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-dep2-pod3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=1;exitY=0.25;entryX=0;entryY=0.5;" edge="1" parent="ns" source="deploy-web" target="pod-web1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-dep2-pod4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=1;exitY=0.75;entryX=0;entryY=0.5;" edge="1" parent="ns" source="deploy-web" target="pod-web2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-hpa" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;dashed=1;" edge="1" parent="ns" source="hpa-api" target="deploy-api"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-pod-db" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;exitX=0.5;exitY=1;entryX=0;entryY=0.5;" edge="1" parent="ns" source="pod-api1" target="svc-db"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="526" y="309"/></Array></mxGeometry></mxCell>
  <mxCell id="e-svcdb-sts" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;" edge="1" parent="ns" source="svc-db" target="sts-db"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-sts-pod" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;" edge="1" parent="ns" source="sts-db" target="pod-db"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-pod-pvc" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#326CE5;" edge="1" parent="ns" source="pod-db" target="pvc"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-cm-dep1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#999999;dashed=1;exitX=0.5;exitY=0;entryX=0.5;entryY=1;" edge="1" parent="ns" source="cm" target="deploy-api"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-cm-dep2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#999999;dashed=1;exitX=0.5;exitY=0;entryX=0.5;entryY=1;" edge="1" parent="ns" source="cm" target="deploy-web"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="370" y="400"/><mxPoint x="375" y="400"/></Array></mxGeometry></mxCell>
  <mxCell id="e-sec-sts" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=1;strokeColor=#999999;dashed=1;exitX=0.5;exitY=0;entryX=0.5;entryY=1;" edge="1" parent="ns" source="sec" target="sts-db"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. K8s stencils use `shape=mxgraph.kubernetes.<name>` with `fillColor=#326CE5` (K8s blue). All 40 stencils only need `fillColor`
2. Cluster boundary: `rounded=1;strokeColor=#326CE5;strokeWidth=2;container=1`. Namespace: `dashed=1;strokeColor=#999999`
3. Labels below icons: `verticalLabelPosition=bottom;verticalAlign=top`. Config resources (ConfigMap/Secret) connect with dashed gray lines
4. Flow left→right: User → Ingress → Service → Deployment → Pods. StatefulSet → Pod → PVC for stateful workloads
