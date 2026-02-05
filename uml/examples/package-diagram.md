# Package Diagram

**Purpose**: Shows the modular organization structure of a system.

**Key Elements**:
- Package: Folder shape `shape=folder;tabWidth=80;tabHeight=20;tabPosition=left`
- Package container: `boundedLbl=1;labelInHeader=1;container=1` - can contain child elements
- Nested package: Smaller folder, placed within parent's geometry
- Dependency edge: `dashed=1;endArrow=open;endFill=0;curved=1`
- Relationship labels: `«use»`, `«import»`, `«access»`, `«merge»`

## Example

E-commerce system module structure with nested packages and multiple dependency types:

```drawio
<mxfile><diagram id="package-diagram-1" name="Page-1"><mxGraphModel dx="950" dy="650" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="950" pageHeight="450" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="external" value="External Services" style="shape=folder;fontStyle=1;tabWidth=110;tabHeight=25;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;fillColor=#f5f5f5;strokeColor=#666666;fontColor=#333333;" parent="1" vertex="1"><mxGeometry x="20" y="20" width="280" height="80" as="geometry"/></mxCell>
  <mxCell id="shipping" value="Shipping" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="external" vertex="1"><mxGeometry x="15" y="40" width="75" height="30" as="geometry"/></mxCell>
  <mxCell id="analytics" value="Analytics" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="external" vertex="1"><mxGeometry x="103" y="40" width="75" height="30" as="geometry"/></mxCell>
  <mxCell id="email" value="Email" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="external" vertex="1"><mxGeometry x="191" y="40" width="75" height="30" as="geometry"/></mxCell>
  <mxCell id="shopfloor" value="Shop Floor" style="shape=folder;fontStyle=1;tabWidth=110;tabHeight=25;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;fillColor=#e1d5e7;strokeColor=#9673a6;fontColor=#000000;" parent="1" vertex="1"><mxGeometry x="320" y="20" width="340" height="80" as="geometry"/></mxCell>
  <mxCell id="displays" value="Displays" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="shopfloor" vertex="1"><mxGeometry x="15" y="40" width="80" height="30" as="geometry"/></mxCell>
  <mxCell id="stock" value="Stock on Shelves" style="shape=folder;fontStyle=0;tabWidth=50;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="shopfloor" vertex="1"><mxGeometry x="115" y="40" width="115" height="30" as="geometry"/></mxCell>
  <mxCell id="roster" value="Roster" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="shopfloor" vertex="1"><mxGeometry x="250" y="40" width="75" height="30" as="geometry"/></mxCell>
  <mxCell id="onlinestore" value="Online Store" style="shape=folder;fontStyle=1;tabWidth=110;tabHeight=25;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;fillColor=#d5e8d4;strokeColor=#82b366;fontColor=#000000;" parent="1" vertex="1"><mxGeometry x="20" y="120" width="350" height="120" as="geometry"/></mxCell>
  <mxCell id="interface" value="Interface" style="shape=folder;fontStyle=1;tabWidth=60;tabHeight=18;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;" parent="onlinestore" vertex="1"><mxGeometry x="15" y="40" width="200" height="65" as="geometry"/></mxCell>
  <mxCell id="website" value="Website" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="interface" vertex="1"><mxGeometry x="10" y="28" width="80" height="28" as="geometry"/></mxCell>
  <mxCell id="mobileapp" value="Mobile App" style="shape=folder;fontStyle=0;tabWidth=50;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="interface" vertex="1"><mxGeometry x="105" y="28" width="85" height="28" as="geometry"/></mxCell>
  <mxCell id="cart" value="Shopping Cart" style="shape=folder;fontStyle=0;tabWidth=55;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="onlinestore" vertex="1"><mxGeometry x="230" y="40" width="105" height="30" as="geometry"/></mxCell>
  <mxCell id="custservice" value="Customer Service" style="shape=folder;fontStyle=0;tabWidth=55;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="onlinestore" vertex="1"><mxGeometry x="230" y="80" width="105" height="30" as="geometry"/></mxCell>
  <mxCell id="payment" value="Payment" style="shape=folder;fontStyle=1;tabWidth=50;tabHeight=12;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;fillColor=#f8cecc;strokeColor=#b85450;fontColor=#000000;" parent="1" vertex="1"><mxGeometry x="400" y="130" width="100" height="40" as="geometry"/></mxCell>
  <mxCell id="auth" value="Authorisation" style="shape=folder;fontStyle=1;tabWidth=100;tabHeight=25;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;fillColor=#f8cecc;strokeColor=#b85450;fontColor=#000000;" parent="1" vertex="1"><mxGeometry x="530" y="110" width="170" height="110" as="geometry"/></mxCell>
  <mxCell id="payauth" value="Payment Auth" style="shape=folder;fontStyle=0;tabWidth=55;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="auth" vertex="1"><mxGeometry x="15" y="40" width="140" height="28" as="geometry"/></mxCell>
  <mxCell id="accauth" value="Account Auth" style="shape=folder;fontStyle=0;tabWidth=55;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="auth" vertex="1"><mxGeometry x="15" y="73" width="140" height="28" as="geometry"/></mxCell>
  <mxCell id="databases" value="Databases" style="shape=folder;fontStyle=1;tabWidth=110;tabHeight=25;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;fillColor=#ffe6cc;strokeColor=#d79b00;fontColor=#000000;" parent="1" vertex="1"><mxGeometry x="20" y="270" width="680" height="80" as="geometry"/></mxCell>
  <mxCell id="suppliers" value="Suppliers" style="shape=folder;fontStyle=0;tabWidth=45;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="databases" vertex="1"><mxGeometry x="15" y="40" width="90" height="30" as="geometry"/></mxCell>
  <mxCell id="products" value="Products" style="shape=folder;fontStyle=0;tabWidth=45;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="databases" vertex="1"><mxGeometry x="120" y="40" width="90" height="30" as="geometry"/></mxCell>
  <mxCell id="inventory" value="Inventory" style="shape=folder;fontStyle=0;tabWidth=45;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="databases" vertex="1"><mxGeometry x="225" y="40" width="90" height="30" as="geometry"/></mxCell>
  <mxCell id="orders" value="Orders" style="shape=folder;fontStyle=0;tabWidth=45;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="databases" vertex="1"><mxGeometry x="330" y="40" width="90" height="30" as="geometry"/></mxCell>
  <mxCell id="customers" value="Customers" style="shape=folder;fontStyle=0;tabWidth=50;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="databases" vertex="1"><mxGeometry x="435" y="40" width="100" height="30" as="geometry"/></mxCell>
  <mxCell id="staff" value="Staff" style="shape=folder;fontStyle=0;tabWidth=40;tabHeight=10;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;" parent="databases" vertex="1"><mxGeometry x="550" y="40" width="80" height="30" as="geometry"/></mxCell>
  <mxCell id="dep1" value="«merge»" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;verticalAlign=bottom;" parent="1" source="interface" target="cart" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep2" value="«use»" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;verticalAlign=bottom;" parent="1" source="onlinestore" target="payment" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep3" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;" parent="1" source="payment" target="auth" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep4" value="«access»" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;verticalAlign=bottom;exitX=0;exitY=0.5;exitDx=0;exitDy=0;exitPerimeter=0;" parent="1" source="payment" target="cart" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep5" value="«needs»" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;verticalAlign=bottom;entryX=0.1;entryY=0;entryDx=0;entryDy=0;entryPerimeter=0;" parent="1" source="onlinestore" target="databases" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep6" value="«import»" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;verticalAlign=bottom;" parent="1" source="payment" target="orders" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep7" value="«needs»" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;verticalAlign=bottom;" parent="1" source="accauth" target="customers" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep8" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;" parent="1" source="inventory" target="products" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="dep9" style="endArrow=open;endFill=0;dashed=1;dashPattern=8 8;html=1;curved=1;fontSize=10;" parent="1" source="inventory" target="orders" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>  
</root></mxGraphModel></diagram></mxfile>
```
