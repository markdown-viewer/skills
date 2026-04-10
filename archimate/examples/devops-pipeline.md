# DevOps Pipeline

CI/CD delivery pipeline modeled with ArchiMate: from code commit through build, test, deploy to production.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Business | `Business_Process`, `Business_Event` |
| Application | `Application_Component`, `Application_Service`, `Application_Function` |
| Technology | `Technology_Node`, `Technology_SystemSoftware`, `Technology_Artifact` |

## Example

GitOps pipeline: commit → build → test → stage → prod with approval gate and monitoring:

```plantuml
@startuml
!include <archimate/Archimate>
left to right direction

Business_Event(commit, "Code Commit")

rectangle "CI Pipeline" {
  Application_Function(build, "Build & Compile")
  Application_Function(unitTest, "Unit Tests")
  Application_Function(scan, "Security Scan")
  Application_Function(package, "Package Image")
  Technology_Artifact(image, "Container Image")
}

rectangle "CD Pipeline" {
  Application_Function(deploySt, "Deploy to Staging")
  Application_Function(intTest, "Integration Tests")
  Business_Process(approval, "Release Approval")
  Application_Function(deployPr, "Deploy to Prod")
}

rectangle "Infrastructure" {
  Technology_Node(staging, "Staging Cluster")
  Technology_Node(prod, "Production Cluster")
  Technology_SystemSoftware(k8s, "Kubernetes")
  Technology_SystemSoftware(registry, "Container Registry")
}

rectangle "Observability" {
  Application_Component(monitor, "Monitoring")
  Application_Component(logging, "Log Aggregation")
  Application_Component(alerting, "Alerting")
}

Rel_Triggering(commit, build, "")
Rel_Triggering(build, unitTest, "")
Rel_Triggering(unitTest, scan, "")
Rel_Triggering(scan, package, "")
Rel_Realization(package, image, "produces")

Rel_Triggering(image, deploySt, "")
Rel_Triggering(deploySt, intTest, "")
Rel_Triggering(intTest, approval, "")
Rel_Triggering(approval, deployPr, "")

Rel_Assignment(staging, deploySt, "")
Rel_Assignment(prod, deployPr, "")
Rel_Assignment(k8s, staging, "")
Rel_Assignment(k8s, prod, "")
Rel_Serving(registry, package, "stores")

Rel_Serving(monitor, prod, "observes")
Rel_Serving(logging, prod, "collects")
Rel_Triggering(monitor, alerting, "triggers")
@enduml
```

## Pattern Notes

1. **Left-to-right flow** — `left to right direction` for natural pipeline reading: commit → build → test → deploy
2. **Triggering chain** — `Rel_Triggering` creates the sequential pipeline stages; each stage triggers the next
3. **Artifact** — `Technology_Artifact` for the container image produced by the package stage
4. **Business Process gate** — `Business_Process` for release approval (human decision point in the automated pipeline)
5. **Dual environments** — Staging and Production as separate `Technology_Node`, both assigned to Kubernetes
6. **Observability** — Monitoring, Logging, Alerting as `Application_Component` serving the production cluster
7. **Mixed layers** — Business events trigger application functions running on technology nodes — proper ArchiMate cross-layer modeling
