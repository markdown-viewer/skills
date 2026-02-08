# Citrix Network Diagram

Shows a Citrix Virtual Apps and Desktops infrastructure with NetScaler Gateway.

## Key Elements

- **NetScaler Gateway**: `shape=mxgraph.citrix2.netscaler_gateway` (100×89)
- **StoreFront**: `shape=mxgraph.citrix2.storefront` (100×86)
- **Delivery Controller**: `shape=mxgraph.citrix2.delivery_controller` (100×100)
- **VDA (Virtual Delivery Agent)**: `shape=mxgraph.citrix2.vda` (100×82)
- **Cloud Connector**: `shape=mxgraph.citrix2.cloud_connector` (100×78)
- **XenServer Hypervisor**: `shape=mxgraph.citrix2.hypervisor_xenserver` (100×62)
- **Director**: `shape=mxgraph.citrix2.director` (100×86)
- **License Server**: `shape=mxgraph.citrix2.citrix_license_server` (100×72)
- **Site Database**: `shape=mxgraph.citrix2.site_database` (91×100)
- **External Users**: `shape=mxgraph.citrix2.external_users` (98×101)
- **Laptop**: `shape=mxgraph.citrix2.laptop` (100×77)
- **Firewall**: `shape=mxgraph.citrix2.firewall` (100×100)

## Citrix Style

| Property | Value | Description |
|-----------|------|---------|
| fillColor | `#000000` | Black (citrix2 standard) |
| strokeColor | `none` | No outline |
| gradientColor | `none` | No gradient |
| aspect | `fixed` | Maintain aspect ratio |
| Extra props | `sketch=0;outlineConnect=0;pointerEvents=1;` | citrix2 required |

**Recommended colors:** `#452170` (purple) / `#0054A6` (blue) / `#00AEEF` (cyan) / `#95C93F` (green)

**Zone backgrounds:** Color-coded zones with `strokeColor=none;opacity=80;verticalAlign=top`:
- DMZ / External: `fillColor=#f8cecc` (red)
- Internal Network: `fillColor=#fff2cc` (gold)
- Server Farm: `fillColor=#EDEDED` (gray)
- Cloud: `fillColor=#d5e8d4` (green)

**Edge style:** `endArrow=none;endFill=0;strokeWidth=2` — bidirectional, no arrows.

## Example

Citrix Virtual Apps and Desktops deployment with DMZ, internal network, and data center zones:

