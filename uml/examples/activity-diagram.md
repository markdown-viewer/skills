# Activity Diagram

Shows workflow with activities, decisions, and parallel processing.

## Key Elements

- **Initial node**: `ellipse;fillColor=#000000` - solid black circle
- **Final node**: `ellipse;shape=endState;fillColor=#000000` - bullseye circle
- **Flow final**: `ellipse;shape=endState;fillColor=#ffffff` - X in circle (terminates flow only)
- **Activity**: `rounded=1;arcSize=50` or `absoluteArcSize=1;arcSize=10` - rounded rectangle
- **Decision/Merge node**: `rhombus` - diamond shape
- **Fork/Join bar**: Rectangle `fillColor=#000000`, vertical or horizontal
- **Swimlane**: `swimlane;horizontal=0` - partition by actor/role
- **Interruptible region**: `rounded=1;dashed=1` - dashed rounded rectangle
- **Signal send**: `shape=mxgraph.infographic.ribbonSimple` - pentagon pointing right
- **Signal receive**: `shape=offPageConnector` - pentagon pointing in
- **Note**: `shape=note` - folded corner rectangle

## Edge Styles

| Type | Style |
|------|-------|
| Control flow | `endArrow=block;endFill=1` |
| Object flow | `endArrow=open;dashed=1` |
| Guard condition | Label with `[condition]` |

## Example

Order fulfillment process with swimlanes, parallel activities, and interruptible region:

