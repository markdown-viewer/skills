# Hybrid Cloud Network Diagram

Shows a hybrid cloud architecture connecting on-premise infrastructure with cloud services.

## Key Elements

- **Cloud Provider**: `ellipse;shape=cloud` with provider branding
- **VPN Gateway**: `shape=mxgraph.cisco.misc.vpn_concentrator`
- **Data Center**: `shape=mxgraph.cisco19.data_center`
- **Virtual Servers**: `shape=mxgraph.cisco_safe.design.server_1`
- **Storage**: `shape=mxgraph.cisco.servers.storage_server`

## Connection Types

| Type | Style | Use Case |
|------|-------|----------|
| Site-to-Site VPN | `strokeColor=#036897;dashed=1` | Secure tunnel |
| Direct Connect | `strokeColor=#036897;strokeWidth=3` | Dedicated line |
| Internet | `strokeColor=#b85450` | Public access |

## Example

Enterprise hybrid cloud with AWS/Azure integration:

```drawio
<mxfile><diagram id="hybrid-cloud" name="Hybrid Cloud"><mxGraphModel dx="1000" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-onprem" value="On-Premise Data Center" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#dae8fc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="200" width="280" height="340" as="geometry"/></mxCell>
  <mxCell id="zone-aws" value="AWS Cloud" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#fff2cc;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="480" y="80" width="280" height="220" as="geometry"/></mxCell>
  <mxCell id="zone-azure" value="Azure Cloud" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#e1d5e7;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="480" y="340" width="280" height="200" as="geometry"/></mxCell>
  <mxCell id="zone-users" value="Remote Users" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=none;fillColor=#d5e8d4;opacity=60;fontSize=14;fontColor=#23445D;verticalAlign=top;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="40" y="40" width="200" height="120" as="geometry"/></mxCell>
  <mxCell id="internet" value="Internet" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#b85450;fillColor=#ffffff;fontSize=14;fontColor=#b85450;fontStyle=1;" parent="1" vertex="1"><mxGeometry x="300" y="100" width="140" height="80" as="geometry"/></mxCell>
  <mxCell id="aws-cloud" value="" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#FF9900;fillColor=#ffffff;" parent="1" vertex="1"><mxGeometry x="560" y="110" width="120" height="60" as="geometry"/></mxCell>
  <mxCell id="azure-cloud" value="" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;strokeWidth=2;strokeColor=#0078D4;fillColor=#ffffff;" parent="1" vertex="1"><mxGeometry x="560" y="370" width="120" height="60" as="geometry"/></mxCell>
  <mxCell id="dc-building" value="" style="shape=mxgraph.cisco19.data_center;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="240" width="70" height="60" as="geometry"/></mxCell>
  <mxCell id="dc-fw" value="" style="shape=mxgraph.cisco.security.firewall;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="160" y="255" width="50" height="30" as="geometry"/></mxCell>
  <mxCell id="dc-vpn" value="" style="shape=mxgraph.cisco.security.vpn_concentrator;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="235" y="250" width="60" height="40" as="geometry"/></mxCell>
  <mxCell id="dc-switch" value="" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="100" y="330" width="90" height="30" as="geometry"/></mxCell>
  <mxCell id="dc-server1" value="" style="shape=mxgraph.cisco.servers.fileserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="390" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="dc-server2" value="" style="shape=mxgraph.cisco.servers.fileserver;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="110" y="390" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="dc-storage" value="" style="shape=mxgraph.cisco.servers.storage_server;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="160" y="385" width="40" height="60" as="geometry"/></mxCell>
  <mxCell id="dc-backup" value="" style="shape=mxgraph.cisco.storage.tape_array;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="210" y="385" width="50" height="60" as="geometry"/></mxCell>
  <mxCell id="aws-vpc" value="VPC" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#FF9900;strokeWidth=2;fillColor=none;fontSize=11;fontStyle=1;verticalAlign=top;" parent="1" vertex="1"><mxGeometry x="500" y="175" width="240" height="110" as="geometry"/></mxCell>
  <mxCell id="aws-ec2-1" value="" style="shape=mxgraph.cisco_safe.design.server_1;html=1;fillColor=#FF9900;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="520" y="210" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="aws-ec2-2" value="" style="shape=mxgraph.cisco_safe.design.server_1;html=1;fillColor=#FF9900;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="580" y="210" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="aws-rds" value="" style="shape=mxgraph.cisco_safe.capability.database;html=1;fillColor=#FF9900;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="640" y="205" width="40" height="60" as="geometry"/></mxCell>
  <mxCell id="aws-s3" value="" style="shape=mxgraph.cisco19.storage;html=1;fillColor=#FF9900;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="700" y="210" width="30" height="50" as="geometry"/></mxCell>
  <mxCell id="azure-vnet" value="VNet" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#0078D4;strokeWidth=2;fillColor=none;fontSize=11;fontStyle=1;verticalAlign=top;" parent="1" vertex="1"><mxGeometry x="500" y="435" width="240" height="90" as="geometry"/></mxCell>
  <mxCell id="azure-vm1" value="" style="shape=mxgraph.cisco_safe.design.server_1;html=1;fillColor=#0078D4;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="520" y="460" width="40" height="50" as="geometry"/></mxCell>
  <mxCell id="azure-vm2" value="" style="shape=mxgraph.cisco_safe.design.server_1;html=1;fillColor=#0078D4;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="580" y="460" width="40" height="50" as="geometry"/></mxCell>
  <mxCell id="azure-sql" value="" style="shape=mxgraph.cisco_safe.capability.database;html=1;fillColor=#0078D4;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="640" y="455" width="40" height="55" as="geometry"/></mxCell>
  <mxCell id="azure-blob" value="" style="shape=mxgraph.cisco19.storage;html=1;fillColor=#0078D4;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="700" y="460" width="30" height="50" as="geometry"/></mxCell>
  <mxCell id="user-laptop" value="" style="shape=mxgraph.cisco.computers_and_peripherals.laptop;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="60" y="80" width="55" height="35" as="geometry"/></mxCell>
  <mxCell id="user-mobile" value="" style="shape=mxgraph.cisco.modems_and_phones.cell_phone;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="135" y="75" width="25" height="45" as="geometry"/></mxCell>
  <mxCell id="user-home" value="" style="shape=mxgraph.cisco.buildings.telecommuter_house;html=1;fillColor=#036897;strokeColor=#ffffff;strokeWidth=2;" parent="1" vertex="1"><mxGeometry x="175" y="70" width="50" height="40" as="geometry"/></mxCell>
  <mxCell id="link-dc-fw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dc-building" target="dc-fw" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-vpn" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dc-fw" target="dc-vpn" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-sw" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#23445D;" parent="1" source="dc-fw" target="dc-switch" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-srv1" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="dc-switch" target="dc-server1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-srv2" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="dc-switch" target="dc-server2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-sto" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="dc-switch" target="dc-storage" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sw-bak" style="endArrow=none;html=1;strokeWidth=1;strokeColor=#666666;" parent="1" source="dc-switch" target="dc-backup" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vpn-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#b85450;" parent="1" source="dc-vpn" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-inet-aws" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#FF9900;dashed=1;dashPattern=8 4;" parent="1" source="internet" target="aws-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-inet-azure" style="endArrow=none;html=1;strokeWidth=3;strokeColor=#0078D4;dashed=1;dashPattern=8 4;" parent="1" source="internet" target="azure-cloud" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-aws-vpc" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#FF9900;" parent="1" source="aws-cloud" target="aws-vpc" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-azure-vnet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#0078D4;" parent="1" source="azure-cloud" target="azure-vnet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-user-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#b85450;" parent="1" source="user-laptop" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-mobile-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#b85450;" parent="1" source="user-mobile" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-home-inet" style="endArrow=none;html=1;strokeWidth=2;strokeColor=#b85450;" parent="1" source="user-home" target="internet" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

