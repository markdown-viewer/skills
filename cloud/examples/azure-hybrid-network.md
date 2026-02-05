# Azure Hybrid Network Architecture

Azure 混合网络架构示例，展示本地数据中心与 Azure VNet 的连接。

## Stencils Used (Verified from azure_1.drawio)

| Component | Stencil |
|-----------|---------|
| Virtual Machine | `mxgraph.azure.virtual_machine` |
| Computer | `mxgraph.azure.computer` |
| Gateway | `mxgraph.mscae.enterprise.gateway` |
| Load Balancer | `mxgraph.mscae.cloud.azure_load_balancer_feature` |
| Web Server | `mxgraph.mscae.enterprise.web` |
| Firewall | `mxgraph.office.concepts.firewall` |
| Lock/Security | `mxgraph.mscae.enterprise.lock` |

## Diagram

```drawio
<mxfile>
  <diagram name="Azure Hybrid Network">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="800" background="#184380">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="title" value="Azure Hybrid Network Architecture" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=24;fontColor=#FFFFFF;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="400" y="20" width="400" height="40" as="geometry"/></mxCell>
        <mxCell id="onprem-zone" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#F04D22;fillOpacity=20;strokeColor=#F04D22;strokeWidth=2;dashed=1;" vertex="1" parent="1"><mxGeometry x="50" y="100" width="300" height="350" as="geometry"/></mxCell>
        <mxCell id="onprem-label" value="On-Premises" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=16;fontColor=#F04D22;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="140" y="110" width="120" height="30" as="geometry"/></mxCell>
        <mxCell id="computer1" value="Workstation 1" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#0078D4;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.azure.computer;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="100" y="180" width="50" height="45" as="geometry"/></mxCell>
        <mxCell id="computer2" value="Workstation 2" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#0078D4;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.azure.computer;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="100" y="280" width="50" height="45" as="geometry"/></mxCell>
        <mxCell id="onprem-firewall" value="Firewall" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#F04D22;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.office.concepts.firewall;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="240" y="220" width="52" height="50" as="geometry"/></mxCell>
        <mxCell id="onprem-gateway" value="VPN Gateway" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#7A7A7A;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.enterprise.gateway;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="240" y="350" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="azure-zone" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#8BC63E;fillOpacity=20;strokeColor=#8BC63E;strokeWidth=2;dashed=1;" vertex="1" parent="1"><mxGeometry x="450" y="100" width="700" height="350" as="geometry"/></mxCell>
        <mxCell id="azure-label" value="Azure Virtual Network" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=16;fontColor=#8BC63E;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="720" y="110" width="160" height="30" as="geometry"/></mxCell>
        <mxCell id="azure-gateway" value="Azure VPN&#xa;Gateway" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#0078D4;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.enterprise.gateway;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="500" y="350" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="security" value="NSG" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#FFB900;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.enterprise.lock;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="500" y="220" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="lb" value="Load Balancer" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#00BCF2;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.cloud.azure_load_balancer_feature;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="640" y="220" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="web-zone" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#0072BC;fillOpacity=20;strokeColor=#0072BC;strokeWidth=2;" vertex="1" parent="1"><mxGeometry x="770" y="150" width="350" height="130" as="geometry"/></mxCell>
        <mxCell id="web-label" value="Web Tier" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=14;fontColor=#0072BC;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="900" y="155" width="80" height="25" as="geometry"/></mxCell>
        <mxCell id="web1" value="Web VM 1" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#0078D4;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.enterprise.web;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="820" y="200" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="web2" value="Web VM 2" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#0078D4;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.enterprise.web;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="920" y="200" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="web3" value="Web VM 3" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#0078D4;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.mscae.enterprise.web;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="1020" y="200" width="50" height="50" as="geometry"/></mxCell>
        <mxCell id="data-zone" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#9B59B6;fillOpacity=20;strokeColor=#9B59B6;strokeWidth=2;" vertex="1" parent="1"><mxGeometry x="770" y="310" width="350" height="120" as="geometry"/></mxCell>
        <mxCell id="data-label" value="Data Tier" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=14;fontColor=#9B59B6;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="900" y="315" width="80" height="25" as="geometry"/></mxCell>
        <mxCell id="db1" value="DB Primary" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#7FBA00;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.azure.virtual_machine;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="850" y="355" width="50" height="45" as="geometry"/></mxCell>
        <mxCell id="db2" value="DB Replica" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#7FBA00;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.azure.virtual_machine;fontColor=#FFFFFF;" vertex="1" parent="1"><mxGeometry x="990" y="355" width="50" height="45" as="geometry"/></mxCell>
        <!-- Computer to Firewall -->
        <mxCell id="conn1" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="computer1" target="onprem-firewall"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn2" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="computer2" target="onprem-firewall"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn3" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="onprem-firewall" target="onprem-gateway"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="vpn-tunnel" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFD700;strokeWidth=3;dashed=1;dashPattern=8 4;" edge="1" parent="1" source="onprem-gateway" target="azure-gateway"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="vpn-label" value="VPN Tunnel" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=12;fontColor=#FFD700;fontStyle=1;" vertex="1" parent="1"><mxGeometry x="350" y="360" width="80" height="20" as="geometry"/></mxCell>
        <mxCell id="conn4" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="azure-gateway" target="security"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="security" target="lb"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn6" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="lb" target="web1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn7" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="lb" target="web2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn8" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="lb" target="web3"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn9" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#FFFFFF;strokeWidth=2;" edge="1" parent="1" source="web2" target="db1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn10" style="edgeStyle=orthogonalEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#9B59B6;strokeWidth=2;dashed=1;" edge="1" parent="1" source="db1" target="db2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="repl-label" value="Replication" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=10;fontColor=#9B59B6;" vertex="1" parent="1"><mxGeometry x="900" y="365" width="70" height="20" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Architecture Overview

This diagram illustrates a typical Azure hybrid network with:

1. **On-Premises Network** (Orange zone)
   - Workstations connecting through corporate firewall
   - VPN Gateway for site-to-site connection

2. **Azure Virtual Network** (Green zone)
   - VPN Gateway receiving encrypted tunnel
   - Network Security Group (NSG) for access control
   - Load Balancer distributing traffic

3. **Web Tier** (Blue zone)
   - Three web server VMs for high availability
   - Behind load balancer for traffic distribution

4. **Data Tier** (Purple zone)
   - Primary and replica database VMs
   - Synchronous replication for data protection
