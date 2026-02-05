# Class Diagram

Shows class structure with attributes, methods, and relationships between classes.

## Key Elements

- **Class box**: Uses `swimlane` style with `childLayout=stackLayout`
- **Abstract class**: `fontStyle=2` (italic) for class name
- **Interface**: `&lt;&lt;interface&gt;&gt;` stereotype with `fontStyle=2`
- **Enumeration**: `&lt;&lt;enumeration&gt;&gt;` stereotype
- **Attributes/Methods**: `text;align=left;spacingLeft=4;portConstraint=eastwest`
- **Separator line**: `line;strokeWidth=1`
- **Static member**: `fontStyle=4` (underline)

## Relationships

| Relationship | Arrow Style | Description |
|--------------|-------------|-------------|
| Inheritance | `endArrow=block;endFill=0` | Hollow triangle (extends) |
| Realization | `endArrow=block;endFill=0;dashed=1` | Dashed + hollow triangle (implements) |
| Association | `endArrow=open;endFill=1` | Open arrow |
| Aggregation | `endArrow=diamondThin;endFill=0` | Hollow diamond (has-a) |
| Composition | `endArrow=diamondThin;endFill=1` | Filled diamond (owns) |
| Dependency | `dashed=1;endArrow=open` | Dashed open arrow (uses) |

## Visibility Symbols

| Symbol | Meaning |
|--------|---------|
| `+` | public |
| `#` | protected |
| `-` | private |
| `~` | package |

## Example

Zoo management system with interfaces, abstract class, enums, and various relationships:

