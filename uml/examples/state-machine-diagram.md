# State Machine Diagram

Shows state changes of an object during its lifecycle.

## Key Elements

- **State**: `rounded=1;fillColor=<color>` - rounded rectangle with colors
- **Initial state**: `ellipse;shape=startState;fillColor=#000000` - solid black circle
- **Final state**: `ellipse;shape=endState;fillColor=#000000` - circle with outer ring
- **Transition**: `endArrow=open;endSize=8` with text label
- **Composite state**: `swimlane;rounded=1;arcSize=18` - container with title

## State Colors

| State | Fill/Stroke |
|-------|-------------|
| Pending | `#dae8fc;#6c8ebf` (blue) |
| Success | `#d5e8d4;#82b366` (green) |
| Error/Cancel | `#f8cecc;#b85450` (red) |
| Processing | `#fff2cc;#d6b656` (yellow) |
| Complete | `#e1d5e7;#9673a6` (purple) |

## Example

Order processing state machine with composite states and parallel regions:

```drawio
<mxfile><diagram id="state-machine-1" name="Page-1"><mxGraphModel dx="900" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="900" pageHeight="600" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="start" value="" style="ellipse;html=1;shape=startState;fillColor=#000000;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="75" y="20" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="newOrder" value="New Order" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="30" y="80" width="120" height="45" as="geometry"/></mxCell>
  <mxCell id="pending" value="Pending Payment&#xa;entry / sendInvoice()&#xa;exit / logStatus()" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;align=center;" parent="1" vertex="1"><mxGeometry x="20" y="160" width="140" height="60" as="geometry"/></mxCell>
  <mxCell id="cancelled" value="Cancelled" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#f8cecc;strokeColor=#b85450;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="200" y="80" width="100" height="45" as="geometry"/></mxCell>
  <mxCell id="processing" value="Processing" style="swimlane;html=1;rounded=1;arcSize=10;fontStyle=1;fillColor=#fff2cc;strokeColor=#d6b656;startSize=25;" parent="1" vertex="1"><mxGeometry x="200" y="155" width="350" height="160" as="geometry"/></mxCell>
  <mxCell id="verifying" value="Verifying" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#d6b656;" parent="processing" vertex="1"><mxGeometry x="20" y="40" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="packaging" value="Packaging" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#d6b656;" parent="processing" vertex="1"><mxGeometry x="130" y="40" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="shipping" value="Shipping" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#d6b656;" parent="processing" vertex="1"><mxGeometry x="240" y="40" width="90" height="40" as="geometry"/></mxCell>
  <mxCell id="fork" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#000000;strokeColor=none;" parent="processing" vertex="1"><mxGeometry x="145" y="95" width="60" height="5" as="geometry"/></mxCell>
  <mxCell id="notify" value="Notify Customer" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#d6b656;fontSize=10;" parent="processing" vertex="1"><mxGeometry x="70" y="110" width="85" height="35" as="geometry"/></mxCell>
  <mxCell id="inventory" value="Update Inventory" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#d6b656;fontSize=10;" parent="processing" vertex="1"><mxGeometry x="195" y="110" width="85" height="35" as="geometry"/></mxCell>
  <mxCell id="ct1" style="endArrow=open;endSize=8;rounded=0;" parent="processing" source="verifying" target="packaging" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ct2" style="endArrow=open;endSize=8;rounded=0;" parent="processing" source="packaging" target="shipping" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ct3" style="endArrow=open;endSize=8;rounded=0;" parent="processing" source="packaging" target="fork" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ct4" style="endArrow=open;endSize=8;rounded=0;" parent="processing" source="fork" target="notify" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ct5" style="endArrow=open;endSize=8;rounded=0;" parent="processing" source="fork" target="inventory" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="delivered" value="Delivered&#xa;do / trackFeedback()" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;align=center;" parent="1" vertex="1"><mxGeometry x="200" y="350" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="choice" value="" style="rhombus;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="380" y="360" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="completed" value="Completed" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#e1d5e7;strokeColor=#9673a6;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="450" y="350" width="100" height="50" as="geometry"/></mxCell>
  <mxCell id="refund" value="Refund Requested" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="340" y="440" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="end" value="" style="ellipse;html=1;shape=endState;fillColor=#000000;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="485" y="455" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="history" value="H" style="ellipse;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#000000;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="590" y="200" width="30" height="30" as="geometry"/></mxCell>
  <mxCell id="t1" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="start" target="newOrder" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t2" value="submit" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="newOrder" target="pending" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t3" value="cancel" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="newOrder" target="cancelled" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t4" value="paymentReceived" style="endArrow=open;endSize=8;edgeStyle=orthogonalEdgeStyle;rounded=0;" parent="1" source="pending" target="processing" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t5" value="timeout [30 days]" style="endArrow=open;endSize=8;edgeStyle=orthogonalEdgeStyle;rounded=0;" parent="1" source="pending" target="cancelled" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="90" y="140"/><mxPoint x="250" y="140"/></Array></mxGeometry></mxCell>
  <mxCell id="t6" value="shipComplete" style="endArrow=open;endSize=8;edgeStyle=orthogonalEdgeStyle;rounded=0;" parent="1" source="processing" target="delivered" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t7" value="review" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="delivered" target="choice" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t8" value="[satisfied]" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="choice" target="completed" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t9" value="[not satisfied]" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="choice" target="refund" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t10" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="completed" target="end" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t11" value="refundProcessed" style="endArrow=open;endSize=8;rounded=0;" parent="1" source="refund" target="end" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="t12" style="endArrow=open;endSize=8;edgeStyle=orthogonalEdgeStyle;rounded=0;" parent="1" source="cancelled" target="end" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="250" y="60"/><mxPoint x="600" y="60"/><mxPoint x="600" y="470"/></Array></mxGeometry></mxCell>
  <mxCell id="t13" value="restore" style="endArrow=open;endSize=8;dashed=1;rounded=0;" parent="1" source="history" target="processing" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
