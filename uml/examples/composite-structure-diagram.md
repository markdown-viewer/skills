# Composite Structure Diagram

**Purpose**: Shows the internal structure of a classifier and collaborations between parts.

## Key Elements

| Element | Style | Description |
|---------|-------|-------------|
| Collaboration | `shape=ellipse;container=1;dashed=1` | Dashed ellipse container |
| Role | `html=1;align=center;rotatable=0` | Rectangle inside collaboration |
| Collaboration Use | `ellipse;dashed=1` + instance name | Named collaboration instance |
| Internal Structure | Header + body rectangles | Class with internal parts |
| Part | `rounded=0;whiteSpace=wrap` | Named part `name: Type` |
| Connector | `endArrow=none;endFill=0` | Link between roles/parts |
| Occurrence | `dashed=1;dashPattern=1 1;endArrow=open` | Collaboration specialization |
| Role Binding | `edgeLabel` on dashed line | Maps role to part |
| Dependency | `dashed=1;endArrow=classic;endFill=1` | Directed dependency |

## Example

Sale collaboration with CustomerDesignSale specialization and internal structure:

```drawio
<mxfile><diagram id="composite-structure-1" name="Page-1"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="sale" value="" style="shape=ellipse;container=1;horizontal=1;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;html=1;dashed=1;collapsible=0;" parent="1" vertex="1"><mxGeometry x="420" y="60" width="180" height="160" as="geometry"/></mxCell>
  <mxCell id="sale-title" value="Sale" style="html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;spacingLeft=4;spacingRight=4;rotatable=0;points=[[0,0.5],[1,0.5]];resizeWidth=1;" parent="sale" vertex="1"><mxGeometry width="180" height="24" as="geometry"/></mxCell>
  <mxCell id="sale-line" value="" style="line;strokeWidth=1;fillColor=none;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;dashed=1;resizeWidth=1;" parent="sale" vertex="1"><mxGeometry x="26" y="24" width="128" height="6" as="geometry"/></mxCell>
  <mxCell id="seller" value="Seller" style="html=1;align=center;verticalAlign=middle;rotatable=0;" parent="sale" vertex="1"><mxGeometry width="90" height="28" relative="1" as="geometry"><mxPoint x="45" y="45" as="offset"/></mxGeometry></mxCell>
  <mxCell id="buyer" value="Buyer" style="html=1;align=center;verticalAlign=middle;rotatable=0;" parent="sale" vertex="1"><mxGeometry width="90" height="28" relative="1" as="geometry"><mxPoint x="45" y="100" as="offset"/></mxGeometry></mxCell>
  <mxCell id="role-conn" value="" style="edgeStyle=none;endArrow=none;verticalAlign=middle;labelBackgroundColor=none;endSize=12;html=1;align=left;endFill=0;spacingLeft=4;" parent="sale" source="seller" target="buyer" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="cds" value="" style="shape=ellipse;container=1;horizontal=1;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;html=1;dashed=1;collapsible=0;" parent="1" vertex="1"><mxGeometry x="60" y="40" width="240" height="200" as="geometry"/></mxCell>
  <mxCell id="cds-title" value="CustomerDesignSale" style="html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;spacingLeft=4;spacingRight=4;rotatable=0;points=[[0,0.5],[1,0.5]];resizeWidth=1;" parent="cds" vertex="1"><mxGeometry y="8" width="240" height="28" as="geometry"/></mxCell>
  <mxCell id="cds-line" value="" style="line;strokeWidth=1;fillColor=none;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;dashed=1;resizeWidth=1;" parent="cds" vertex="1"><mxGeometry x="35" y="30" width="170" height="6" as="geometry"/></mxCell>
  <mxCell id="producer" value="Producer" style="html=1;align=center;verticalAlign=middle;rotatable=0;" parent="cds" vertex="1"><mxGeometry width="90" height="28" relative="1" as="geometry"><mxPoint x="75" y="50" as="offset"/></mxGeometry></mxCell>
  <mxCell id="designer" value="Designer" style="html=1;align=center;verticalAlign=middle;rotatable=0;" parent="cds" vertex="1"><mxGeometry width="90" height="28" relative="1" as="geometry"><mxPoint x="75" y="140" as="offset"/></mxGeometry></mxCell>
  <mxCell id="cds-conn" value="" style="edgeStyle=none;endArrow=none;verticalAlign=middle;labelBackgroundColor=none;endSize=12;html=1;align=left;endFill=0;spacingLeft=4;" parent="cds" source="producer" target="designer" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="occurrence" value="«occurrence»" style="rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;dashPattern=1 1;endArrow=open;endFill=0;fontSize=10;" parent="1" source="cds" target="sale" edge="1"><mxGeometry x="0.0066" y="11" relative="1" as="geometry"><mxPoint as="offset"/></mxGeometry></mxCell>
  <mxCell id="bind1" style="edgeStyle=none;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;dashPattern=1 1;endArrow=open;endFill=0;" parent="1" source="producer" target="seller" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="bind2" style="edgeStyle=none;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;dashPattern=1 1;endArrow=open;endFill=0;" parent="1" source="designer" target="buyer" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="struct-group" value="" style="group" parent="1" vertex="1" connectable="0"><mxGeometry x="660" y="40" width="280" height="210" as="geometry"/></mxCell>
  <mxCell id="struct-header" value="CustomerDesignSale" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;fontStyle=1;" parent="struct-group" vertex="1"><mxGeometry width="280" height="35" as="geometry"/></mxCell>
  <mxCell id="struct-body" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;" parent="struct-group" vertex="1"><mxGeometry y="35" width="280" height="175" as="geometry"/></mxCell>
  <mxCell id="collab-use" value="customDesign: Sale" style="ellipse;whiteSpace=wrap;html=1;dashed=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="struct-group" vertex="1"><mxGeometry x="80" y="55" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="part-design" value="d: Design" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="struct-group" vertex="1"><mxGeometry x="20" y="150" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="part-product" value="p: Product" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="struct-group" vertex="1"><mxGeometry x="170" y="150" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="role-design" style="edgeStyle=none;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=open;endFill=0;dashed=1;" parent="struct-group" source="collab-use" target="part-design" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="role-design-label" value="Designer" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="role-design" vertex="1" connectable="0"><mxGeometry x="0.35" y="1" relative="1" as="geometry"><mxPoint x="-20" y="-5" as="offset"/></mxGeometry></mxCell>
  <mxCell id="role-product" style="edgeStyle=none;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=classic;endFill=1;dashed=1;" parent="struct-group" source="collab-use" target="part-product" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="role-product-label" value="Producer" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="role-product" vertex="1" connectable="0"><mxGeometry x="0.1" y="2" relative="1" as="geometry"><mxPoint x="20" y="5" as="offset"/></mxGeometry></mxCell>
  <mxCell id="part-conn" style="edgeStyle=none;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=none;endFill=0;" parent="struct-group" source="part-design" target="part-product" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>  
</root></mxGraphModel></diagram></mxfile>
```

## Style Patterns

| Pattern | Usage |
|---------|-------|
| Collaboration container | `shape=ellipse;container=1;dashed=1` with title + separator line |
| Role inside collaboration | `relative=1` geometry with `mxPoint` offset |
| Collaboration Use | Named dashed ellipse inside internal structure |
| Internal Structure | Group with header rect + body rect |
| Role binding label | `edgeLabel` attached to dashed dependency edge |
| Connector types | `endArrow=none` (association), `endArrow=open` (dependency), `endArrow=classic` (directed) |
