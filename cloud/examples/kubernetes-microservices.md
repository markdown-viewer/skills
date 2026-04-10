# Kubernetes Microservices Architecture

Microservices on Kubernetes with Ingress, Services, Deployments, StatefulSet, HPA, and persistent storage.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Ingress | `mxgraph.kubernetes.ing` |
| Service | `mxgraph.kubernetes.svc` |
| Deployment | `mxgraph.kubernetes.deploy` |
| StatefulSet | `mxgraph.kubernetes.sts` |
| Pod | `mxgraph.kubernetes.pod` |
| HPA | `mxgraph.kubernetes.hpa` |
| ConfigMap | `mxgraph.kubernetes.cm` |
| Secret | `mxgraph.kubernetes.secret` |
| PVC | `mxgraph.kubernetes.pvc` |
| User | `mxgraph.kubernetes.user` |

## Example

```plantuml
@startuml
left to right direction

mxgraph.kubernetes.user "User" as user

rectangle "Kubernetes Cluster" {
  rectangle "namespace: production" {
    mxgraph.kubernetes.ing "Ingress" as ingress

    mxgraph.kubernetes.svc "api-svc" as svc_api
    mxgraph.kubernetes.svc "web-svc" as svc_web
    mxgraph.kubernetes.svc "db-svc" as svc_db

    mxgraph.kubernetes.deploy "api-deploy" as dep_api
    mxgraph.kubernetes.deploy "web-deploy" as dep_web
    mxgraph.kubernetes.hpa "HPA" as hpa

    mxgraph.kubernetes.pod "api-1" as pod_api1
    mxgraph.kubernetes.pod "api-2" as pod_api2
    mxgraph.kubernetes.pod "web-1" as pod_web1
    mxgraph.kubernetes.pod "web-2" as pod_web2

    mxgraph.kubernetes.sts "db-statefulset" as sts_db
    mxgraph.kubernetes.pod "db-0" as pod_db
    mxgraph.kubernetes.pvc "db-pvc" as pvc

    mxgraph.kubernetes.cm "app-config" as cm
    mxgraph.kubernetes.secret "db-secret" as sec
  }
}

' Ingress routing
user --> ingress
ingress --> svc_api
ingress --> svc_web

' Stateless workloads
svc_api --> dep_api
svc_web --> dep_web
dep_api --> pod_api1
dep_api --> pod_api2
dep_web --> pod_web1
dep_web --> pod_web2
hpa ..> dep_api : scale

' Stateful workload
pod_api1 --> svc_db
svc_db --> sts_db
sts_db --> pod_db
pod_db --> pvc

' Config injection
cm ..> dep_api
cm ..> dep_web
sec ..> sts_db
@enduml
```

## Pattern Notes

1. **K8s stencils**: `mxgraph.kubernetes.<name>` — all stencils auto-colored in K8s blue
2. **Cluster + Namespace**: Nested rectangles for cluster boundary and namespace isolation
3. **Flow left→right**: User → Ingress → Service → Deployment → Pods; StatefulSet → Pod → PVC for stateful workloads
4. **Config injection**: `..>` dashed links from ConfigMap/Secret to Deployments/StatefulSets

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Job | `mxgraph.kubernetes.job` | Batch job execution |
| CronJob | `mxgraph.kubernetes.cronjob` | Scheduled tasks |
| DaemonSet | `mxgraph.kubernetes.ds` | Per-node daemon pods |
| Namespace | `mxgraph.kubernetes.ns` | Namespace boundary |
| NetworkPolicy | `mxgraph.kubernetes.netpol` | Network access rules |
| ServiceAccount | `mxgraph.kubernetes.sa` | Pod identity / RBAC |
