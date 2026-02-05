# Sequence Diagram

Shows message interactions between objects in chronological order.

## Key Elements

- **Lifeline**: `shape=umlLifeline;perimeter=lifelinePerimeter;container=1;collapsible=0`
- **Actor lifeline**: `shape=umlLifeline;participant=umlActor` (stick figure)
- **Entity lifeline**: `shape=umlLifeline;participant=umlEntity` (circle with underline)
- **Activation box**: Nested inside lifeline, `perimeter=orthogonalPerimeter`
- **UML Frame**: `shape=umlFrame;whiteSpace=wrap` for diagram boundary
- **Destroy marker**: `shape=umlDestroy;strokeWidth=3` (X symbol)

## Message Types

| Message | Style | Description |
|---------|-------|-------------|
| Synchronous | `endArrow=block` | Solid line, filled arrow |
| Asynchronous | `endArrow=open` | Solid line, open arrow |
| Return | `dashed=1;endArrow=open;endSize=8` | Dashed line |
| Create | `endArrow=open` + new lifeline | Creates object |
| Found | `startArrow=oval;startSize=8` | Message from outside |

## Combined Fragments

| Fragment | Description |
|----------|-------------|
| `alt` | Alternative (if-else) |
| `opt` | Optional (if) |
| `loop` | Loop iteration |
| `par` | Parallel execution |
| `break` | Break out of loop |

## ⚠️ Important Notes

**Message Connection Best Practice:**

When drawing messages between lifelines, **always use absolute coordinates** with `sourcePoint` and `targetPoint` instead of `source` and `target` attributes referencing activation box IDs.

❌ **Wrong** - Using source/target references (positions may be incorrect):
```xml
<mxCell id="msg1" source="client-act" target="server-act" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
```

✅ **Correct** - Using absolute coordinates:
```xml
<mxCell id="msg1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="70" y="130" as="sourcePoint"/><mxPoint x="205" y="130" as="targetPoint"/></mxGeometry></mxCell>
```

**Why?** Activation boxes are nested inside lifeline containers. Using `source`/`target` references causes Draw.io to calculate positions relative to parent containers, often resulting in misaligned message arrows.

## Example

E-commerce order processing with multiple participants and fragments:

