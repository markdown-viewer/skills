# IBM Cloud Kubernetes Architecture

Containerized microservices on IBM Cloud Kubernetes Service with VPC, load balancer, registry, and PostgreSQL.

## Key Elements

| Component | Stencil |
|-----------|---------|
| K8s Service | `mxgraph.ibm_cloud.ibm-cloud--kubernetes-service` |
| App LB | `mxgraph.ibm_cloud.load-balancer--application` |
| Container Registry | `mxgraph.ibm_cloud.cloud-registry` |
| Virtual Server | `mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc` |
| PostgreSQL | `mxgraph.ibm_cloud.database--postgresql` |
| User | `mxgraph.ibm_cloud.user` |

## Example

```plantuml
@startuml
left to right direction

mxgraph.ibm_cloud.user "User" as user

cloud "IBM Cloud" {
  rectangle "VPC" {
    rectangle "Zone 1" {
      rectangle "Public Subnet" {
        mxgraph.ibm_cloud.load-balancer--application "App LB" as lb
      }

      rectangle "Private Subnet" {
        mxgraph.ibm_cloud.ibm-cloud--kubernetes-service "Kubernetes\nService" as k8s
        mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc "Worker 1" as w1
        mxgraph.ibm_cloud.ibm-cloud--virtual-server-vpc "Worker 2" as w2
        mxgraph.ibm_cloud.cloud-registry "Container\nRegistry" as reg
        mxgraph.ibm_cloud.database--postgresql "PostgreSQL" as db
      }
    }
  }
}

user --> lb
lb --> k8s
k8s --> w1
k8s --> w2
k8s --> reg
w1 --> db
w2 --> db
@enduml
```

## Pattern Notes

1. **IBM Cloud stencils**: `mxgraph.ibm_cloud.<name>` — use hyphenated names (e.g. `ibm-cloud--kubernetes-service`)
2. **Container hierarchy**: IBM Cloud → VPC → Zone → Public/Private Subnet
3. **No tag stencils needed**: PlantUML containers handle zone/subnet labeling automatically
4. **Worker nodes**: K8s Service manages Worker VMs, which connect to shared PostgreSQL

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Secrets Manager | `mxgraph.ibm_cloud.ibm-cloud--secrets-manager` | Secret management |
| Logging | `mxgraph.ibm_cloud.ibm-cloud--logging` | Centralized logging |
| Monitoring | `mxgraph.ibm_cloud.cloud--monitoring` | Observability |
| Key Protect | `mxgraph.ibm_cloud.ibm-cloud--key-protect` | Encryption key mgmt |
| Transit Gateway | `mxgraph.ibm_cloud.ibm-cloud--transit-gateway` | Network connectivity |
| Object Storage | `mxgraph.ibm_cloud.object-storage` | Blob/object storage |
