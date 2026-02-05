# Component Diagram

Shows system component organization, interfaces, and dependencies.

## Key Elements

| Element | Style | Description |
|---------|-------|-------------|
| Component | `html=1;dropTarget=0` + nested `shape=module` | Rectangle with module icon |
| Module icon | `shape=module;jettyWidth=8;jettyHeight=4` | Two small rectangles |
| Port | `html=1;rounded=0` (small square) | Interaction point on component boundary |
| Provided interface | `ellipse;aspect=fixed` (lollipop) | Service offered by component |
| Required interface | `endArrow=halfCircle;endFill=0` (socket) | Service needed by component |
| Ball-socket assembly | `endArrow=oval` + `endArrow=halfCircle` | Direct interface connection |
| Dependency | `dashed=1;endArrow=open;endFill=0` | Component depends on another |
| Delegate | `<<delegate>>` label on connection | Port delegates to internal interface |
| Subsystem | Large component containing others | Container with stereotype |

## Interface Notations

```
  ○───     Provided interface (lollipop) - "I provide this"
  ───◗     Required interface (socket) - "I need this"
  ○──◗     Ball-socket assembly - direct connection
```

## Example

E-commerce system with ports, interfaces, and internal components:

```drawio
<mxfile><diagram id="component-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="680" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="store" value="«component»&#xa;&lt;b&gt;:OnlineStore&lt;/b&gt;" style="html=1;dropTarget=0;whiteSpace=wrap;verticalAlign=top;align=left;spacingTop=5;spacingLeft=10;fillColor=#f5f5f5;strokeColor=#666666;fontSize=11;" parent="1" vertex="1"><mxGeometry x="110" y="60" width="420" height="260" as="geometry"/></mxCell>
  <mxCell id="store-icon" value="" style="shape=module;jettyWidth=8;jettyHeight=4;" parent="store" vertex="1"><mxGeometry x="1" width="20" height="20" relative="1" as="geometry"><mxPoint x="-27" y="7" as="offset"/></mxGeometry></mxCell>
  <mxCell id="port-ext" value="" style="html=1;rounded=0;" parent="1" vertex="1"><mxGeometry x="95" y="128" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="iface-ext" value="OrderSubmission" style="ellipse;html=1;fontSize=9;align=center;fillColor=none;points=[];aspect=fixed;resizable=0;verticalAlign=top;labelPosition=center;verticalLabelPosition=bottom;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="39" y="131" width="8" height="8" as="geometry"/></mxCell>
  <mxCell id="iface-ext-line" value="" style="endArrow=none;html=1;rounded=0;" parent="1" source="port-ext" target="iface-ext" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="order" value="«component»&#xa;&lt;b&gt;:Order&lt;/b&gt;" style="html=1;dropTarget=0;whiteSpace=wrap;fontSize=11;fillColor=#fff2cc;strokeColor=#d6b656;" parent="1" vertex="1"><mxGeometry x="170" y="120" width="130" height="55" as="geometry"/></mxCell>
  <mxCell id="order-icon" value="" style="shape=module;jettyWidth=8;jettyHeight=4;" parent="order" vertex="1"><mxGeometry x="1" width="20" height="20" relative="1" as="geometry"><mxPoint x="-27" y="7" as="offset"/></mxGeometry></mxCell>
  <mxCell id="port-order-l" value="" style="html=1;rounded=0;" parent="1" vertex="1"><mxGeometry x="162" y="140" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="iface-order" value="" style="ellipse;html=1;fontSize=9;align=center;fillColor=none;points=[];aspect=fixed;resizable=0;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="145" y="143" width="8" height="8" as="geometry"/></mxCell>
  <mxCell id="iface-order-line" value="" style="endArrow=none;html=1;rounded=0;" parent="1" source="port-order-l" target="iface-order" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="delegate1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=none;endFill=0;" parent="1" source="iface-order" target="port-ext" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="149" y="120"/><mxPoint x="102" y="120"/></Array></mxGeometry></mxCell>
  <mxCell id="delegate1-label" value="«delegate»" style="edgeLabel;html=1;align=center;verticalAlign=bottom;resizable=0;points=[];fontSize=8;" parent="delegate1" vertex="1" connectable="0"><mxGeometry x="-0.1" relative="1" as="geometry"><mxPoint y="-5" as="offset"/></mxGeometry></mxCell>
  <mxCell id="port-order-r" value="" style="html=1;rounded=0;" parent="1" vertex="1"><mxGeometry x="300" y="140" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="customer" value="«component»&#xa;&lt;b&gt;:Customer&lt;/b&gt;" style="html=1;dropTarget=0;whiteSpace=wrap;fontSize=11;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="370" y="120" width="130" height="55" as="geometry"/></mxCell>
  <mxCell id="customer-icon" value="" style="shape=module;jettyWidth=8;jettyHeight=4;" parent="customer" vertex="1"><mxGeometry x="1" width="20" height="20" relative="1" as="geometry"><mxPoint x="-27" y="7" as="offset"/></mxGeometry></mxCell>
  <mxCell id="port-customer" value="" style="html=1;rounded=0;" parent="1" vertex="1"><mxGeometry x="362" y="140" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="iface-person" value="Person" style="ellipse;whiteSpace=wrap;html=1;align=center;aspect=fixed;fillColor=none;strokeColor=none;resizable=0;fontSize=9;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;" parent="1" vertex="1"><mxGeometry x="335" y="143" width="10" height="10" as="geometry"/></mxCell>
  <mxCell id="socket-person" style="rounded=0;html=1;endArrow=halfCircle;endFill=0;endSize=6;strokeWidth=1;curved=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;" parent="1" source="port-order-r" target="iface-person" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ball-person" style="rounded=0;html=1;endArrow=oval;endFill=0;endSize=10;strokeWidth=1;curved=1;exitX=0;exitY=0.5;exitDx=0;exitDy=0;" parent="1" source="port-customer" target="iface-person" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="product" value="«component»&#xa;&lt;b&gt;:Product&lt;/b&gt;" style="html=1;dropTarget=0;whiteSpace=wrap;fontSize=11;fillColor=#d5e8d4;strokeColor=#82b366;" parent="1" vertex="1"><mxGeometry x="170" y="240" width="130" height="55" as="geometry"/></mxCell>
  <mxCell id="product-icon" value="" style="shape=module;jettyWidth=8;jettyHeight=4;" parent="product" vertex="1"><mxGeometry x="1" width="20" height="20" relative="1" as="geometry"><mxPoint x="-27" y="7" as="offset"/></mxGeometry></mxCell>
  <mxCell id="port-order-b" value="" style="html=1;rounded=0;aspect=fixed;" parent="1" vertex="1"><mxGeometry x="227" y="175" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="port-product" value="" style="html=1;rounded=0;" parent="1" vertex="1"><mxGeometry x="227" y="232" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="iface-product" value="OrderableProduct" style="ellipse;whiteSpace=wrap;html=1;align=left;aspect=fixed;fillColor=none;strokeColor=none;resizable=0;fontSize=9;labelPosition=right;verticalLabelPosition=middle;verticalAlign=middle;" parent="1" vertex="1"><mxGeometry x="230" y="205" width="10" height="10" as="geometry"/></mxCell>
  <mxCell id="socket-product" style="rounded=0;html=1;endArrow=halfCircle;endFill=0;endSize=6;strokeWidth=1;curved=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" parent="1" source="port-order-b" target="iface-product" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ball-product" style="rounded=0;html=1;endArrow=oval;endFill=0;endSize=10;strokeWidth=1;curved=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;" parent="1" source="port-product" target="iface-product" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="port-customer-b" value="" style="html=1;rounded=0;aspect=fixed;" parent="1" vertex="1"><mxGeometry x="427" y="175" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="account" value="«component»&#xa;&lt;b&gt;:Account&lt;/b&gt;" style="html=1;dropTarget=0;whiteSpace=wrap;fontSize=11;fillColor=#e1d5e7;strokeColor=#9673a6;" parent="1" vertex="1"><mxGeometry x="600" y="170" width="130" height="55" as="geometry"/></mxCell>
  <mxCell id="account-icon" value="" style="shape=module;jettyWidth=8;jettyHeight=4;" parent="account" vertex="1"><mxGeometry x="1" width="20" height="20" relative="1" as="geometry"><mxPoint x="-27" y="7" as="offset"/></mxGeometry></mxCell>
  <mxCell id="port-account" value="" style="html=1;rounded=0;" parent="1" vertex="1"><mxGeometry x="592" y="190" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="iface-account" value="" style="ellipse;html=1;fontSize=9;align=center;fillColor=none;points=[];aspect=fixed;resizable=0;strokeColor=#000000;" parent="1" vertex="1"><mxGeometry x="560" y="193" width="8" height="8" as="geometry"/></mxCell>
  <mxCell id="iface-account-line" value="" style="endArrow=none;html=1;rounded=0;" parent="1" source="port-account" target="iface-account" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="port-store-r" value="" style="html=1;rounded=0;aspect=fixed;" parent="1" vertex="1"><mxGeometry x="522" y="190" width="15" height="15" as="geometry"/></mxCell>
  <mxCell id="iface-account-mid" value="Account" style="ellipse;whiteSpace=wrap;html=1;align=right;aspect=fixed;fillColor=none;strokeColor=none;resizable=0;fontSize=9;labelPosition=left;verticalLabelPosition=middle;verticalAlign=middle;" parent="1" vertex="1"><mxGeometry x="430" y="200" width="10" height="10" as="geometry"/></mxCell>
  <mxCell id="socket-account" style="rounded=0;html=1;endArrow=halfCircle;endFill=0;endSize=6;strokeWidth=1;curved=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" parent="1" source="port-customer-b" target="iface-account-mid" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="delegate2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=none;endFill=0;" parent="1" source="iface-account-mid" target="port-store-r" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="435" y="230"/><mxPoint x="530" y="230"/></Array></mxGeometry></mxCell>
  <mxCell id="delegate2-label" value="«delegate»" style="edgeLabel;html=1;align=center;verticalAlign=top;resizable=0;points=[];fontSize=8;" parent="delegate2" vertex="1" connectable="0"><mxGeometry x="0.2" relative="1" as="geometry"><mxPoint y="5" as="offset"/></mxGeometry></mxCell>
  <mxCell id="conn-ext" style="edgeStyle=none;curved=1;rounded=0;html=1;endArrow=none;endFill=0;dashed=1;" parent="1" source="port-store-r" target="iface-account" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Style Patterns

| Pattern | Style Key |
|---------|-----------|
| Component with icon | Parent `dropTarget=0` + child `shape=module` |
| Port square | `html=1;rounded=0` small square (8-16px) |
| Provided (ball) | `endArrow=oval;endFill=0;endSize=10` |
| Required (socket) | `endArrow=halfCircle;endFill=0;endSize=6` |
| Delegate | `<<delegate>>` label + orthogonal edge |
| Subsystem | Large component with `<<subsystem>>` stereotype |
