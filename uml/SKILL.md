---
name: uml
description: Create UML (Unified Modeling Language) diagrams using drawio XML format. Best for software modeling including Class, Sequence, Activity, State Machine, Component, Use Case, and Deployment diagrams. Built on drawio with UML-specific shapes and notation. NOT for simple flowcharts (use mermaid), layered system architecture (use architecture), or data charts (use vega).
author: UML diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# UML Diagram Generator
**Quick Start:** Choose diagram type → Define classes/objects/actors → Add relationships/edges → Use appropriate shapes and arrow styles → Wrap in ` ```drawio ` fence.
> ⚠️ **IMPORTANT:** Always use ` ```drawio ` code fence. NEVER use ` ```xml ` — it will NOT render as a diagram.

## Critical Rules

> 🔗 **This is a drawio-derived skill.** All structure, layout, and edge routing rules inherit from [drawio SKILL.md](../drawio/SKILL.md). Read the base rules first.

**UML-specific additions:**
- Use standard UML shapes: `shape=umlLifeline`, `shape=umlActor`, `shape=component`, `swimlane;childLayout=stackLayout`
- Use `fillColor=none;` for package/component containers to avoid covering child elements

## UML Diagram Types
| Type | Purpose | Key Shape | Example |
|------|---------|-----------|---------|
| Class | Class structure and relationships | `swimlane;childLayout=stackLayout` | [class-diagram.md](examples/class-diagram.md) |
| Sequence | Message interactions over time | `shape=umlLifeline` | [sequence-diagram.md](examples/sequence-diagram.md) |
| Activity | Workflow and process flow | `rounded=1;arcSize=50` | [activity-diagram.md](examples/activity-diagram.md) |
| State Machine | Object lifecycle states | `rounded=1` with colors | [state-machine-diagram.md](examples/state-machine-diagram.md) |
| Component | System component organization | `shape=component` | [component-diagram.md](examples/component-diagram.md) |
| Use Case | User-system interactions | `shape=umlActor`, `ellipse` | [use-case-diagram.md](examples/use-case-diagram.md) |
| Deployment | Physical deployment architecture | `shape=cube;direction=south` | [deployment-diagram.md](examples/deployment-diagram.md) |
| Object | Runtime object snapshot | `swimlane;fontStyle=4` | [object-diagram.md](examples/object-diagram.md) |
| Package | Module organization | `shape=folder` | [package-diagram.md](examples/package-diagram.md) |
| Communication | Object collaboration | `whiteSpace=wrap` with numbered messages | [communication-diagram.md](examples/communication-diagram.md) |
| Composite Structure | Internal class structure | `shape=ellipse;container=1;dashed=1` | [composite-structure-diagram.md](examples/composite-structure-diagram.md) |
| Interaction Overview | Activity + sequence combination | `shape=umlFrame` | [interaction-overview-diagram.md](examples/interaction-overview-diagram.md) |
| Timing | State changes over time | `shape=waypoint` | [timing-diagram.md](examples/timing-diagram.md) |
| Profile | UML extension mechanisms | `<<stereotype>>` labels | [profile-diagram.md](examples/profile-diagram.md) |
