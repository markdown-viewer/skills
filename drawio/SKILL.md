---
name: drawio
description: General-purpose diagramming tool using Draw.io XML format with 8900+ stencils. Best for custom diagrams requiring pixel-perfect positioning, diagrams with vendor-specific icons (AWS, Azure, Cisco), or any diagram not covered by specialized skills. Use network skill for network topology, uml skill for UML diagrams, architecture skill for layered system views. NOT for simple flowcharts (use mermaid) or data-driven charts (use vega).
author: Draw.io is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Draw.io Diagram Generator
**Quick Start:** Create `<mxfile>` with `<diagram>` → Define `<mxGraphModel>` with grid settings → Add `<root>` with cells → Use `<mxCell>` for shapes and edges → Set geometry with `<mxGeometry>` → Wrap in ` ```drawio ` fence.
## Critical Rules
### Rule 1: Stencils Require fillColor
Many device stencils have no default color. Always add `fillColor`/`strokeColor` to make them visible:
```
style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;"
```
**Preset Color Palette:** Blue(`#dae8fc`,`#6c8ebf`) Green(`#d5e8d4`,`#82b366`) Orange(`#ffe6cc`,`#d79b00`) Red(`#f8cecc`,`#b85450`) Purple(`#e1d5e7`,`#9673a6`) Yellow(`#fff2cc`,`#d6b656`) Gray(`#f5f5f5`,`#666666`)
**Exception:** Edge/link stencils (e.g., `mxgraph.networks.comm_link`) should NOT have `fillColor`/`strokeColor` — they are connectors, not devices.
### Rule 2: Check Stencil Names Before Use
Before using stencils, check [stencils/README.md](stencils/README.md) to find correct shape names. Use exact names like `mxgraph.cisco.routers.router`.
### Rule 3: Root Cells Required
- `<mxCell id="0"/>` — Root cell (required)
- `<mxCell id="1" parent="0"/>` — Default parent (required)
- Missing root cells → Diagram won't render
### Rule 4: Device Stencil Labels Below
When adding labels to device stencils, place them below the stencil for better readability:
```
style="...;verticalLabelPosition=bottom;verticalAlign=top;labelPosition=center;align=center;"
```
## Common Shapes
### Basic Shapes
```drawio
<mxfile><diagram name="Basic Shapes" id="basic-shapes"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="rect" value="Box" style="rounded=0;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="20" y="20" width="100" height="50" as="geometry"/></mxCell>
  <mxCell id="rounded" value="Rounded" style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="140" y="20" width="100" height="50" as="geometry"/></mxCell>
  <mxCell id="circle" value="Circle" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="260" y="10" width="70" height="70" as="geometry"/></mxCell>
  <mxCell id="diamond" value="Decision" style="rhombus;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="350" y="10" width="70" height="70" as="geometry"/></mxCell>
  <mxCell id="db" value="Database" style="shape=cylinder;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="440" y="5" width="60" height="80" as="geometry"/></mxCell>
  <mxCell id="cloud" value="Cloud" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="520" y="10" width="100" height="70" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
### Container/Swimlane
```drawio
<mxfile><diagram name="Container Example" id="container-ex"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="container" value="Container" style="swimlane;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="40" y="40" width="200" height="150" as="geometry"/>
  </mxCell>
  <mxCell id="zone" value="Zone Name" style="whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=none;verticalAlign=top;fontSize=14;" vertex="1" parent="1"><mxGeometry x="280" y="40" width="200" height="150" as="geometry"/>
  </mxCell>
