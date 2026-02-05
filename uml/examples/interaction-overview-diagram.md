# Interaction Overview Diagram

**Purpose**: Combines activity diagrams and sequence diagrams to show interaction fragments within control flow.

## Key Elements

| Element | Style | Description |
|---------|-------|-------------|
| Interaction frame | `shape=umlFrame;width=170;fontStyle=1` | Main diagram container |
| Ref fragment | `shape=umlFrame;width=50` | Reference to another interaction |
| sd fragment | `shape=umlFrame;width=120` | Inline sequence diagram |
| alt/loop/opt | `shape=umlFrame` + label | Combined fragment in sequence |
| Initial node | `ellipse;fillColor=strokeColor` | Start point (filled circle) |
| Final node | `shape=endState;fillColor=strokeColor` | End point |
| Decision node | `rhombus` | Branch point (diamond) |
| Lifeline | `shape=umlLifeline` | Participant timeline |
| Actor lifeline | `shape=umlLifeline;participant=umlActor` | Human participant |
| Entity lifeline | `shape=umlLifeline;participant=umlEntity` | Database/entity |
| Activation bar | `points=[];perimeter=orthogonalPerimeter` | Active execution |
| Destroy marker | `shape=umlDestroy;strokeWidth=3` | Object destruction (X) |
| Condition label | Edge value `[condition]` | Guard condition |

## Example

Library system usage flow with inline sequence diagram:

```drawio
<mxfile><diagram id="interaction-overview-1" name="Page-1"><mxGraphModel dx="1200" dy="900" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1000" pageHeight="900" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="frame" value="Interaction useLibrary" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;recursiveResize=0;container=1;collapsible=0;width=170;fontStyle=1" parent="1" vertex="1"><mxGeometry x="20" y="20" width="1220" height="560" as="geometry"/></mxCell>
  <mxCell id="start" value="" style="ellipse;fillColor=strokeColor;html=1;" parent="1" vertex="1"><mxGeometry x="50" y="60" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="decision1" value="" style="rhombus;whiteSpace=wrap;html=1;" parent="1" vertex="1"><mxGeometry x="100" y="50" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="flow1" style="edgeStyle=none;curved=1;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="start" target="decision1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ref1" value="Ref" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;width=50;" parent="1" vertex="1"><mxGeometry x="180" y="40" width="180" height="80" as="geometry"/></mxCell>
  <mxCell id="ref1-text" value="useCatalog" style="text;align=center;html=1;fontSize=14;" parent="1" vertex="1"><mxGeometry x="210" y="65" width="120" height="30" as="geometry"/></mxCell>
  <mxCell id="flow2" style="edgeStyle=none;curved=1;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="decision1" target="ref1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="decision2" value="" style="rhombus;whiteSpace=wrap;html=1;" parent="1" vertex="1"><mxGeometry x="400" y="50" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="flow3" style="edgeStyle=none;curved=1;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="ref1" target="decision2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="sd1" value="sd searchForItems" style="shape=umlFrame;whiteSpace=wrap;html=1;width=120;height=30;boundedLbl=1;verticalAlign=middle;align=left;spacingLeft=5;fillColor=#f5f5f5;strokeColor=#666666;" parent="1" vertex="1"><mxGeometry x="500" y="40" width="500" height="380" as="geometry"/></mxCell>
  <mxCell id="alt1" value="alt" style="shape=umlFrame;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;" parent="1" vertex="1"><mxGeometry x="580" y="170" width="380" height="200" as="geometry"/></mxCell>
  <mxCell id="alt-divider" style="endArrow=none;dashed=1;html=1;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="580" y="290" as="sourcePoint"/><mxPoint x="960" y="290" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="alt-cond1" value="[itemName=valid]" style="text;html=1;align=left;verticalAlign=middle;strokeColor=none;fillColor=none;fontSize=10;" parent="1" vertex="1"><mxGeometry x="585" y="190" width="100" height="20" as="geometry"/></mxCell>
  <mxCell id="alt-cond2" value="[else]" style="text;html=1;align=left;verticalAlign=middle;strokeColor=none;fillColor=none;fontSize=10;" parent="1" vertex="1"><mxGeometry x="585" y="300" width="40" height="20" as="geometry"/></mxCell>
  <mxCell id="ll1" value=":ValidLibraryMember" style="shape=umlLifeline;participant=umlActor;perimeter=lifelinePerimeter;html=1;container=1;collapsible=0;recursiveResize=0;verticalAlign=top;spacingTop=36;outlineConnect=0;size=40;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="530" y="80" width="20" height="330" as="geometry"/></mxCell>
  <mxCell id="act1" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="535" y="135" width="10" height="260" as="geometry"/></mxCell>
  <mxCell id="ll2" value=":SearchForm" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="1" vertex="1"><mxGeometry x="620" y="80" width="80" height="330" as="geometry"/></mxCell>
  <mxCell id="act2" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="1" vertex="1"><mxGeometry x="655" y="135" width="10" height="230" as="geometry"/></mxCell>
  <mxCell id="ll3" value=":ItemDatabase" style="shape=umlLifeline;participant=umlEntity;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;verticalAlign=top;spacingTop=36;outlineConnect=0;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="760" y="80" width="30" height="330" as="geometry"/></mxCell>
  <mxCell id="act3" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="770" y="210" width="10" height="40" as="geometry"/></mxCell>
  <mxCell id="ll4" value=":ResultList" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="860" y="200" width="80" height="120" as="geometry"/></mxCell>
  <mxCell id="act4" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="895" y="230" width="10" height="50" as="geometry"/></mxCell>
  <mxCell id="destroy" value="" style="shape=umlDestroy;whiteSpace=wrap;html=1;strokeWidth=3;" parent="1" vertex="1"><mxGeometry x="888" y="290" width="24" height="24" as="geometry"/></mxCell>
  <mxCell id="msg1" value="1: itemSearch(itemName)" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;fontSize=10;" parent="1" source="act1" target="act2" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="545" y="145" as="sourcePoint"/></mxGeometry></mxCell>
  <mxCell id="msg2" value="1.2: searchItems()" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;fontSize=10;" parent="1" source="act2" target="act3" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="665" y="220" as="sourcePoint"/></mxGeometry></mxCell>
  <mxCell id="msg3" value="1.2.1: listResults()" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;fontSize=10;" parent="1" source="act3" target="act4" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="780" y="240" as="sourcePoint"/></mxGeometry></mxCell>
  <mxCell id="msg4" value="1.3: displayError()" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;fontSize=10;entryX=1.1;entryY=0.85;entryDx=0;entryDy=0;entryPerimeter=0;edgeStyle=orthogonalEdgeStyle;" parent="1" source="act2" target="act2" edge="1"><mxGeometry x="-0.5" relative="1" as="geometry"><mxPoint x="665" y="330" as="sourcePoint"/><mxPoint x="685" y="350" as="targetPoint"/><Array as="points"><mxPoint x="690" y="330"/><mxPoint x="690" y="350"/></Array><mxPoint as="offset"/></mxGeometry></mxCell>
  <mxCell id="ret1" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;rounded=0;fontSize=10;" parent="1" source="act2" target="act1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="665" y="390" as="sourcePoint"/></mxGeometry></mxCell>
  <mxCell id="flow4" value="[validMember]" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;fontSize=10;" parent="1" source="decision2" target="sd1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ref2" value="Ref" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;width=50;" parent="1" vertex="1"><mxGeometry x="180" y="160" width="180" height="80" as="geometry"/></mxCell>
  <mxCell id="ref2-text" value="browseShelves" style="text;align=center;html=1;fontSize=14;" parent="1" vertex="1"><mxGeometry x="200" y="185" width="140" height="30" as="geometry"/></mxCell>
  <mxCell id="flow5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="decision1" target="ref2" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="125" y="200"/></Array></mxGeometry></mxCell>
  <mxCell id="decision3" value="" style="rhombus;whiteSpace=wrap;html=1;" parent="1" vertex="1"><mxGeometry x="245" y="280" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="flow6" style="edgeStyle=none;curved=1;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="ref2" target="decision3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ref3" value="Ref" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;width=50;" parent="1" vertex="1"><mxGeometry x="60" y="380" width="180" height="80" as="geometry"/></mxCell>
  <mxCell id="ref3-text" value="registerLibraryMember" style="text;align=center;html=1;fontSize=12;" parent="1" vertex="1"><mxGeometry x="70" y="405" width="160" height="30" as="geometry"/></mxCell>
  <mxCell id="flow7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="decision3" target="ref3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="flow8" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="ref3" target="decision3" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="40" y="420"/><mxPoint x="40" y="305"/></Array></mxGeometry></mxCell>
  <mxCell id="ref4" value="Ref" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;width=50;" parent="1" vertex="1"><mxGeometry x="500" y="480" width="180" height="80" as="geometry"/></mxCell>
  <mxCell id="ref4-text" value="borrowBook" style="text;align=center;html=1;fontSize=14;" parent="1" vertex="1"><mxGeometry x="520" y="505" width="140" height="30" as="geometry"/></mxCell>
  <mxCell id="flow9" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="sd1" target="ref4" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="750" y="450"/><mxPoint x="590" y="450"/></Array></mxGeometry></mxCell>
  <mxCell id="flow10" value="[validMember]" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;fontSize=10;" parent="1" source="decision3" target="ref4" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="400" y="305"/><mxPoint x="400" y="520"/></Array></mxGeometry></mxCell>
  <mxCell id="ref5" value="Ref" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;width=50;" parent="1" vertex="1"><mxGeometry x="1050" y="40" width="180" height="80" as="geometry"/></mxCell>
  <mxCell id="ref5-text" value="attendEvent" style="text;align=center;html=1;fontSize=14;" parent="1" vertex="1"><mxGeometry x="1080" y="65" width="120" height="30" as="geometry"/></mxCell>
  <mxCell id="flow11" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="decision2" target="ref5" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="425" y="30"/><mxPoint x="1140" y="30"/></Array></mxGeometry></mxCell>
  <mxCell id="end" value="" style="ellipse;html=1;shape=endState;fillColor=strokeColor;" parent="1" vertex="1"><mxGeometry x="1125" y="530" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="flow12" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="ref4" target="end" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="flow13" style="edgeStyle=orthogonalEdgeStyle;rounded=0;endSize=8;endArrow=classic;html=1;" parent="1" source="ref5" target="end" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="1140" y="160"/><mxPoint x="1220" y="160"/><mxPoint x="1220" y="545"/></Array></mxGeometry></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Style Patterns

| Pattern | Style Key |
|---------|-----------|
| Outer frame | `shape=umlFrame;width=170` (title width) |
| Reference box | `shape=umlFrame;width=50` for "Ref" label |
| Inline sd | `shape=umlFrame;width=120` + sd prefix |
| Actor lifeline | `participant=umlActor;size=40` |
| Entity lifeline | `participant=umlEntity` (circle with line) |
| Activation bar | `points=[];perimeter=orthogonalPerimeter` inside lifeline |
| Destroy X | `shape=umlDestroy;strokeWidth=3` |
| Alt fragment | `shape=umlFrame` + dashed divider line |
| Guard condition | `[condition]` as edge label |
