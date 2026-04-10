---
name: uml
description: Create UML (Unified Modeling Language) diagrams using PlantUML syntax. Best for software modeling including Class, Sequence, Activity, State Machine, Component, Use Case, and Deployment diagrams. Uses concise text-based notation that auto-layouts. NOT for simple flowcharts (use mermaid), layered system architecture (use architecture), or data charts (use vega).
metadata:
  author: UML diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# UML Diagram Generator
**Quick Start:** Choose diagram type → Write PlantUML text → Define elements and relationships → Wrap in ` ```plantuml ` fence.
> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use standard PlantUML keywords: `class`, `interface`, `abstract`, `enum`, `actor`, `participant`, `component`, `node`, `database`, `package`
- Relationships use arrow syntax: `-->`, `<|--`, `*--`, `o--`, `..>`, `..|>`
- Use `skinparam` for global styling and colors
- Use `#color` on individual elements for specific colors
- Notes use `note left of`, `note right of`, `note over`, or standalone `note "text" as N`

## UML Diagram Types
| Type | Purpose | Key Syntax | Example |
|------|---------|------------|---------|
| Class | Class structure and relationships | `class`, `interface`, `<\|--` | [class-diagram.md](examples/class-diagram.md) |
| Sequence | Message interactions over time | `participant`, `->`, `-->` | [sequence-diagram.md](examples/sequence-diagram.md) |
| Activity | Workflow and process flow | `start`, `:action;`, `if/else` | [activity-diagram.md](examples/activity-diagram.md) |
| Swimlane Activity | Multi-role activity with swimlanes | `\|Lane\|`, `:action;` | [swimlane-activity-diagram.md](examples/swimlane-activity-diagram.md) |
| State Machine | Object lifecycle states | `state`, `[*] -->` | [state-machine-diagram.md](examples/state-machine-diagram.md) |
| Component | System component organization | `component`, `[name]`, `interface` | [component-diagram.md](examples/component-diagram.md) |
| Use Case | User-system interactions | `actor`, `usecase`, `(name)` | [use-case-diagram.md](examples/use-case-diagram.md) |
| Deployment | Physical deployment architecture | `node`, `artifact`, `database` | [deployment-diagram.md](examples/deployment-diagram.md) |
| Object | Runtime object snapshot | `object "name" as id` | [object-diagram.md](examples/object-diagram.md) |
| Package | Module organization | `package "name"` | [package-diagram.md](examples/package-diagram.md) |
| Communication | Object collaboration | Numbered messages with sequence syntax | [communication-diagram.md](examples/communication-diagram.md) |
| Composite Structure | Internal class structure | `component` with nested `port` | [composite-structure-diagram.md](examples/composite-structure-diagram.md) |
| Interaction Overview | Activity + sequence combination | `group`, `ref over` | [interaction-overview-diagram.md](examples/interaction-overview-diagram.md) |
| Profile | UML extension mechanisms | `<<stereotype>>` labels | [profile-diagram.md](examples/profile-diagram.md) |

## Mxgraph Stencil Icons

draw-uml supports 9500+ mxgraph stencil icons (AWS, Azure, Cisco, Kubernetes, etc.) via the `mxgraph.*` syntax. Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`.

**Full stencil reference:** See [stencils/README.md](stencils/README.md).

### Syntax

```
mxgraph.<namespace>.<icon> "Label" as <alias>
mxgraph.<namespace>.<icon> "Label" as <alias> #color
mxgraph.<namespace>.<icon> <alias>
```

- `mxgraph.<namespace>.<icon>` — the stencil shape key (e.g. `mxgraph.aws4.lambda`, `mxgraph.kubernetes.pod`)
- `"Label"` — display text (quoted if contains spaces, unquoted for single word)
- `as <alias>` — identifier for use in relationships
- `#color` — optional override color (e.g. `#FF6600`, `#LightBlue`)

### Examples

```plantuml
@startuml
' Simple icon declaration
mxgraph.aws4.lambda "Lambda\nFunction" as fn
mxgraph.aws4.api_gateway "API GW" as gw
mxgraph.aws4.dynamodb "DynamoDB" as db

gw --> fn
fn --> db
@enduml
```

```plantuml
@startuml
' Kubernetes architecture with icons
mxgraph.kubernetes.ing "Ingress" as ing
mxgraph.kubernetes.svc "Service" as svc
mxgraph.kubernetes.pod "Pod" as pod
mxgraph.kubernetes.deploy "Deployment" as deploy

ing --> svc
svc --> pod
deploy --> pod
@enduml
```

```plantuml
@startuml
' Mixing standard UML with stencil icons
node "Cloud" {
  mxgraph.aws4.ec2 "EC2" as ec2
  mxgraph.aws4.rds "RDS" as rds
}
database "Legacy DB" as legacy

ec2 --> rds
rds --> legacy
@enduml
```