```drawio
<mxfile><diagram id="citrix-network" name="Citrix CVAD"><mxGraphModel dx="1100" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="850" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="zone-dc" value="Data Center" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#EDEDED;fontSize=14;strokeColor=none;verticalAlign=top;fontStyle=1;opacity=80;" vertex="1" parent="1"><mxGeometry x="440" y="40" width="720" height="760" as="geometry"/></mxCell>
  <mxCell id="zone-dmz" value="DMZ" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#f8cecc;fontSize=14;strokeColor=none;verticalAlign=top;fontStyle=1;opacity=80;" vertex="1" parent="1"><mxGeometry x="460" y="80" width="200" height="700" as="geometry"/></mxCell>
  <mxCell id="zone-internal" value="Internal Network" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#fff2cc;fontSize=14;strokeColor=none;verticalAlign=top;fontStyle=1;opacity=80;" vertex="1" parent="1"><mxGeometry x="700" y="80" width="440" height="700" as="geometry"/></mxCell>
  <mxCell id="ext-users" value="External&#xa;Users" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.external_users;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="60" y="160" width="59" height="60" as="geometry"/></mxCell>
  <mxCell id="laptop1" value="Laptop" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.laptop;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="40" y="360" width="80" height="62" as="geometry"/></mxCell>
  <mxCell id="tablet1" value="Mobile" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.tablet;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="60" y="530" width="44" height="60" as="geometry"/></mxCell>
  <mxCell id="fw-ext" value="Firewall" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.firewall;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="240" y="340" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="nsg" value="NetScaler&#xa;Gateway" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.netscaler_gateway;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="510" y="160" width="60" height="53" as="geometry"/></mxCell>
  <mxCell id="sf" value="StoreFront" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.storefront;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="510" y="380" width="60" height="52" as="geometry"/></mxCell>
  <mxCell id="fw-int" value="Firewall" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.firewall;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="510" y="570" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="dc1" value="Delivery&#xa;Controller 1" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.delivery_controller;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="730" y="120" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="dc2" value="Delivery&#xa;Controller 2" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.delivery_controller;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="860" y="120" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="director" value="Director" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.director;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="1000" y="120" width="60" height="52" as="geometry"/></mxCell>
  <mxCell id="license" value="License&#xa;Server" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.citrix_license_server;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="1000" y="290" width="60" height="43" as="geometry"/></mxCell>
  <mxCell id="sitedb" value="Site&#xa;Database" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.site_database;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="1000" y="430" width="55" height="60" as="geometry"/></mxCell>
  <mxCell id="xenhost1" value="XenServer 1" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.hypervisor_xenserver;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="730" y="310" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="xenhost2" value="XenServer 2" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.hypervisor_xenserver;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="860" y="310" width="80" height="50" as="geometry"/></mxCell>
  <mxCell id="vda1" value="VDA" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.vda;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="730" y="460" width="60" height="49" as="geometry"/></mxCell>
  <mxCell id="vda2" value="VDA" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.vda;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="830" y="460" width="60" height="49" as="geometry"/></mxCell>
  <mxCell id="vda3" value="VDA" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.vda;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="930" y="460" width="60" height="49" as="geometry"/></mxCell>
  <mxCell id="winapp" value="Windows&#xa;Apps" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.windows_app;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="730" y="600" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="linapp" value="Linux&#xa;Apps" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.linux_app;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="860" y="600" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="vdesk" value="Virtual&#xa;Desktop" style="verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;shape=mxgraph.citrix2.virtual_desktop;fillColor=#000000;gradientColor=none;fontSize=12;sketch=0;outlineConnect=0;pointerEvents=1;" vertex="1" parent="1"><mxGeometry x="990" y="600" width="47" height="60" as="geometry"/></mxCell>
  <mxCell id="link-ext-fw" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="ext-users" target="fw-ext"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lap-fw" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="laptop1" target="fw-ext"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-tab-fw" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="tablet1" target="fw-ext"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-nsg" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="fw-ext" target="nsg"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fw-sf" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="fw-ext" target="sf"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-nsg-dc1" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="nsg" target="dc1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sf-fwi" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="sf" target="fw-int"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-fwi-dc1" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;dashed=1;" edge="1" parent="1" source="fw-int" target="dc1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc1-dc2" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="dc1" target="dc2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc2-dir" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="dc2" target="director"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc1-xen1" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="dc1" target="xenhost1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc2-xen2" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="dc2" target="xenhost2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc1-lic" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="dc1" target="license"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dc1-db" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="dc2" target="sitedb"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xen1-vda1" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="xenhost1" target="vda1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xen1-vda2" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="xenhost1" target="vda2"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-xen2-vda3" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="xenhost2" target="vda3"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda1-win" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="vda1" target="winapp"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda2-lin" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="vda2" target="linapp"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-vda3-vd" style="edgeStyle=none;html=1;endArrow=none;endFill=0;strokeWidth=2;fontSize=12;" edge="1" parent="1" source="vda3" target="vdesk"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. **citrix2 black fill**: All `mxgraph.citrix2.*` stencils use `fillColor=#000000;gradientColor=none;strokeColor=none`
2. **Required extra props**: citrix2 stencils need `sketch=0;outlineConnect=0;pointerEvents=1;`
3. **No arrows**: Network links use `endArrow=none;endFill=0;strokeWidth=2` — bidirectional connections
4. **Dashed = secondary path**: Use `dashed=1` for backup/fallback connections
5. **Color-coded zones**: DMZ (`#f8cecc`), Internal (`#fff2cc`), Server Farm (`#EDEDED`), Cloud (`#d5e8d4`)
6. **Labels below**: All stencils use `verticalLabelPosition=bottom;verticalAlign=top`
7. **Layered layout**: Clients → Firewall → DMZ (NetScaler + StoreFront) → Internal Firewall → Delivery Controllers → Hypervisors → VDAs → Apps