```drawio
<mxfile><diagram id="class-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="ianimal" value="&lt;&lt;interface&gt;&gt;&#xa;IAnimal" style="swimlane;fontStyle=2;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=40;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="440" y="20" width="160" height="100" as="geometry"/></mxCell>
  <mxCell id="ianimal-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="ianimal" vertex="1"><mxGeometry y="40" width="160" height="8" as="geometry"/></mxCell>
  <mxCell id="ianimal-m1" value="+makeSound(): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontStyle=2" parent="ianimal" vertex="1"><mxGeometry y="48" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="ianimal-m2" value="+move(): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontStyle=2" parent="ianimal" vertex="1"><mxGeometry y="74" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="animal" value="Animal" style="swimlane;fontStyle=3;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=26;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="440" y="180" width="160" height="138" as="geometry"/></mxCell>
  <mxCell id="animal-attr1" value="#name: String" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="animal" vertex="1"><mxGeometry y="26" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="animal-attr2" value="#age: int" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="animal" vertex="1"><mxGeometry y="52" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="animal-attr3" value="-animalCount: int" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontStyle=4" parent="animal" vertex="1"><mxGeometry y="78" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="animal-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="animal" vertex="1"><mxGeometry y="104" width="160" height="8" as="geometry"/></mxCell>
  <mxCell id="animal-method1" value="+makeSound(): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontStyle=2" parent="animal" vertex="1"><mxGeometry y="112" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="animal-realize" value="" style="endArrow=block;endSize=10;endFill=0;shadow=0;strokeWidth=1;rounded=0;dashed=1;edgeStyle=orthogonalEdgeStyle;" parent="1" source="animal" target="ianimal" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
  <mxCell id="diettype" value="&lt;&lt;enumeration&gt;&gt;&#xa;DietType" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=40;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="680" y="180" width="140" height="118" as="geometry"/></mxCell>
  <mxCell id="diet-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="diettype" vertex="1"><mxGeometry y="40" width="140" height="8" as="geometry"/></mxCell>
  <mxCell id="diet-v1" value="HERBIVORE" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="diettype" vertex="1"><mxGeometry y="48" width="140" height="22" as="geometry"/></mxCell>
  <mxCell id="diet-v2" value="CARNIVORE" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="diettype" vertex="1"><mxGeometry y="70" width="140" height="22" as="geometry"/></mxCell>
  <mxCell id="diet-v3" value="OMNIVORE" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="diettype" vertex="1"><mxGeometry y="92" width="140" height="26" as="geometry"/></mxCell>
  <mxCell id="animal-diet" value="" style="endArrow=open;endFill=0;shadow=0;strokeWidth=1;rounded=0;dashed=1;edgeStyle=orthogonalEdgeStyle;" parent="1" source="animal" target="diettype" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
  <mxCell id="dog" value="Dog" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=26;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="1" vertex="1"><mxGeometry x="280" y="400" width="160" height="112" as="geometry"/></mxCell>
  <mxCell id="dog-attr1" value="-breed: String" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="dog" vertex="1"><mxGeometry y="26" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="dog-attr2" value="-isVaccinated: boolean" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="dog" vertex="1"><mxGeometry y="52" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="dog-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="dog" vertex="1"><mxGeometry y="78" width="160" height="8" as="geometry"/></mxCell>
  <mxCell id="dog-method1" value="+makeSound(): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="dog" vertex="1"><mxGeometry y="86" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="cat" value="Cat" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=26;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="1" vertex="1"><mxGeometry x="600" y="400" width="160" height="112" as="geometry"/></mxCell>
  <mxCell id="cat-attr1" value="-indoor: boolean" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="cat" vertex="1"><mxGeometry y="26" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="cat-attr2" value="-livesRemaining: int" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="cat" vertex="1"><mxGeometry y="52" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="cat-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="cat" vertex="1"><mxGeometry y="78" width="160" height="8" as="geometry"/></mxCell>
  <mxCell id="cat-method1" value="+makeSound(): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="cat" vertex="1"><mxGeometry y="86" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="dog-inherit" value="" style="endArrow=block;endSize=10;endFill=0;shadow=0;strokeWidth=1;rounded=0;edgeStyle=orthogonalEdgeStyle;" parent="1" source="dog" target="animal" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
  <mxCell id="cat-inherit" value="" style="endArrow=block;endSize=10;endFill=0;shadow=0;strokeWidth=1;rounded=0;edgeStyle=orthogonalEdgeStyle;" parent="1" source="cat" target="animal" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
  <mxCell id="zoo" value="Zoo" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=26;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="40" y="180" width="180" height="138" as="geometry"/></mxCell>
  <mxCell id="zoo-attr1" value="-name: String" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="zoo" vertex="1"><mxGeometry y="26" width="180" height="26" as="geometry"/></mxCell>
  <mxCell id="zoo-attr2" value="-location: String" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="zoo" vertex="1"><mxGeometry y="52" width="180" height="26" as="geometry"/></mxCell>
  <mxCell id="zoo-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="zoo" vertex="1"><mxGeometry y="78" width="180" height="8" as="geometry"/></mxCell>
  <mxCell id="zoo-m1" value="+addAnimal(a: Animal): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="zoo" vertex="1"><mxGeometry y="86" width="180" height="26" as="geometry"/></mxCell>
  <mxCell id="zoo-m2" value="+getAnimalCount(): int" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="zoo" vertex="1"><mxGeometry y="112" width="180" height="26" as="geometry"/></mxCell>
  <mxCell id="cage" value="Cage" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=26;horizontalStack=0;resizeParent=1;resizeLast=0;collapsible=1;marginBottom=0;rounded=0;shadow=0;strokeWidth=1;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="40" y="400" width="160" height="112" as="geometry"/></mxCell>
  <mxCell id="cage-attr1" value="-cageId: int" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="cage" vertex="1"><mxGeometry y="26" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="cage-attr2" value="-capacity: int" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="cage" vertex="1"><mxGeometry y="52" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="cage-sep" value="" style="line;html=1;strokeWidth=1;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;" parent="cage" vertex="1"><mxGeometry y="78" width="160" height="8" as="geometry"/></mxCell>
  <mxCell id="cage-m1" value="+clean(): void" style="text;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;" parent="cage" vertex="1"><mxGeometry y="86" width="160" height="26" as="geometry"/></mxCell>
  <mxCell id="zoo-cage" value="" style="endArrow=none;startArrow=diamondThin;startFill=1;startSize=14;shadow=0;strokeWidth=1;rounded=0;edgeStyle=orthogonalEdgeStyle;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" parent="1" source="zoo" target="cage" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
  <mxCell id="zoo-cage-label1" value="1" style="text;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=11;" parent="zoo-cage" connectable="0" vertex="1"><mxGeometry x="-0.85" y="-1" relative="1" as="geometry"><mxPoint x="-10" y="1" as="offset"/></mxGeometry></mxCell>
  <mxCell id="zoo-cage-label2" value="1..*" style="text;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=11;" parent="zoo-cage" connectable="0" vertex="1"><mxGeometry x="0.85" y="-1" relative="1" as="geometry"><mxPoint x="-14" as="offset"/></mxGeometry></mxCell>
  <mxCell id="zoo-animal" value="" style="endArrow=none;startArrow=diamondThin;startFill=0;startSize=14;shadow=0;strokeWidth=1;rounded=0;edgeStyle=orthogonalEdgeStyle;" parent="1" source="zoo" target="animal" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
  <mxCell id="zoo-animal-label1" value="1" style="text;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=11;" parent="zoo-animal" connectable="0" vertex="1"><mxGeometry x="-0.85" relative="1" as="geometry"><mxPoint x="-10" y="10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="zoo-animal-label2" value="0..*" style="text;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=11;" parent="zoo-animal" connectable="0" vertex="1"><mxGeometry x="0.85" relative="1" as="geometry"><mxPoint x="10" y="10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="cage-animal" value="" style="endArrow=open;endFill=1;shadow=0;strokeWidth=1;rounded=0;edgeStyle=orthogonalEdgeStyle;exitX=1;exitY=0.5;exitDx=0;exitDy=0;" parent="1" source="cage-attr1" target="dog" edge="1"><mxGeometry width="160" relative="1" as="geometry"><Array as="points"><mxPoint x="240" y="439"/><mxPoint x="240" y="456"/></Array></mxGeometry></mxCell>
  <mxCell id="cage-animal-label" value="houses" style="text;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="cage-animal" connectable="0" vertex="1"><mxGeometry x="0.5" relative="1" as="geometry"><mxPoint x="-14" y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="cage-animal-mult" value="0..*" style="text;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="cage-animal" connectable="0" vertex="1"><mxGeometry x="0.9" relative="1" as="geometry"><mxPoint x="10" y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="note1" value="Abstract class Animal&#xa;implements IAnimal&#xa;interface" style="shape=note;strokeWidth=1;fontSize=11;size=20;whiteSpace=wrap;fillColor=#ffffcc;strokeColor=#999966;fontColor=#333333;" parent="1" vertex="1"><mxGeometry x="680" y="40" width="120" height="70" as="geometry"/></mxCell>
  <mxCell id="note1-link" value="" style="endArrow=none;dashed=1;strokeWidth=1;rounded=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="animal" target="note1" edge="1"><mxGeometry width="160" relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
