# Communication Diagram

**Purpose**: Shows interactions between objects, emphasizing structural organization and links rather than time sequence.

## Key Elements

| Element | Style | Description |
|---------|-------|-------------|
| Object | `whiteSpace=wrap;html=1` | Rectangle with `:ClassName` format |
| Actor | `shape=umlActor` | Stick figure for external participant |
| Boundary | `shape=umlBoundary` | Circle with line for UI/interface |
| Control | `shape=umlControl` | Circle with arrow for controller |
| Entity | `shape=umlEntity` | Circle with underline for data/database |
| Link | `curved=1` | Curved line connecting objects |
| Message label | `edgeLabel` | Separate label node attached to edge |
| Self-call | `edgeStyle=orthogonalEdgeStyle` | Loop back to same object |
| Note | `shape=note` | Folded corner rectangle |

## Message Numbering

- **Sequential**: `1, 2, 3...` - messages in order
- **Nested**: `1.1, 1.2, 1.1.1...` - sub-messages within a call
- **Concurrent**: `1a, 1b` - parallel messages at same level
- **Return**: `1.1: result` - optional return value notation

## Example

E-commerce checkout process with multiple object types:

```drawio
<mxfile><diagram id="communication-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="actor" value="Customer" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="40" y="180" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="ui" value="CheckoutUI" style="shape=umlBoundary;whiteSpace=wrap;html=1;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="1" vertex="1"><mxGeometry x="140" y="185" width="100" height="50" as="geometry"/></mxCell>
  <mxCell id="controller" value="CheckoutController" style="shape=umlControl;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="310" y="180" width="80" height="60" as="geometry"/></mxCell>
  <mxCell id="orderDb" value=":OrderDB" style="shape=umlEntity;whiteSpace=wrap;html=1;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="470" y="100" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="inventoryDb" value=":InventoryDB" style="shape=umlEntity;whiteSpace=wrap;html=1;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="470" y="185" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="payment" value=":PaymentService" style="whiteSpace=wrap;html=1;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="460" y="280" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="notification" value=":NotificationService" style="whiteSpace=wrap;html=1;align=center;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="280" y="350" width="120" height="40" as="geometry"/></mxCell>
  <mxCell id="shipping" value=":ShippingService" style="whiteSpace=wrap;html=1;align=center;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="460" y="350" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="msg1" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;" parent="1" source="actor" target="ui" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg1-label" value="1: checkout(cart)" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg1" vertex="1" connectable="0"><mxGeometry x="-0.2" relative="1" as="geometry"><mxPoint y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg2" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;" parent="1" source="ui" target="controller" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg2-label" value="1.1: processCheckout()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg2" vertex="1" connectable="0"><mxGeometry x="-0.1" relative="1" as="geometry"><mxPoint y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="self1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=1;entryY=0.25;entryDx=0;entryDy=0;endArrow=open;endFill=0;" parent="1" source="controller" target="controller" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="350" y="160"/><mxPoint x="400" y="160"/><mxPoint x="400" y="195"/></Array></mxGeometry></mxCell>
  <mxCell id="self1-label" value="1.1.0: validate()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="self1" vertex="1" connectable="0"><mxGeometry x="-0.3" relative="1" as="geometry"><mxPoint x="5" y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg3" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;exitX=1;exitY=0.25;exitDx=0;exitDy=0;" parent="1" source="controller" target="orderDb" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg3-label" value="1.1.1: createOrder()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg3" vertex="1" connectable="0"><mxGeometry x="0.2" relative="1" as="geometry"><mxPoint y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg4" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;" parent="1" source="controller" target="inventoryDb" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg4-label" value="1.1.2: reserveItems()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg4" vertex="1" connectable="0"><mxGeometry x="-0.1" relative="1" as="geometry"><mxPoint y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg5" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;exitX=1;exitY=0.75;exitDx=0;exitDy=0;" parent="1" source="controller" target="payment" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg5-label" value="1.1.3: charge(amount)" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg5" vertex="1" connectable="0"><mxGeometry x="-0.1" relative="1" as="geometry"><mxPoint y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg6" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" parent="1" source="controller" target="notification" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg6-label" value="1.1.4a: sendConfirmation()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg6" vertex="1" connectable="0"><mxGeometry x="-0.2" relative="1" as="geometry"><mxPoint x="-20" y="5" as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg7" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=open;endFill=0;" parent="1" source="payment" target="shipping" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="msg7-label" value="1.1.4b: schedule()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="msg7" vertex="1" connectable="0"><mxGeometry x="-0.2" relative="1" as="geometry"><mxPoint x="10" y="-10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="self2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;exitX=0.75;exitY=1;exitDx=0;exitDy=0;entryX=1;entryY=0.5;entryDx=0;entryDy=0;endArrow=open;endFill=0;" parent="1" source="payment" target="payment" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="535" y="340"/><mxPoint x="580" y="340"/><mxPoint x="580" y="300"/></Array></mxGeometry></mxCell>
  <mxCell id="self2-label" value="1.1.3.1: logTransaction()" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=10;" parent="self2" vertex="1" connectable="0"><mxGeometry x="-0.5" relative="1" as="geometry"><mxPoint x="15" y="10" as="offset"/></mxGeometry></mxCell>
  <mxCell id="link1" style="edgeStyle=none;rounded=0;html=1;endArrow=none;dashed=1;strokeColor=#999999;" parent="1" source="orderDb" target="inventoryDb" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="note1" value="Messages 1.1.4a and 1.1.4b&#xa;execute concurrently" style="shape=note;strokeWidth=1;fontSize=10;size=15;fillColor=#ffffcc;strokeColor=#999966;whiteSpace=wrap;" parent="1" vertex="1"><mxGeometry x="110" y="340" width="130" height="50" as="geometry"/></mxCell>
  <mxCell id="noteLink" style="edgeStyle=none;rounded=0;html=1;endArrow=none;dashed=1;strokeColor=#999966;" parent="1" source="note1" target="notification" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>  
</root></mxGraphModel></diagram></mxfile>
```

## Style Patterns

| Pattern | Usage |
|---------|-------|
| Boundary-Control-Entity | Separate UI, logic, and data objects |
| Concurrent messages | Use `a, b` suffix (e.g., `1.1.4a`, `1.1.4b`) |
| Association link | Dashed line without arrow between related entities |
| Self-call variants | Top loop vs bottom loop for different visual clarity |
| Color coding | Different colors for different stereotypes |
