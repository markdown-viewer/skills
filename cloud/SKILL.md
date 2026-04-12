---
name: cloud
description: Create cloud architecture diagrams using PlantUML syntax with official cloud provider stencil icons. Best for AWS, Azure, GCP, Alibaba Cloud architecture diagrams with proper service icons and auto-layout. NOT for general software modeling (use uml) or network topology without cloud services (use network skill).
metadata:
  author: Cloud diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Cloud Architecture Diagram Generator

**Quick Start:** Choose cloud provider → Declare stencil icons → Group into VPC/region zones → Connect with arrow syntax → Wrap in ` ```plantuml ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use `left to right direction` for typical cloud architectures (data flows left→right)
- Use `mxgraph.*` stencil syntax for cloud service icons
- Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`
- Use `rectangle "VPC" { ... }` or `package "Region" { ... }` for cloud containers
- Use `cloud "Name" { ... }` for cloud boundary shapes
- Directed flows use `-->`, async/event-driven flows use `..>` (dashed)

**Full stencil reference:** See [stencils/README.md](../uml/stencils/README.md) for 9500+ available icons.

## Mxgraph Stencil Syntax

```
mxgraph.<provider>.<icon> "Label" as <alias>
```

### Common Cloud Stencil Families

| Family | Prefix | Typical Icons |
|--------|--------|---------------|
| AWS | `mxgraph.aws4.*` | `lambda_function`, `ec2`, `rds_instance`, `s3`, `api_gateway`, `cloudfront`, `dynamodb` |
| Azure | `mxgraph.azure.*` | `virtual_machine`, `azure_load_balancer`, `sql_database`, `azure_active_directory`, `storage` |
| GCP | `mxgraph.gcp2.*` | `compute_engine_2`, `cloud`, `process`, `repository`, `cloud_monitoring` |
| Alibaba | `mxgraph.alibaba_cloud.*` | `ecs_elastic_compute_service`, `slb_server_load_balancer_01`, `polardb`, `oss_object_storage_service` |
| IBM | `mxgraph.ibm_cloud.*` | `ibm-cloud--kubernetes-service`, `load-balancer--application`, `database--postgresql` |
| Kubernetes | `mxgraph.kubernetes.*` | `pod`, `svc`, `deploy`, `ing`, `sts`, `pvc`, `cm`, `secret` |
| OpenStack | `mxgraph.openstack.*` | `nova_server`, `neutron_router`, `cinder_volume`, `swift_container` |

### Connection Types

| Syntax | Meaning | Use Case |
|--------|---------|----------|
| `A --> B` | Solid arrow | Sync API call / data flow |
| `A ..> B` | Dashed arrow | Async event / trigger / replication |
| `A -- B` | Solid line, no arrow | Physical / bidirectional link |
| `A --> B : "label"` | Labeled connection | Describe the data flow |

### Quick Example

```plantuml
@startuml
left to right direction
mxgraph.aws4.users "Users" as users
mxgraph.aws4.cloudfront "CloudFront" as cf
mxgraph.aws4.application_load_balancer "ALB" as alb

rectangle "VPC" {
  mxgraph.aws4.ec2 "EC2" as ec2
  mxgraph.aws4.rds_instance "RDS" as rds
}

users --> cf
cf --> alb
alb --> ec2
ec2 --> rds
@enduml
```

## Cloud Architecture Types

| Type | Purpose | Key Stencils | Example |
|------|---------|--------------|---------|
| AWS | Amazon Web Services | `mxgraph.aws4.*` | [aws-basic.md](examples/aws-basic.md) |
| AWS Serverless | Event-driven serverless | `mxgraph.aws4.*` | [aws-serverless.md](examples/aws-serverless.md) |
| Azure | Microsoft Azure | `mxgraph.azure.*` | [azure-hybrid-network.md](examples/azure-hybrid-network.md) |
| GCP | Google Cloud Platform | `mxgraph.gcp2.*` | [gcp-log-processing.md](examples/gcp-log-processing.md) |
| Alibaba Cloud | Alibaba Cloud | `mxgraph.alibaba_cloud.*` | [alibaba-web-app.md](examples/alibaba-web-app.md) |
| IBM Cloud | IBM Cloud | `mxgraph.ibm_cloud.*` | [ibm-kubernetes.md](examples/ibm-kubernetes.md) |
| Kubernetes | Container orchestration | `mxgraph.kubernetes.*` | [kubernetes-microservices.md](examples/kubernetes-microservices.md) |
| OpenStack | Private cloud | `mxgraph.openstack.*` | [openstack-basic.md](examples/openstack-basic.md) |