```drawio
<mxfile><diagram id="sequence-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="frame" value="sd Order Processing" style="shape=umlFrame;whiteSpace=wrap;html=1;width=130;height=30;boundedLbl=1;verticalAlign=middle;align=left;spacingLeft=5;fillColor=#f5f5f5;fontColor=#333333;strokeColor=#666666;" parent="1" vertex="1"><mxGeometry x="20" y="10" width="730" height="490" as="geometry"/></mxCell>
  <mxCell id="customer" value=":Customer" style="shape=umlLifeline;participant=umlActor;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;verticalAlign=top;spacingTop=36;outlineConnect=0;size=40;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="60" y="50" width="20" height="430" as="geometry"/></mxCell>
  <mxCell id="customer-act" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#f8cecc;strokeColor=#b85450;" parent="customer" vertex="1"><mxGeometry x="5" y="70" width="10" height="340" as="geometry"/></mxCell>
  <mxCell id="webui" value=":WebUI" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="1" vertex="1"><mxGeometry x="160" y="50" width="100" height="430" as="geometry"/></mxCell>
  <mxCell id="webui-act" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#ffe6cc;strokeColor=#d79b00;" parent="webui" vertex="1"><mxGeometry x="45" y="80" width="10" height="320" as="geometry"/></mxCell>
  <mxCell id="orderservice" value=":OrderService" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="320" y="50" width="100" height="430" as="geometry"/></mxCell>
  <mxCell id="order-act" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="orderservice" vertex="1"><mxGeometry x="45" y="100" width="10" height="280" as="geometry"/></mxCell>
  <mxCell id="order-self-act" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="orderservice" vertex="1"><mxGeometry x="50" y="120" width="10" height="30" as="geometry"/></mxCell>
  <mxCell id="payment" value=":PaymentGateway" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;outlineConnect=0;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="480" y="50" width="110" height="430" as="geometry"/></mxCell>
  <mxCell id="payment-act" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#d5e8d4;strokeColor=#82b366;" parent="payment" vertex="1"><mxGeometry x="50" y="200" width="10" height="80" as="geometry"/></mxCell>
  <mxCell id="database" value=":OrderDB" style="shape=umlLifeline;participant=umlEntity;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;collapsible=0;recursiveResize=0;verticalAlign=top;spacingTop=36;outlineConnect=0;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="650" y="50" width="40" height="430" as="geometry"/></mxCell>
  <mxCell id="db-act" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="database" vertex="1"><mxGeometry x="15" y="310" width="10" height="50" as="geometry"/></mxCell>
  <mxCell id="msg1" value="1: placeOrder()" style="html=1;verticalAlign=bottom;startArrow=oval;endArrow=block;startSize=8;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="70" y="130" as="sourcePoint"/><mxPoint x="205" y="130" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg2" value="1.1: createOrder(items)" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="215" y="150" as="sourcePoint"/><mxPoint x="365" y="150" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg3" value="1.1.1: validateOrder()" style="edgeStyle=orthogonalEdgeStyle;html=1;align=left;spacingLeft=2;endArrow=block;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="375" y="170" as="sourcePoint"/><mxPoint x="380" y="195" as="targetPoint"/><Array as="points"><mxPoint x="405" y="170"/><mxPoint x="405" y="195"/></Array></mxGeometry></mxCell>
  <mxCell id="alt-frame" value="alt" style="shape=umlFrame;whiteSpace=wrap;html=1;fillColor=#f5f5f5;fontColor=#333333;strokeColor=#666666;" parent="1" vertex="1"><mxGeometry x="200" y="210" width="510" height="220" as="geometry"/></mxCell>
  <mxCell id="alt-cond1" value="[payment valid]" style="text;html=1;align=left;verticalAlign=middle;resizable=0;points=[];fontSize=11;fontStyle=2;" parent="1" vertex="1"><mxGeometry x="205" y="235" width="90" height="20" as="geometry"/></mxCell>
  <mxCell id="alt-sep" value="" style="endArrow=none;dashed=1;html=1;rounded=0;" parent="1" edge="1"><mxGeometry width="50" height="50" relative="1" as="geometry"><mxPoint x="200" y="340" as="sourcePoint"/><mxPoint x="710" y="340" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="alt-cond2" value="[else]" style="text;html=1;align=left;verticalAlign=middle;resizable=0;points=[];fontSize=11;fontStyle=2;" parent="1" vertex="1"><mxGeometry x="205" y="345" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="msg4" value="1.1.2: processPayment(amount)" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="375" y="250" as="sourcePoint"/><mxPoint x="530" y="250" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg5" value="paymentResult" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="530" y="320" as="sourcePoint"/><mxPoint x="375" y="320" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg6" value="1.1.3: saveOrder(order)" style="html=1;verticalAlign=bottom;endArrow=block;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="375" y="360" as="sourcePoint"/><mxPoint x="665" y="360" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg7" value="orderId" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="665" y="400" as="sourcePoint"/><mxPoint x="375" y="400" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg8" value="paymentError" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;rounded=0;strokeColor=#FF0000;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="365" y="370" as="sourcePoint"/><mxPoint x="215" y="370" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg9" value="orderConfirmation" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;rounded=0;" parent="1" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="205" y="440" as="sourcePoint"/><mxPoint x="75" y="440" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="note1" value="Payment gateway&#xa;handles credit card&#xa;processing" style="shape=note;strokeWidth=1;fontSize=11;size=20;whiteSpace=wrap;fillColor=#ffffcc;strokeColor=#999966;fontColor=#333333;" parent="1" vertex="1"><mxGeometry x="580" y="100" width="120" height="60" as="geometry"/></mxCell>
  <mxCell id="note1-link" value="" style="endArrow=none;dashed=1;strokeWidth=1;rounded=0;" parent="1" edge="1"><mxGeometry width="160" relative="1" as="geometry"><mxPoint x="540" y="130" as="sourcePoint"/><mxPoint x="580" y="130" as="targetPoint"/></mxGeometry></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
