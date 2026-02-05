---
name: uml
description: Create UML (Unified Modeling Language) diagrams using Draw.io XML format. Best for software modeling including Class, Sequence, Activity, State Machine, Component, Use Case, and Deployment diagrams. Built on Draw.io with UML-specific shapes and notation. NOT for simple flowcharts (use mermaid), layered system architecture (use architecture), or data charts (use vega).
author: UML diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# UML Diagram Generator
**Quick Start:** Choose diagram type → Define classes/objects/actors → Add relationships/edges → Use appropriate shapes and arrow styles → Wrap in ` ```drawio ` fence.
> ⚠️ **IMPORTANT:** Always use ` ```drawio ` code fence. NEVER use ` ```xml ` — it will NOT render as a diagram.

## Critical Rules
### Rule 1: Device Stencils Require fillColor
Many device stencils have no default color. Always add `fillColor`/`strokeColor` to make them visible:
```
style="shape=mxgraph.sysml.package;html=1;fillColor=#036897;strokeColor=#ffffff;"
```
**Preset Color Palette:** Blue(`#dae8fc`,`#6c8ebf`) Green(`#d5e8d4`,`#82b366`) Orange(`#ffe6cc`,`#d79b00`) Red(`#f8cecc`,`#b85450`) Purple(`#e1d5e7`,`#9673a6`) Yellow(`#fff2cc`,`#d6b656`) Gray(`#f5f5f5`,`#666666`)

**Exception:** Edge/link stencils should NOT have `fillColor`/`strokeColor` — they are connectors, not shapes.

### Rule 2: Check Stencil Names Before Use
Before using stencils, check [stencils/README.md](../drawio/stencils/README.md) to find correct shape names. Use exact names like `mxgraph.sysml.package`.

### Rule 3: Root Cells Required
- `<mxCell id="0"/>` — Root cell (required)
- `<mxCell id="1" parent="0"/>` — Default parent (required)
- Missing root cells → Diagram won't render

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
| SysML | Systems engineering | `shape=mxgraph.sysml.package` | [sysml-bdd.md](examples/sysml-bdd.md) |
## Common Style Reference
- **Arrow Types:** Inheritance(`endArrow=block;endFill=0`) Implementation(`endArrow=block;endFill=0;dashed=1`) Association(`endArrow=open;endFill=1`) Dependency(`endArrow=open;dashed=1`) Aggregation(`startArrow=diamondThin;startFill=0`) Composition(`startArrow=diamondThin;startFill=1`)
- **Visibility Symbols:** `+`(public) `#`(protected) `-`(private) `~`(package) `/`(derived)
- **State Colors:** Pending(`#dae8fc`,`#6c8ebf`) Success(`#d5e8d4`,`#82b366`) Error(`#f8cecc`,`#b85450`) Warning(`#fff2cc`,`#d6b656`) Complete(`#e1d5e7`,`#9673a6`)
- **Shape Styles:** `rounded`(0,1) `fillColor`(hex) `strokeColor`(hex) `strokeWidth`(num) `dashed`(0,1) `opacity`(0-100) `fontColor`(hex) `fontSize`(num) `fontStyle`(0=normal,1=bold,2=italic,3=both) `align`(left,center,right) `verticalAlign`(top,middle,bottom)
- **Edge Styles:** `edgeStyle`(orthogonalEdgeStyle,entityRelationEdgeStyle,elbowEdgeStyle) `curved`(0,1) `endArrow`/`startArrow`(classic,block,open,oval,diamond,none) `endFill`/`startFill`(0=hollow,1=filled)
- **Preset Color Palette:** Blue(`#dae8fc`,`#6c8ebf`) Green(`#d5e8d4`,`#82b366`) Orange(`#ffe6cc`,`#d79b00`) Red(`#f8cecc`,`#b85450`) Purple(`#e1d5e7`,`#9673a6`) Yellow(`#fff2cc`,`#d6b656`) Gray(`#f5f5f5`,`#666666`)
## Draw.io XML Syntax Examples
### Example 1: Shape Definition (vertex)
```drawio
<mxfile><diagram name="Shape Example" id="shape-ex"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/><mxCell id="shape1" value="Label" style="rounded=1;whiteSpace=wrap;html=1;" parent="1" vertex="1"><mxGeometry x="100" y="100" width="120" height="60" as="geometry"/></mxCell></root></mxGraphModel></diagram></mxfile>
```
### Example 2: Edge Definition (edge)
```drawio
<mxfile><diagram name="Edge Example" id="edge-ex"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/><mxCell id="a" value="A" style="rounded=1;whiteSpace=wrap;html=1;" parent="1" vertex="1"><mxGeometry x="40" y="100" width="80" height="40" as="geometry"/></mxCell><mxCell id="b" value="B" style="rounded=1;whiteSpace=wrap;html=1;" parent="1" vertex="1"><mxGeometry x="200" y="100" width="80" height="40" as="geometry"/></mxCell><mxCell id="edge1" style="edgeStyle=orthogonalEdgeStyle;endArrow=classic;html=1;" parent="1" source="a" target="b" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell></root></mxGraphModel></diagram></mxfile>
```