</root></mxGraphModel></diagram></mxfile>
```
## Stencil Libraries
Draw.io provides 8900+ pre-built stencils across 48 categories for professional diagrams. **Full stencil reference:** See [stencils/README.md](stencils/README.md).
| Category | Examples | Use Case |
|----------|----------|----------|
| **Cloud** | `aws4`, `azure`, `gcp2`, `alibaba_cloud`, `ibm_cloud` | Cloud architecture diagrams |
| **Network** | `cisco`, `cisco19`, `cisco_safe`, `networks`, `networks2` | Network topology |
| **Virtualization** | `citrix`, `citrix2`, `veeam`, `vvd`, `kubernetes` | Infrastructure diagrams |
| **Software** | `bpmn`, `flowchart`, `sitemap`, `mockup` | Process & UI design |
| **Hardware** | `rack`, `cabinets`, `electrical` | Data center & electrical |
| **Office** | `office`, `atlassian`, `salesforce` | Business diagrams |
```drawio
<mxfile><diagram name="Stencil Example" id="stencil-ex"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
<mxCell id="router" value="" style="shape=mxgraph.cisco.routers.router;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" vertex="1" parent="1"><mxGeometry x="100" y="100" width="78" height="53" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
## Common Style Reference
- **Arrow Types:** Inheritance(`endArrow=block;endFill=0`) Implementation(`endArrow=block;endFill=0;dashed=1`) Association(`endArrow=open;endFill=1`) Dependency(`endArrow=open;dashed=1`) Aggregation(`startArrow=diamondThin;startFill=0`) Composition(`startArrow=diamondThin;startFill=1`)
- **Visibility Symbols:** `+`(public) `#`(protected) `-`(private) `~`(package) `/`(derived)
- **State Colors:** Pending(`#dae8fc`,`#6c8ebf`) Success(`#d5e8d4`,`#82b366`) Error(`#f8cecc`,`#b85450`) Warning(`#fff2cc`,`#d6b656`) Complete(`#e1d5e7`,`#9673a6`)
- **Shape Styles:** `rounded`(0,1) `fillColor`(hex) `strokeColor`(hex) `strokeWidth`(num) `dashed`(0,1) `opacity`(0-100) `fontColor`(hex) `fontSize`(num) `fontStyle`(0=normal,1=bold,2=italic,3=both) `align`(left,center,right) `verticalAlign`(top,middle,bottom)
- **Edge Styles:** `edgeStyle`(orthogonalEdgeStyle,entityRelationEdgeStyle,elbowEdgeStyle) `curved`(0,1) `endArrow`/`startArrow`(classic,block,open,oval,diamond,none) `endFill`/`startFill`(0=hollow,1=filled)
## Edge Examples
```drawio
<mxfile><diagram name="Edge Examples" id="edge-examples"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="a1" value="A" style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="20" y="20" width="60" height="30" as="geometry"/></mxCell>
  <mxCell id="b1" value="B" style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="140" y="20" width="60" height="30" as="geometry"/></mxCell>
  <mxCell style="endArrow=classic;html=1;" edge="1" parent="1" source="a1" target="b1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a2" value="C" style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="20" y="80" width="60" height="30" as="geometry"/></mxCell>
  <mxCell id="b2" value="D" style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1"><mxGeometry x="140" y="80" width="60" height="30" as="geometry"/></mxCell>
  <mxCell style="edgeStyle=orthogonalEdgeStyle;endArrow=classic;dashed=1;html=1;" edge="1" parent="1" source="a2" target="b2"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Complete Example: Simple Architecture

```drawio
<mxfile><diagram name="Architecture" id="arch-1"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="client" value="Client" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1"><mxGeometry x="40" y="100" width="100" height="50" as="geometry"/></mxCell>
  <mxCell id="server" value="Server" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1"><mxGeometry x="240" y="100" width="100" height="50" as="geometry"/></mxCell>
  <mxCell id="db" value="Database" style="shape=cylinder;whiteSpace=wrap;html=1;fillColor=#ffe6cc;strokeColor=#d79b00;" vertex="1" parent="1"><mxGeometry x="440" y="85" width="80" height="80" as="geometry"/></mxCell>
  <mxCell style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;" edge="1" parent="1" source="client" target="server"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;" edge="1" parent="1" source="server" target="db"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram</mxfile>
```

## Common Pitfalls

| Issue | Solution |
|-------|----------|
| Shape not visible | Verify `vertex="1"` and `parent="1"` attributes |
| Edge not connecting | Ensure `source` and `target` match cell IDs |
| Styles not applying | Check semicolon separators in style string |
| Text not showing | Add `html=1;whiteSpace=wrap;` to style |

## Tips for AI Generation

1. **Plan layout first**: Sketch positions mentally before writing XML
2. **Use grid alignment**: Position shapes at multiples of 10 or 20
3. **Unique IDs**: Use descriptive IDs like `client`, `server`, `db` instead of random strings
4. **Consistent spacing**: Keep 40-60px gaps between connected shapes
5. **Layer backgrounds first**: Define zone/container cells before shapes inside them
6. **Color zones**: Use light background colors with `strokeColor=none` for region highlighting


## Resources

- [Draw.io Documentation](https://www.drawio.com/doc/)
- [mxGraph API Reference](https://jgraph.github.io/mxgraph/docs/manual.html)
