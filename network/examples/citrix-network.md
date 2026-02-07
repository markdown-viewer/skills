# Citrix Network Diagram

Shows a Citrix Virtual Apps and Desktops infrastructure with NetScaler Gateway.

## Key Elements

- **NetScaler Gateway**: `shape=mxgraph.citrix.netscaler_gateway`
- **Delivery Controller**: `shape=mxgraph.citrix2.delivery_controller`
- **StoreFront**: `shape=mxgraph.citrix2.storefront`
- **VDA (Virtual Delivery Agent)**: `shape=mxgraph.citrix2.vda`
- **XenServer**: `shape=mxgraph.citrix.xenserver`
- **License Server**: `shape=mxgraph.citrix.license_server`

## Citrix Architecture Components

| Component | Icon | Purpose |
|-----------|------|---------|
| NetScaler | `mxgraph.citrix.netscaler_gateway` | Load balancing, SSL VPN |
| StoreFront | `mxgraph.citrix2.storefront` | App/desktop aggregation |
| Delivery Controller | `mxgraph.citrix2.delivery_controller` | Broker sessions |
| VDA | `mxgraph.citrix2.vda` | Virtual desktop agent |
| Director | `mxgraph.citrix2.director` | Monitoring |

## Example

Citrix Virtual Apps and Desktops deployment:

```drawio
<mxfile><diagram id="citrix-network" name="Citrix"><mxGraphModel dx="1000" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="900" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-users" value="External Users" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#d5e8d4;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="40" width="200" height="160" as="geometry"/></mxCell>
  <mxCell id="zone-dmz" value="DMZ" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#fff2cc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="300" y="40" width="200" height="160" as="geometry"/></mxCell>
  <mxCell id="zone-infra" value="Citrix Infrastructure" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#dae8fc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="560" y="40" width="340" height="300" as="geometry"/></mxCell>
  <mxCell id="zone-vda" value="Virtual Desktops" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#e1d5e7;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="560" y="380" width="340" height="160" as="geometry"/></mxCell>
  <mxCell id="zone-backend" value="Backend Services" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#f8cecc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="380" width="460" height="160" as="geometry"/></mxCell>
  <mxCell id="internet" value="" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#23445D;fillColor=#ffffff;" parent="1" vertex="1"><mxGeometry x="250" y="85" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="user-laptop" value="" style="shape=mxgraph.citrix.laptop_1;html=1;fillColor=#6D9C36;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="80" width="55" height="40" as="geometry"/></mxCell>
  <mxCell id="user-mobile" value="" style="shape=mxgraph.citrix.cell_phone;html=1;fillColor=#6D9C36;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="130" y="75" width="30" height="50" as="geometry"/></mxCell>
  <mxCell id="user-thin" value="" style="shape=mxgraph.citrix2.thin_client;html=1;fillColor=#6D9C36;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="60" y="140" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="user-home" value="" style="shape=mxgraph.citrix.home_office;html=1;fillColor=#6D9C36;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="130" y="135" width="55" height="50" as="geometry"/></mxCell>
  <mxCell id="netscaler" value="" style="shape=mxgraph.citrix.netscaler_gateway;html=1;fillColor=#F6921E;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="360" y="80" width="80" height="60" as="geometry"/></mxCell>
  <mxCell id="storefront1" value="" style="shape=mxgraph.citrix2.storefront;html=1;fillColor=#036897;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="590" y="80" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="storefront2" value="" style="shape=mxgraph.citrix2.storefront;html=1;fillColor=#036897;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="660" y="80" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="controller1" value="" style="shape=mxgraph.citrix2.delivery_controller;html=1;fillColor=#036897;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="590" y="170" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="controller2" value="" style="shape=mxgraph.citrix2.delivery_controller;html=1;fillColor=#036897;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="660" y="170" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="director" value="" style="shape=mxgraph.citrix2.director;html=1;fillColor=#036897;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="740" y="80" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="license" value="" style="shape=mxgraph.citrix.license_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="810" y="80" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="pvs" value="" style="shape=mxgraph.citrix.provisioning_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="740" y="170" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="studio" value="" style="shape=mxgraph.citrix2.studio_web_studio;html=1;fillColor=#036897;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="810" y="170" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="xenserver1" value="" style="shape=mxgraph.citrix.xenserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="590" y="270" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="xenserver2" value="" style="shape=mxgraph.citrix.xenserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="660" y="270" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vda1" value="" style="shape=mxgraph.citrix2.vda;html=1;fillColor=#8E44AD;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="590" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vda2" value="" style="shape=mxgraph.citrix2.vda;html=1;fillColor=#8E44AD;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="660" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vda3" value="" style="shape=mxgraph.citrix2.vda;html=1;fillColor=#8E44AD;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="730" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="vda4" value="" style="shape=mxgraph.citrix2.vda;html=1;fillColor=#8E44AD;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="800" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="desktop1" value="" style="shape=mxgraph.citrix2.virtual_desktop;html=1;fillColor=#8E44AD;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="610" y="490" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="desktop2" value="" style="shape=mxgraph.citrix2.virtual_desktop;html=1;fillColor=#8E44AD;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="750" y="490" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="ad-server" value="" style="shape=mxgraph.citrix.directory_server;html=1;fillColor=#C0392B;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="70" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="sql-server" value="" style="shape=mxgraph.citrix.database_server;html=1;fillColor=#C0392B;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="150" y="420" width="50" height="55" as="geometry"/></mxCell>
  <mxCell id="file-server" value="" style="shape=mxgraph.citrix.file_server;html=1;fillColor=#C0392B;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="230" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="dhcp-server" value="" style="shape=mxgraph.citrix.dhcp_server;html=1;fillColor=#C0392B;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="310" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="dns-server" value="" style="shape=mxgraph.citrix.dns_server;html=1;fillColor=#C0392B;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="390" y="420" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="link-laptop-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="user-laptop" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-mobile-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="user-mobile" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-thin-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="user-thin" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-home-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="user-home" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-inet-ns" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#F6921E;" parent="1" source="internet" target="netscaler" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ns-sf1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#036897;" parent="1" source="netscaler" target="storefront1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ns-sf2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#036897;" parent="1" source="netscaler" target="storefront2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sf1-ctrl1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#036897;" parent="1" source="storefront1" target="controller1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sf2-ctrl2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#036897;" parent="1" source="storefront2" target="controller2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ctrl1-xs1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#036897;" parent="1" source="controller1" target="xenserver1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ctrl2-xs2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#036897;" parent="1" source="controller2" target="xenserver2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xs1-vda1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#8E44AD;" parent="1" source="xenserver1" target="vda1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xs1-vda2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#8E44AD;" parent="1" source="xenserver1" target="vda2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xs2-vda3" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#8E44AD;" parent="1" source="xenserver2" target="vda3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xs2-vda4" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#8E44AD;" parent="1" source="xenserver2" target="vda4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda1-d1" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="vda1" target="desktop1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda2-d1" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="vda2" target="desktop1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda3-d2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="vda3" target="desktop2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda4-d2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="vda4" target="desktop2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ctrl-ad" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#C0392B;dashed=1;" parent="1" source="controller1" target="ad-server" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ctrl-sql" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#C0392B;dashed=1;" parent="1" source="controller2" target="sql-server" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-pvs-file" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#C0392B;dashed=1;" parent="1" source="pvs" target="file-server" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

