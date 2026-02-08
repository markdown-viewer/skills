# Rack Diagram - Data Center Cabinet

A 42U standard rack populated with networking, security, storage, and compute equipment from multiple vendors (Cisco, F5, HP, IBM).

Based on template: `engineering/rack_1.drawio`

## Stencils Used

| Stencil | Role |
|---------|------|
| `mxgraph.rack.general.42u_rack_19_standard` | Rack enclosure — container with `childLayout=rack` auto-stacking |
| `mxgraph.rack.general.cat5e_enhanced_patch_panel_48_ports` | Patch panel — 1U copper interconnect (×4) |
| `mxgraph.rack.general.switches_2` | Network switch — 1U L2/L3 switch |
| `mxgraph.rack.cisco.cisco_nexus_7000_4-slot_switch_chassis` | Core switch — 5U modular chassis |
| `mxgraph.rack.cisco.cisco_wae-674` | WAN accelerator — 1U appliance |
| `mxgraph.rack.cisco.cisco_wave_294` | WAN optimization — 1U appliance |
| `mxgraph.rack.cisco.cisco_web_security_appliance_s670` | Web security — 1U proxy/filter |
| `mxgraph.rack.f5.viprion_2400` | ADC chassis — 3U load balancer |
| `mxgraph.rack.f5.firepass_4100` | SSL VPN — 2U remote access |
| `mxgraph.rack.f5.big_ip_6900` | Load balancer — 2U traffic manager |
| `mxgraph.rack.f5.big_ip_3900` | Load balancer — 1U compact ADC |
| `mxgraph.rack.f5.arx_4000` | File virtualization — 3U storage gateway |
| `mxgraph.rack.f5.arx_1500` | File virtualization — 1U compact (×2) |
| `mxgraph.rack.f5.arx_500` | File virtualization — 1U entry model |
| `mxgraph.rack.hp.hp_proliant_dl385p_g8` | Compute server — 1U rack server |
| `mxgraph.rack.ibm.ibm_x3850_x5` | Compute server — 3U enterprise server |

- Rack container uses `container=1;collapsible=0;childLayout=rack` with margin offsets (`marginLeft=33;marginRight=9;marginTop=21;marginBottom=22`) to position children automatically
- All equipment uses `labelPosition=right;align=left;spacingLeft=15` for labels placed to the right of the device graphic
- Equipment height follows U-count: 1U = 20 px, 2U = 40 px, 3U = 60 px, 5U = 100 px
- Fill is uniformly `fillColor=#ffffff` with `strokeColor=#666666` (general) or `strokeColor=#000000` (vendor-specific)
- `numDisp=ascend` on the rack container shows ascending U-numbers on the left rail

## Example

Mixed-vendor data center rack: 4× patch panels (U1–U5), Cisco network/security tier (U6–U14), F5 application delivery tier (U15–U27), HP/IBM compute tier (U28–U32).