```drawio
<mxfile><diagram id="activity-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="swimlane-container" value="Order Fulfillment" style="swimlane;html=1;childLayout=stackLayout;resizeParent=1;resizeParentMax=0;horizontal=0;startSize=30;horizontalStack=0;fillColor=#f5f5f5;strokeColor=#666666;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="20" y="20" width="860" height="500" as="geometry"/></mxCell>
  <mxCell id="lane-customer" value="Customer" style="swimlane;html=1;startSize=30;horizontal=0;fillColor=#f8cecc;strokeColor=#b85450;" parent="swimlane-container" vertex="1"><mxGeometry x="30" width="830" height="120" as="geometry"/></mxCell>
  <mxCell id="start" value="" style="ellipse;html=1;shape=startState;fillColor=#000000;strokeColor=#000000;" parent="lane-customer" vertex="1"><mxGeometry x="40" y="45" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="act-place" value="Place Order" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#f8cecc;strokeColor=#b85450;" parent="lane-customer" vertex="1"><mxGeometry x="110" y="40" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="signal-order" value="Order Request" style="html=1;shape=mxgraph.infographic.ribbonSimple;notch1=20;notch2=0;fillColor=#f8cecc;strokeColor=#b85450;fontSize=10;" parent="lane-customer" vertex="1"><mxGeometry x="230" y="40" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="act-confirm" value="Receive&#xa;Confirmation" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#f8cecc;strokeColor=#b85450;" parent="lane-customer" vertex="1"><mxGeometry x="710" y="40" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="e1" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-customer" source="start" target="act-place" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e2" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-customer" source="act-place" target="signal-order" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="lane-order" value="Order Processing" style="swimlane;html=1;startSize=30;horizontal=0;fillColor=#fff2cc;strokeColor=#d6b656;" parent="swimlane-container" vertex="1"><mxGeometry x="30" y="120" width="830" height="180" as="geometry"/></mxCell>
  <mxCell id="interrupt-region" value="Interruptible Region" style="rounded=1;html=1;absoluteArcSize=1;arcSize=20;dashed=1;fillColor=#fffef0;strokeColor=#999999;verticalAlign=top;spacingTop=5;fontStyle=2;fontSize=10;" parent="lane-order" vertex="1"><mxGeometry x="40" y="20" width="480" height="140" as="geometry"/></mxCell>
  <mxCell id="receive-order" value="Order" style="shape=offPageConnector;html=1;rotation=-90;fillColor=#fff2cc;strokeColor=#d6b656;fontSize=10;" parent="lane-order" vertex="1"><mxGeometry x="50" y="60" width="60" height="40" as="geometry"/></mxCell>
  <mxCell id="act-validate" value="Validate&#xa;Order" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#fff2cc;strokeColor=#d6b656;" parent="lane-order" vertex="1"><mxGeometry x="130" y="60" width="70" height="40" as="geometry"/></mxCell>
  <mxCell id="decision-valid" value="" style="rhombus;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="lane-order" vertex="1"><mxGeometry x="220" y="65" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="act-process" value="Process&#xa;Order" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#fff2cc;strokeColor=#d6b656;" parent="lane-order" vertex="1"><mxGeometry x="280" y="60" width="70" height="40" as="geometry"/></mxCell>
  <mxCell id="fork1" value="" style="html=1;fillColor=#000000;strokeColor=none;" parent="lane-order" vertex="1"><mxGeometry x="375" y="40" width="5" height="80" as="geometry"/></mxCell>
  <mxCell id="act-ship" value="Prepare&#xa;Shipment" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#fff2cc;strokeColor=#d6b656;" parent="lane-order" vertex="1"><mxGeometry x="410" y="35" width="80" height="40" as="geometry"/></mxCell>
  <mxCell id="signal-cancel" value="Cancel Request" style="html=1;shape=mxgraph.infographic.ribbonSimple;notch1=20;notch2=0;fillColor=#f8cecc;strokeColor=#b85450;fontSize=9;rotation=0;" parent="lane-order" vertex="1"><mxGeometry x="280" y="120" width="90" height="30" as="geometry"/></mxCell>
  <mxCell id="flow-final" value="" style="ellipse;html=1;shape=endState;fillColor=#ffffff;strokeColor=#000000;" parent="lane-order" vertex="1"><mxGeometry x="400" y="120" width="25" height="25" as="geometry"/></mxCell>
  <mxCell id="join1" value="" style="html=1;fillColor=#000000;strokeColor=none;" parent="lane-order" vertex="1"><mxGeometry x="540" y="40" width="5" height="80" as="geometry"/></mxCell>
  <mxCell id="act-notify" value="Send&#xa;Confirmation" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#fff2cc;strokeColor=#d6b656;" parent="lane-order" vertex="1"><mxGeometry x="580" y="55" width="80" height="40" as="geometry"/></mxCell>
  <mxCell id="e3" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-order" source="receive-order" target="act-validate" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e4" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-order" source="act-validate" target="decision-valid" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e5" value="[valid]" style="endArrow=block;endFill=1;rounded=0;fontSize=10;" parent="lane-order" source="decision-valid" target="act-process" edge="1"><mxGeometry x="0.1" y="10" relative="1" as="geometry"><mxPoint as="offset"/></mxGeometry></mxCell>
  <mxCell id="e6" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-order" source="act-process" target="fork1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e7" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-order" source="fork1" target="act-ship" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e8" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-order" source="act-ship" target="join1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e9" value="" style="endArrow=block;endFill=1;rounded=0;" parent="lane-order" source="join1" target="act-notify" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-cancel" value="" style="endArrow=block;endFill=1;rounded=0;dashed=1;strokeColor=#b85450;" parent="lane-order" source="signal-cancel" target="flow-final" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="lane-account" value="Accounting" style="swimlane;html=1;startSize=30;horizontal=0;fillColor=#d5e8d4;strokeColor=#82b366;" parent="swimlane-container" vertex="1"><mxGeometry x="30" y="300" width="830" height="100" as="geometry"/></mxCell>
  <mxCell id="act-invoice" value="Send Invoice" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#d5e8d4;strokeColor=#82b366;" parent="lane-account" vertex="1"><mxGeometry x="410" y="30" width="80" height="40" as="geometry"/></mxCell>
  <mxCell id="e10" value="" style="endArrow=block;endFill=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" parent="swimlane-container" source="fork1" target="act-invoice" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="408" y="220" as="sourcePoint"/></mxGeometry></mxCell>
  <mxCell id="e11" value="" style="endArrow=block;endFill=1;rounded=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" parent="swimlane-container" source="act-invoice" target="join1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="573" y="220" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="lane-warehouse" value="Warehouse" style="swimlane;html=1;startSize=30;horizontal=0;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="swimlane-container" vertex="1"><mxGeometry x="30" y="400" width="830" height="100" as="geometry"/></mxCell>
  <mxCell id="act-pack" value="Pack Items" style="rounded=1;html=1;absoluteArcSize=1;arcSize=10;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="lane-warehouse" vertex="1"><mxGeometry x="580" y="30" width="80" height="40" as="geometry"/></mxCell>
  <mxCell id="end" value="" style="ellipse;html=1;shape=endState;fillColor=#000000;strokeColor=#000000;" parent="lane-warehouse" vertex="1"><mxGeometry x="760" y="35" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="e12" value="" style="endArrow=block;endFill=1;rounded=0;" parent="swimlane-container" source="act-notify" target="act-pack" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e13" value="" style="endArrow=block;endFill=1;rounded=0;" parent="swimlane-container" source="act-pack" target="end" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e14" value="" style="endArrow=block;endFill=1;rounded=0;" parent="swimlane-container" source="act-notify" target="act-confirm" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="e-invalid" value="[invalid]" style="endArrow=block;endFill=1;edgeStyle=orthogonalEdgeStyle;rounded=0;fontSize=10;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" parent="swimlane-container" source="decision-valid" target="act-place" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="note1" value="Parallel execution:&#xa;Invoice and Shipment&#xa;can proceed&#xa;simultaneously" style="shape=note;strokeWidth=1;fontSize=10;size=15;fillColor=#ffffcc;strokeColor=#999966;" parent="swimlane-container" vertex="1"><mxGeometry x="700" y="200" width="120" height="70" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
