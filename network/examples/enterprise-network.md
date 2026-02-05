# Enterprise Network Diagram

Shows a multi-tier enterprise network with DMZ, internal zones, and security layers.

## Key Elements

- **Core/Distribution/Access**: Three-tier architecture
- **DMZ**: Demilitarized zone for public services
- **Firewall Layers**: `shape=mxgraph.cisco.security.firewall`, `mxgraph.cisco.misc.asa_5500`
- **Server Farm**: `shape=mxgraph.cisco.servers.standard_host`, `mxgraph.cisco_safe.capability.database`
- **Load Balancer**: `shape=mxgraph.cisco_safe.design.load_balancer`

## Network Tiers

| Tier | Purpose | Devices |
|------|---------|---------|
| Core | High-speed backbone | Core switches, routers |
| Distribution | Policy, routing | L3 switches, firewalls |
| Access | End-user connectivity | Access switches, APs |

## Example

Enterprise network with DMZ, server farm, and user segments:

```drawio
<mxfile><diagram id="enterprise-net" name="Enterprise"><mxGraphModel dx="1000" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="900" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-inet" value="Internet" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#f8cecc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="380" y="20" width="240" height="80" as="geometry"/></mxCell>
  <mxCell id="zone-dmz" value="DMZ" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#fff2cc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="320" y="140" width="360" height="120" as="geometry"/></mxCell>
  <mxCell id="zone-core" value="Core Network" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#dae8fc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="280" y="300" width="440" height="100" as="geometry"/></mxCell>
  <mxCell id="zone-server" value="Server Farm" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#e1d5e7;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="560" y="440" width="220" height="160" as="geometry"/></mxCell>
  <mxCell id="zone-users" value="User Network" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#d5e8d4;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="440" width="480" height="160" as="geometry"/></mxCell>
  <mxCell id="inet-cloud" value="" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#b85450;fillColor=#ffffff;" parent="1" vertex="1"><mxGeometry x="440" y="35" width="120" height="55" as="geometry"/></mxCell>
  <mxCell id="fw-edge" value="" style="shape=mxgraph.cisco.misc.asa_5500;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="475" y="105" width="50" height="30" as="geometry"/></mxCell>
  <mxCell id="dmz-lb" value="" style="shape=mxgraph.cisco_safe.design.load_balancer;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="340" y="170" width="60" height="40" as="geometry"/></mxCell>
  <mxCell id="dmz-web1" value="" style="shape=mxgraph.cisco.servers.www_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="430" y="165" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="dmz-web2" value="" style="shape=mxgraph.cisco.servers.www_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="490" y="165" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="dmz-mail" value="" style="shape=mxgraph.cisco_safe.architecture.email_security;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="560" y="165" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="dmz-dns" value="" style="shape=mxgraph.cisco.servers.directory_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="620" y="175" width="40" height="40" as="geometry"/></mxCell>
  <mxCell id="fw-internal" value="" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="475" y="265" width="50" height="30" as="geometry"/></mxCell>
  <mxCell id="core-sw1" value="" style="shape=mxgraph.cisco.switches.layer_3_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="360" y="330" width="70" height="50" as="geometry"/></mxCell>
  <mxCell id="core-sw2" value="" style="shape=mxgraph.cisco.switches.layer_3_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="570" y="330" width="70" height="50" as="geometry"/></mxCell>
  <mxCell id="acc-sw1" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="80" y="480" width="80" height="30" as="geometry"/></mxCell>
  <mxCell id="acc-sw2" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="260" y="480" width="80" height="30" as="geometry"/></mxCell>
  <mxCell id="acc-sw3" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="400" y="480" width="80" height="30" as="geometry"/></mxCell>
  <mxCell id="user-pc1" value="" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="540" width="40" height="50" as="geometry"/></mxCell>
  <mxCell id="user-pc2" value="" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="110" y="540" width="40" height="50" as="geometry"/></mxCell>
  <mxCell id="user-laptop1" value="" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="240" y="545" width="50" height="35" as="geometry"/></mxCell>
  <mxCell id="user-laptop2" value="" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="300" y="545" width="50" height="35" as="geometry"/></mxCell>
  <mxCell id="user-phone1" value="" style="shape=mxgraph.cisco.modems_and_phones.ip_phone;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="410" y="540" width="30" height="45" as="geometry"/></mxCell>
  <mxCell id="user-phone2" value="" style="shape=mxgraph.cisco.modems_and_phones.ip_phone;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="450" y="540" width="30" height="45" as="geometry"/></mxCell>
  <mxCell id="srv-app1" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="580" y="480" width="35" height="55" as="geometry"/></mxCell>
  <mxCell id="srv-app2" value="" style="shape=mxgraph.cisco.servers.standard_host;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="625" y="480" width="35" height="55" as="geometry"/></mxCell>
  <mxCell id="srv-db" value="" style="shape=mxgraph.cisco_safe.capability.database;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="680" y="475" width="45" height="60" as="geometry"/></mxCell>
  <mxCell id="srv-storage" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="740" y="475" width="30" height="60" as="geometry"/></mxCell>
  <mxCell id="link-inet-fw" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#b85450;" parent="1" source="inet-cloud" target="fw-edge" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-lb" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="fw-edge" target="dmz-lb" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lb-web1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dmz-lb" target="dmz-web1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lb-web2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dmz-lb" target="dmz-web2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-mail" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="fw-edge" target="dmz-mail" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-dns" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="fw-edge" target="dmz-dns" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-fwint" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="fw-edge" target="fw-internal" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fwint-core1" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="fw-internal" target="core-sw1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fwint-core2" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="fw-internal" target="core-sw2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-core1-core2" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#036897;" parent="1" source="core-sw1" target="core-sw2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-core1-acc1" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="core-sw1" target="acc-sw1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-core1-acc2" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="core-sw1" target="acc-sw2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-core2-acc3" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="core-sw2" target="acc-sw3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-core2-srv" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="core-sw2" target="srv-app1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-acc1-pc1" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="acc-sw1" target="user-pc1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-acc1-pc2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="acc-sw1" target="user-pc2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-acc2-l1" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="acc-sw2" target="user-laptop1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-acc2-l2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="acc-sw2" target="user-laptop2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-acc3-p1" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="acc-sw3" target="user-phone1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-acc3-p2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="acc-sw3" target="user-phone2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-srv-app2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="srv-app1" target="srv-app2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-srv-db" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="srv-app2" target="srv-db" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-db-storage" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="srv-db" target="srv-storage" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