```drawio
<mxfile>
  <diagram name="Page-1" id="579b083d-5abb-d308-4585-858c28a85260">
    <mxGraphModel dx="1408" dy="544" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="cdbfa7a1973974c-1" value="" style="strokeColor=#666666;fillColor=#FFFFFF;shape=mxgraph.rack.general.42u_rack_19_standard;container=1;collapsible=0;childLayout=rack;marginLeft=33;marginRight=9;marginTop=21;marginBottom=22;textColor=#666666;numDisp=ascend;html=1;" parent="1" vertex="1"><mxGeometry x="240" y="66" width="239" height="690" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-25" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.general.cat5e_enhanced_patch_panel_48_ports;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="21" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-26" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.general.switches_2;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="41" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-27" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.general.cat5e_enhanced_patch_panel_48_ports;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="61" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-28" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.general.cat5e_enhanced_patch_panel_48_ports;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="81" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-29" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.general.cat5e_enhanced_patch_panel_48_ports;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="101" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-30" value="" style="shape=mxgraph.rack.cisco.cisco_nexus_7000_4-slot_switch_chassis;html=1;labelPosition=right;align=left;spacingLeft=15;dashed=0;shadow=0;fillColor=#ffffff;rounded=0;comic=0;labelBackgroundColor=none;strokeColor=#000000;strokeWidth=1;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="121" width="197" height="100" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-31" value="" style="shape=mxgraph.rack.cisco.cisco_wae-674;html=1;labelPosition=right;align=left;spacingLeft=15;dashed=0;shadow=0;fillColor=#ffffff;rounded=0;comic=0;labelBackgroundColor=none;strokeColor=#000000;strokeWidth=1;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="221" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-32" value="" style="shape=mxgraph.rack.cisco.cisco_wave_294;html=1;labelPosition=right;align=left;spacingLeft=15;dashed=0;shadow=0;fillColor=#ffffff;rounded=0;comic=0;labelBackgroundColor=none;strokeColor=#000000;strokeWidth=1;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="241" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-33" value="" style="shape=mxgraph.rack.cisco.cisco_web_security_appliance_s670;html=1;labelPosition=right;align=left;spacingLeft=15;dashed=0;shadow=0;fillColor=#ffffff;rounded=0;comic=0;labelBackgroundColor=none;strokeColor=#000000;strokeWidth=1;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="261" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-34" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.viprion_2400;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="281" width="197" height="60" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-35" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.firepass_4100;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="341" width="197" height="40" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-36" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.big_ip_6900;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="381" width="197" height="40" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-37" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.big_ip_3900;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="421" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-38" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.arx_4000;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="441" width="197" height="60" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-39" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.arx_1500;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="501" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-40" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.arx_1500;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="521" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-41" value="" style="strokeColor=#666666;html=1;labelPosition=right;align=left;spacingLeft=15;shadow=0;dashed=0;fillColor=#ffffff;shape=mxgraph.rack.f5.arx_500;rounded=0;comic=0;labelBackgroundColor=none;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="541" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-42" value="" style="shape=mxgraph.rack.hp.hp_proliant_dl385p_g8;html=1;labelPosition=right;align=left;spacingLeft=15;dashed=0;shadow=0;fillColor=#ffffff;rounded=0;comic=0;labelBackgroundColor=none;strokeColor=#000000;strokeWidth=1;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="561" width="197" height="20" as="geometry"/></mxCell>
        <mxCell id="cdbfa7a1973974c-43" value="" style="shape=mxgraph.rack.ibm.ibm_x3850_x5;html=1;labelPosition=right;align=left;spacingLeft=15;dashed=0;shadow=0;fillColor=#ffffff;rounded=0;comic=0;labelBackgroundColor=none;strokeColor=#000000;strokeWidth=1;fontFamily=Verdana;fontSize=12;fontColor=#000000;" parent="cdbfa7a1973974c-1" vertex="1"><mxGeometry x="33" y="581" width="197" height="60" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>

```

## Pattern Notes

1. **Rack auto-layout**: `childLayout=rack` on the container eliminates manual y-positioning — children stack top-to-bottom in insertion order
2. **U-height mapping**: always `height = U × 20` (1U = 20 px, 2U = 40 px, 3U = 60 px, 5U = 100 px); width is fixed at 197 px for standard 19″ equipment
3. **Margin offsets**: `marginLeft=33;marginTop=21;marginBottom=22;marginRight=9` account for the rack rails and top/bottom frame drawn by the container shape
4. **Label placement**: all equipment cells use `labelPosition=right;align=left;spacingLeft=15` so text labels appear outside the rack frame to the right
5. **Vendor stencil families**: group equipment by vendor prefix — `mxgraph.rack.cisco.*`, `mxgraph.rack.f5.*`, `mxgraph.rack.hp.*`, `mxgraph.rack.ibm.*`, `mxgraph.rack.general.*`
6. **Logical tiering**: arrange equipment in functional tiers from top to bottom — cabling/patching → network → security → application delivery → compute
7. **Consistent fill**: use `fillColor=#ffffff` for all equipment to keep a clean monochrome look; vary `strokeColor` only by vendor convention (#666666 for general, #000000 for vendor-specific)
8. **U-number display**: `numDisp=ascend` shows ascending U-numbers on the rack rail to help readers identify slot positions

## Rack Unit Sizing

- **1U** = 20px height
- **2U** = 40px height
- **3U** = 60px height
- **5U** = 100px height
