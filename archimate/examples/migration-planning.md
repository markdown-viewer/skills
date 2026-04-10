# Migration Planning

Plateau-based migration roadmap: baseline → intermediate → target architecture with work packages and gaps.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Implementation | `Implementation_Plateau`, `Implementation_Gap`, `Implementation_WorkPackage`, `Implementation_Deliverable` |
| Application | `Application_Component` |

## Example

Legacy ERP migration: monolith → microservices over three plateaus with identified gaps:

```plantuml
@startuml
!include <archimate/Archimate>
left to right direction

rectangle "Baseline (Current)" {
  Implementation_Plateau(p0, "Plateau 0\nCurrent State")
  Application_Component(mono, "Monolithic ERP")
  Application_Component(legacyDB, "Oracle DB")
}

rectangle "Phase 1 — Strangler Fig" {
  Implementation_Plateau(p1, "Plateau 1\nQ2 2026")
  Implementation_WorkPackage(wp1, "Extract Order Module")
  Implementation_WorkPackage(wp2, "Setup API Gateway")
  Implementation_Deliverable(d1, "Order Microservice")
  Implementation_Deliverable(d2, "API Gateway Config")
  Application_Component(orderSvc, "Order Service")
  Application_Component(apiGw, "API Gateway")
}

rectangle "Phase 2 — Data Migration" {
  Implementation_Plateau(p2, "Plateau 2\nQ4 2026")
  Implementation_WorkPackage(wp3, "Migrate Order Data")
  Implementation_WorkPackage(wp4, "Extract Inventory Module")
  Implementation_Deliverable(d3, "PostgreSQL Cluster")
  Application_Component(invSvc, "Inventory Service")
}

rectangle "Target Architecture" {
  Implementation_Plateau(p3, "Plateau 3\nQ2 2027")
  Application_Component(allSvc, "Full Microservices")
  Implementation_Deliverable(d4, "Decommission Plan")
}

Implementation_Gap(gap1, "API compatibility gap")
Implementation_Gap(gap2, "Data sync during migration")
Implementation_Gap(gap3, "Legacy decommission risk")

Rel_Triggering(p0, p1, "")
Rel_Triggering(p1, p2, "")
Rel_Triggering(p2, p3, "")

Rel_Composition(p1, wp1, "")
Rel_Composition(p1, wp2, "")
Rel_Realization(wp1, d1, "")
Rel_Realization(wp2, d2, "")

Rel_Composition(p2, wp3, "")
Rel_Composition(p2, wp4, "")
Rel_Realization(wp3, d3, "")

Rel_Association(gap1, p1, "")
Rel_Association(gap2, p2, "")
Rel_Association(gap3, p3, "")
@enduml
```

## Pattern Notes

1. **Plateau sequence** — `Implementation_Plateau` represents architecture states at specific milestones; `Rel_Triggering` chains them in order
2. **Work Packages** — `Implementation_WorkPackage` are the actionable tasks within each plateau; `Rel_Composition` groups them under the plateau
3. **Deliverables** — `Implementation_Deliverable` are the outputs of work packages; `Rel_Realization` links work → deliverable
4. **Gaps** — `Implementation_Gap` identifies risks and incompatibilities between plateaus
5. **Left-to-right** — `left to right direction` reads the timeline naturally: Baseline → Phase 1 → Phase 2 → Target
6. **Mixed layers** — Application Components appear alongside Implementation elements to show what changes at each phase
