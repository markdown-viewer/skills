# Use Case Diagram

Describes system functional requirements and user interactions.

## Key Elements

- **Actor**: `shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top`
- **Use Case**: `ellipse` - can use different colors to distinguish function types
- **System boundary**: Rectangle with `dashed=1` border
- **Association**: `endArrow=none` - solid line without arrow
- **Include**: `dashed=1;dashPattern=1 4;endArrow=open;endFill=0` with `«include»` label
- **Extend**: Same as include, with `«extend»` label, arrow points to base use case

## Example

E-commerce system use cases showing multiple actor types, system actors, database, and various relationship types:

```drawio
<mxfile><diagram id="use-case-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1169" pageHeight="827" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="boundary" value="E-Commerce System" style="shape=rect;html=1;whiteSpace=wrap;verticalAlign=top;fontStyle=1;align=left;spacingLeft=10;strokeWidth=2;dashed=1;fontSize=14;" parent="1" vertex="1"><mxGeometry x="140" y="30" width="480" height="500" as="geometry"/></mxCell>
  <mxCell id="customer" value="Customer" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="50" y="150" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="guest" value="Guest" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="50" y="320" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="admin" value="Admin" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="680" y="80" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="system" value="System" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="680" y="200" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="payment-gw" value="Payment&#xa;Gateway" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="680" y="320" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="shipping-api" value="Shipping&#xa;API" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fillColor=#f8cecc;strokeColor=#b85450;" parent="1" vertex="1"><mxGeometry x="680" y="440" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="database" value="Product&#xa;Database" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="730" y="200" width="60" height="70" as="geometry"/></mxCell>
  <mxCell id="uc-browse" value="Browse Products" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="60" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-search" value="Search Products" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="120" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-cart" value="Add to Cart" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="180" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-checkout" value="Checkout" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="240" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-register" value="Register" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="300" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-login" value="Login" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="360" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-history" value="View Order History" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="180" y="420" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-verify-pay" value="Verify Payment" style="ellipse;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="360" y="220" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="uc-calc-ship" value="Calculate Shipping" style="ellipse;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="360" y="280" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="uc-coupon" value="Apply Coupon" style="ellipse;whiteSpace=wrap;html=1;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="360" y="340" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="uc-email" value="Send Email" style="ellipse;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="360" y="400" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="uc-auth" value="Authenticate" style="ellipse;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="360" y="160" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="uc-manage-prod" value="Manage Products" style="ellipse;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="490" y="60" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-manage-order" value="Manage Orders" style="ellipse;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="490" y="120" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-reports" value="View Reports" style="ellipse;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="490" y="180" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="uc-track" value="Track Shipment" style="ellipse;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="490" y="460" width="110" height="45" as="geometry"/></mxCell>
  <mxCell id="a-cust-browse" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-browse" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-search" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-search" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-cart" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-cart" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-checkout" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-checkout" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-register" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-register" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-login" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-login" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-history" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-history" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-admin-prod" style="endArrow=none;html=1;rounded=0;" parent="1" source="admin" target="uc-manage-prod" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-admin-order" style="endArrow=none;html=1;rounded=0;" parent="1" source="admin" target="uc-manage-order" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-admin-reports" style="endArrow=none;html=1;rounded=0;" parent="1" source="admin" target="uc-reports" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-sys-auth" style="endArrow=none;html=1;rounded=0;" parent="1" source="system" target="uc-auth" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-sys-email" style="endArrow=none;html=1;rounded=0;" parent="1" source="system" target="uc-email" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-sys-db" style="endArrow=none;html=1;rounded=0;" parent="1" source="system" target="database" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-pay-verify" style="endArrow=none;html=1;rounded=0;" parent="1" source="payment-gw" target="uc-verify-pay" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-ship-calc" style="endArrow=none;html=1;rounded=0;" parent="1" source="shipping-api" target="uc-calc-ship" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-ship-track" style="endArrow=none;html=1;rounded=0;" parent="1" source="shipping-api" target="uc-track" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-cust-track" style="endArrow=none;html=1;rounded=0;" parent="1" source="customer" target="uc-track" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="inc-checkout-pay" value="«include»" style="endArrow=open;endFill=0;dashed=1;dashPattern=1 4;html=1;rounded=0;fontSize=10;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="uc-checkout" target="uc-verify-pay" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="inc-checkout-ship" value="«include»" style="endArrow=open;endFill=0;dashed=1;dashPattern=1 4;html=1;rounded=0;fontSize=10;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="uc-checkout" target="uc-calc-ship" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="inc-login-auth" value="«include»" style="endArrow=open;endFill=0;dashed=1;dashPattern=1 4;html=1;rounded=0;fontSize=10;exitX=1;exitY=0.3;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="uc-login" target="uc-auth" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="inc-register-email" value="«include»" style="endArrow=open;endFill=0;dashed=1;dashPattern=1 4;html=1;rounded=0;fontSize=10;exitX=1;exitY=0.7;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="uc-register" target="uc-email" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ext-coupon-checkout" value="«extend»" style="endArrow=open;endFill=0;dashed=1;dashPattern=1 4;html=1;rounded=0;fontSize=10;exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=1;entryY=0.8;entryDx=0;entryDy=0;" parent="1" source="uc-coupon" target="uc-checkout" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="gen-guest" value="" style="endArrow=block;endFill=0;html=1;rounded=0;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" parent="1" source="guest" target="customer" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-guest-browse" style="endArrow=none;html=1;rounded=0;dashed=1;" parent="1" source="guest" target="uc-browse" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="a-guest-search" style="endArrow=none;html=1;rounded=0;dashed=1;" parent="1" source="guest" target="uc-search" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="prec-login-history" value="precedes" style="endArrow=classic;html=1;dashed=1;dashPattern=1 4;rounded=0;fontSize=10;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" parent="1" source="uc-login" target="uc-history" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="note" value="Legend:&#xa;Green = Customer actions&#xa;Blue = Admin/System&#xa;Yellow = Included UC&#xa;Purple = Extended UC&#xa;Red = External systems" style="shape=note;whiteSpace=wrap;html=1;backgroundOutline=1;darkOpacity=0.05;fillColor=#f5f5f5;strokeColor=#666666;fontColor=#333333;fontSize=10;align=left;spacingLeft=5;" parent="1" vertex="1"><mxGeometry x="730" y="30" width="130" height="100" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
