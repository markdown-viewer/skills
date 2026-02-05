# Deployment Diagram

Shows physical deployment architecture of the system.

## Key Elements

| Element | Style | Description |
|---------|-------|-------------|
| Node | `shape=cube;size=10;direction=south` | 3D box for execution environment |
| Device | `shape=cube` + `«device»` stereotype | Physical hardware |
| Execution Environment | `shape=cube` + `«executionEnvironment»` | Software environment (OS, container) |
| Artifact | `text;fillColor=#ffffff;strokeColor=#000000` | Deployable unit with `«artifact»` |
| Deployment Spec | `«deployment spec»` stereotype | Configuration descriptor |
| Manifest | `dashed=1;endArrow=open` | Artifact manifests component |
| Deploy | `dashed=1;endArrow=open` + `«deploy»` | Artifact deployed to node |
| Communication path | `endArrow=open;endFill=0` | Network connection with protocol |
| Document icon | `shape=note;size=6` | Small document indicator |

## Example

Application server deployment with nested artifacts and deployment specs:

```drawio
<mxfile><diagram id="deployment-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="400" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="server" value=":ApplicationServer1" style="verticalAlign=top;align=left;shape=cube;size=10;direction=south;fontStyle=1;html=1;boundedLbl=1;spacingLeft=5;strokeColor=#999999;fillColor=#f9f9f9;" parent="1" vertex="1"><mxGeometry x="40" y="40" width="520" height="260" as="geometry"/></mxCell>
  <mxCell id="ear" value="&amp;lt;&amp;lt;artifact&amp;gt;&amp;gt;&lt;br&gt;&lt;b&gt;OrderApp.ear&lt;/b&gt;" style="text;html=1;align=center;verticalAlign=top;fillColor=#ffffff;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="50" y="90" width="490" height="200" as="geometry"/></mxCell>
  <mxCell id="shopjar" value="&amp;lt;&amp;lt;artifact&amp;gt;&amp;gt;&lt;br&gt;&lt;b&gt;ShopApp.jar&lt;/b&gt;" style="text;html=1;align=center;verticalAlign=middle;fillColor=#ffffff;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="70" y="140" width="180" height="60" as="geometry"/></mxCell>
  <mxCell id="orderjar" value="&amp;lt;&amp;lt;artifact&amp;gt;&amp;gt;&lt;br&gt;&lt;b&gt;Order.jar&lt;/b&gt;" style="text;html=1;align=center;verticalAlign=middle;fillColor=#ffffff;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="340" y="140" width="180" height="60" as="geometry"/></mxCell>
  <mxCell id="shopspec" value="&amp;lt;&amp;lt;deployment spec&amp;gt;&amp;gt;&lt;br&gt;&lt;b&gt;ShopAppDescription.xml&lt;/b&gt;" style="text;html=1;align=center;verticalAlign=middle;fillColor=#ffffff;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="70" y="220" width="180" height="60" as="geometry"/></mxCell>
  <mxCell id="orderspec" value="&amp;lt;&amp;lt;deployment spec&amp;gt;&amp;gt;&lt;br&gt;&lt;b&gt;OrderDescription.xml&lt;/b&gt;" style="text;html=1;align=center;verticalAlign=middle;fillColor=#ffffff;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="280" y="220" width="180" height="60" as="geometry"/></mxCell>
  <mxCell id="doc1" value="" style="shape=note;whiteSpace=wrap;html=1;backgroundOutline=1;darkOpacity=0.05;size=6;" parent="1" vertex="1"><mxGeometry x="227" y="147" width="15" height="20" as="geometry"/></mxCell>
  <mxCell id="doc2" value="" style="shape=note;whiteSpace=wrap;html=1;backgroundOutline=1;darkOpacity=0.05;size=6;" parent="1" vertex="1"><mxGeometry x="519" y="96" width="15" height="20" as="geometry"/></mxCell>
  <mxCell id="doc3" value="" style="shape=note;whiteSpace=wrap;html=1;backgroundOutline=1;darkOpacity=0.05;size=6;" parent="1" vertex="1"><mxGeometry x="498" y="146" width="15" height="20" as="geometry"/></mxCell>
  <mxCell id="dep1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=open;endFill=0;dashed=1;" parent="1" source="shopjar" target="orderjar" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep2" style="rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=open;endFill=0;dashed=1;" parent="1" source="orderspec" target="orderjar" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Style Patterns

| Pattern | Style Key |
|---------|-----------|
| Device node | `shape=cube` + `«device»` in value |
| Execution Environment | `shape=cube` + `«executionEnvironment»` |
| Nested artifact | Smaller artifact inside larger artifact bounds |
| Deployment spec | Yellow fill `fillColor=#fff2cc` + `«deployment spec»` |
| Document icon | `shape=note;size=6` small icon near artifact |
| Communication protocol | `«HTTP»`, `«TCP»`, `«JDBC»` as edge label |
| Manifest dependency | `dashed=1;endArrow=open` from spec to artifact |
