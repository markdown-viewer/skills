# P&ID - Oil Refining Plant

A professional Piping & Instrumentation Diagram (P&ID) for an auxiliary oil refining plant with centrifugal compressor, mixing reactor, distillation tower, storage vessels, and SCADA-connected instrumentation.

Based on template: `engineering/pid_1.drawio`

## Stencils Used

| Component | Stencil | Role |
|-----------|---------|------|
| Storage Tank | `mxgraph.pid.vessels.tank` | Feed / product storage (OV 01, OV 02) |
| Mixing Reactor | `mxgraph.pid.vessels.mixing_reactor` | Chemical reaction vessel (OM 01) |
| Packed Tower | `mxgraph.pid.vessels.tower_with_packing` | Distillation / separation (RT 01) |
| Centrifugal Compressor | `mxgraph.pid.compressors.centrifugal_compressor_-_turbine_driven` | Gas compression (OT 01) |
| U-Tube Heat Exchanger | `mxgraph.pid.heat_exchangers.u-tube_heat_exchanger` | Heat transfer |
| Hairpin Exchanger | `mxgraph.pid.heat_exchangers.hairpin_exchanger` | Heat recovery |
| Ball Valve | `mxgraph.pid.valves.ball_valve` | Manual isolation |
| Motor Operated Valve | `mxgraph.pid.valves.motor_operated_valve` | Remote-controlled valve |
| Pressure Transmitter | `mxgraph.pid.instruments.pressure_transmitter_2` | Pressure measurement (PT) |
| Level Transmitter | `mxgraph.pid.instruments.level_transmitter_2` | Level measurement (LT) |
| Flow Transmitter | `mxgraph.pid.instruments.flow_transmitter` | Flow measurement (FT) |
| Signal Arrow | `mxgraph.arrows.signal-in_arrow` | Process flow direction |

- **All equipment**: `fillColor=white;strokeColor=black` — monochrome P&ID standard
- **Piping**: `edgeStyle=elbowEdgeStyle;endArrow=none;rounded=0` — elbow routing, no arrowheads
- **Instruments**: 40×38 px (transmitters), with 4-digit tag numbers as `text` cells
- **SCADA row**: instruments repeated at top (y≈78) with type labels (PRESS, LEVEL, FLOW)
- **Title block**: bordered cells at bottom with plant info ("Europe Oil Inc.", "Plant: RP 12")

## Example

Oil refining P&ID with crude oil input → compressor → reactor → tower → storage tanks, with motor-operated valves and SCADA-connected transmitters:

```drawio
<mxfile>
  <diagram name="Page-1" id="ce31cf60-c478-4b58-59a4-9352b24465d2">
    <mxGraphModel dx="1408" dy="544" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1.5" pageWidth="826" pageHeight="1169" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="180" value="" style="fillColor=none;strokeWidth=3" parent="1" vertex="1"><mxGeometry x="34" y="30" width="1700" height="1140" as="geometry"/></mxCell>
        <mxCell id="179" value="" parent="1" vertex="1"><mxGeometry x="1574" y="79.69907407407409" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="178" value="" parent="1" vertex="1"><mxGeometry x="1474" y="79.69907407407409" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="177" value="" parent="1" vertex="1"><mxGeometry x="1425" y="78.34953703703705" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="176" value="" parent="1" vertex="1"><mxGeometry x="1370" y="77" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="175" value="" parent="1" vertex="1"><mxGeometry x="1320" y="79.09953703703705" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="174" value="" parent="1" vertex="1"><mxGeometry x="1184" y="78.34953703703704" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="173" value="" parent="1" vertex="1"><mxGeometry x="1127" y="78.9490740740741" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="172" value="" parent="1" vertex="1"><mxGeometry x="999" y="79.09953703703708" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="171" value="" parent="1" vertex="1"><mxGeometry x="944" y="78" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="170" value="" parent="1" vertex="1"><mxGeometry x="888" y="78.94907407407409" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="169" value="" parent="1" vertex="1"><mxGeometry x="702" y="76" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="168" value="" parent="1" vertex="1"><mxGeometry x="624" y="76.5" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="167" value="" parent="1" vertex="1"><mxGeometry x="434" y="77.25" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="166" value="" parent="1" vertex="1"><mxGeometry x="384" y="77.6990740740741" width="40" height="37.8" as="geometry"/></mxCell>
        <mxCell id="2" value="" style="shape=mxgraph.pid.vessels.tank;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1350" y="320" width="80" height="290" as="geometry"/></mxCell>
        <mxCell id="3" value="" style="shape=mxgraph.pid.vessels.tank;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1230" y="320" width="80" height="290" as="geometry"/></mxCell>
        <mxCell id="4" value="" style="shape=mxgraph.pid.vessels.mixing_reactor;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="694" y="620" width="200" height="316" as="geometry"/></mxCell>
        <mxCell id="5" value="" style="shape=mxgraph.pid.vessels.tower_with_packing;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1014" y="300" width="80" height="440" as="geometry"/></mxCell>
        <mxCell id="6" value="" style="shape=mxgraph.pid.compressors.centrifugal_compressor_-_turbine_driven;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="454" y="320" width="268" height="180" as="geometry"/></mxCell>
        <mxCell id="7" value="" style="shape=mxgraph.pid.heat_exchangers.u-tube_heat_exchanger;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1220" y="550" width="60" height="20" as="geometry"/></mxCell>
        <mxCell id="8" value="" style="shape=mxgraph.pid.heat_exchangers.hairpin_exchanger;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1004" y="687" width="70" height="22" as="geometry"/></mxCell>
        <mxCell id="9" value="RTU 021" style="horizontal=0" parent="1" vertex="1"><mxGeometry x="34" y="130" width="20" height="100" as="geometry"/></mxCell>
        <mxCell id="10" value="" parent="1" vertex="1"><mxGeometry x="54" y="130" width="1680" height="100" as="geometry"/></mxCell>
        <mxCell id="11" value="N-OZ-301" style="shape=mxgraph.arrows.signal-in_arrow;fillColor=white;strokeColor=black;strokeWidth=1" parent="1" vertex="1"><mxGeometry x="124" y="572.5" width="80" height="30" as="geometry"/></mxCell>
        <mxCell id="12" value="Crude Oil from DBS-01" style="text" parent="1" vertex="1"><mxGeometry x="104" y="539.5" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="13" value="1" parent="1" vertex="1"><mxGeometry x="94" y="572.5" width="30" height="30" as="geometry"/></mxCell>
        <mxCell id="14" value="" style="shape=mxgraph.pid.valves.ball_valve;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="264" y="565" width="70" height="45" as="geometry"/></mxCell>
        <mxCell id="15" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=1;exitY=0.5;exitPerimeter=0;entryX=0;entryY=0.067;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="14" target="6" edge="1"><mxGeometry x="64" y="10" width="100" height="100" as="geometry"><mxPoint x="64" y="110" as="sourcePoint"/><mxPoint x="164" y="10" as="targetPoint"/><Array as="points"><mxPoint x="364" y="490"/></Array></mxGeometry></mxCell>
        <mxCell id="16" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=1;exitY=0.5;exitPerimeter=0;entryX=0;entryY=0.5;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="11" target="14" edge="1"><mxGeometry x="64" y="-47.5" width="100" height="100" as="geometry"><mxPoint x="64" y="52.500000000000014" as="sourcePoint"/><mxPoint x="164" y="-47.5" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="19" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="394" y="370" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="21" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=0.5;exitY=1;exitPerimeter=0;entryX=0;entryY=0.63;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="19" target="6" edge="1"><mxGeometry x="64" y="10" width="100" height="100" as="geometry"><mxPoint x="64" y="110" as="sourcePoint"/><mxPoint x="164" y="10" as="targetPoint"/><Array as="points"><mxPoint x="414" y="420"/></Array></mxGeometry></mxCell>
        <mxCell id="22" value="1201" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="394" y="389" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="27" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="434" y="260" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="28" value="1202" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="434" y="279" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="29" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="702" y="260" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="30" value="1203" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="702" y="279" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="31" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=0;exitY=0.067;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="6" target="27" edge="1"><mxGeometry x="64" y="10" width="100" height="100" as="geometry"><mxPoint x="64" y="110" as="sourcePoint"/><mxPoint x="164" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="32" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=1;exitY=0.067;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="6" target="29" edge="1"><mxGeometry x="64" y="10" width="100" height="100" as="geometry"><mxPoint x="64" y="110" as="sourcePoint"/><mxPoint x="164" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="33" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="44" y="1020" width="1560" height="150" as="geometry"/></mxCell>
        <mxCell id="34" value="Europe Oil Inc.&#10;&#10;Auxiliary Oil Refining Plant" style="strokeWidth=2;fontSize=18;fontStyle=1" parent="1" vertex="1"><mxGeometry x="742" y="1020" width="372" height="150" as="geometry"/></mxCell>
        <mxCell id="35" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="1114" y="1020" width="26" height="150" as="geometry"/></mxCell>
        <mxCell id="36" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="1404" y="1100" width="26" height="70" as="geometry"/></mxCell>
        <mxCell id="37" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="1404" y="1020" width="26" height="80" as="geometry"/></mxCell>
        <mxCell id="38" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="1430" y="1020" width="304" height="80" as="geometry"/></mxCell>
        <mxCell id="39" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="1430" y="1100" width="304" height="70" as="geometry"/></mxCell>
        <mxCell id="40" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="34" y="1020.0" width="30" height="80" as="geometry"/></mxCell>
        <mxCell id="41" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="34" y="1100" width="30" height="70" as="geometry"/></mxCell>
        <mxCell id="42" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="64" y="1020" width="180" height="40" as="geometry"/></mxCell>
        <mxCell id="43" value="" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="64" y="1060" width="180" height="40" as="geometry"/></mxCell>
        <mxCell id="44" value="Plant: RP 12" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="64" y="1100" width="180" height="30" as="geometry"/></mxCell>
        <mxCell id="45" value="Page: 1 of 1" style="strokeWidth=2" parent="1" vertex="1"><mxGeometry x="64" y="1130" width="180" height="40" as="geometry"/></mxCell>
        <mxCell id="46" value="10'' CWS" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=1;exitY=0.5;exitPerimeter=0;entryX=0.5;entryY=0;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="14" target="4" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="794" y="600"/></Array></mxGeometry></mxCell>
        <mxCell id="47" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=0;exitPerimeter=0;entryX=0.5;entryY=0;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="4" target="5" edge="1"><mxGeometry x="824" y="420" width="100" height="100" as="geometry"><mxPoint x="824" y="520" as="sourcePoint"/><mxPoint x="924" y="420" as="targetPoint"/><Array as="points"><mxPoint x="944" y="280"/></Array></mxGeometry></mxCell>
        <mxCell id="48" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=1;exitY=0.5;exitPerimeter=0;entryX=0;entryY=0.5;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="5" target="3" edge="1"><mxGeometry x="1204" y="680" width="100" height="100" as="geometry"><mxPoint x="1204" y="780" as="sourcePoint"/><mxPoint x="1304" y="680" as="targetPoint"/><Array as="points"><mxPoint x="1134" y="490"/></Array></mxGeometry></mxCell>
        <mxCell id="49" value="" style="edgeStyle=elbowEdgeStyle;elbow=horizontal;exitX=1;exitY=0.5;exitPerimeter=0;entryX=0;entryY=0.5;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="3" target="2" edge="1"><mxGeometry x="60" y="10" width="100" height="100" as="geometry"><mxPoint x="60" y="110" as="sourcePoint"/><mxPoint x="160" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="53" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=0;exitPerimeter=0;entryX=0.5;entryY=0;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="2" target="3" edge="1"><mxGeometry x="60" y="10" width="100" height="100" as="geometry"><mxPoint x="60" y="110" as="sourcePoint"/><mxPoint x="160" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1330" y="290"/></Array></mxGeometry></mxCell>
        <mxCell id="54" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="944" y="310" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="55" value="1204" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="944" y="330" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="56" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="944" y="602.5" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="57" value="1204" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="944" y="622.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="58" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1154" y="515.5" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="59" value="1206" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1154" y="535.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="60" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1154" y="289.5" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="61" value="1205" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1154" y="309.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="62" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1474" y="291.5" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="63" value="1207" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1474" y="311.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="64" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1474" y="515.5" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="65" value="1208" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1474" y="535.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="72" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="54" target="5" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="994" y="370"/></Array></mxGeometry></mxCell>
        <mxCell id="73" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="56" target="5" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="984" y="670"/></Array></mxGeometry></mxCell>
        <mxCell id="74" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="60" target="3" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1204" y="360"/></Array></mxGeometry></mxCell>
        <mxCell id="75" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="58" target="3" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1204" y="580"/></Array></mxGeometry></mxCell>
        <mxCell id="76" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="62" target="2" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1444" y="370"/></Array></mxGeometry></mxCell>
        <mxCell id="77" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="64" target="2" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1454" y="580"/></Array></mxGeometry></mxCell>
        <mxCell id="78" value="OV 01" style="text;align=center;fontStyle=1" parent="1" vertex="1"><mxGeometry x="1234" y="408" width="70" height="26" as="geometry"/></mxCell>
        <mxCell id="79" value="OV 02" style="text;align=center;fontStyle=1" parent="1" vertex="1"><mxGeometry x="1355" y="408" width="70" height="26" as="geometry"/></mxCell>
        <mxCell id="80" value="RT 01" style="text;align=center;fontStyle=1" parent="1" vertex="1"><mxGeometry x="1019" y="330.5" width="70" height="26" as="geometry"/></mxCell>
        <mxCell id="81" value="OT 01" style="text;align=center;fontStyle=1" parent="1" vertex="1"><mxGeometry x="554" y="421" width="70" height="26" as="geometry"/></mxCell>
        <mxCell id="82" value="OM 01" style="text;align=center;fontStyle=1" parent="1" vertex="1"><mxGeometry x="759" y="830" width="70" height="26" as="geometry"/></mxCell>
        <mxCell id="83" value="N-WC-303" style="shape=mxgraph.arrows.signal-in_arrow;fillColor=white;strokeColor=black;strokeWidth=1" parent="1" vertex="1"><mxGeometry x="1599" y="969" width="80" height="30" as="geometry"/></mxCell>
        <mxCell id="84" value="Water to Cooler 01" style="text" parent="1" vertex="1"><mxGeometry x="1579" y="936" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="85" value="1" parent="1" vertex="1"><mxGeometry x="1569" y="969" width="30" height="30" as="geometry"/></mxCell>
        <mxCell id="86" value="N-RO-302" style="shape=mxgraph.arrows.signal-in_arrow;fillColor=white;strokeColor=black;strokeWidth=1" parent="1" vertex="1"><mxGeometry x="1594" y="695.5" width="80" height="30" as="geometry"/></mxCell>
        <mxCell id="87" value="Refined Oil to ROT-02" style="text" parent="1" vertex="1"><mxGeometry x="1574" y="662.5" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="88" value="1" parent="1" vertex="1"><mxGeometry x="1564" y="695.5" width="30" height="30" as="geometry"/></mxCell>
        <mxCell id="89" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;entryX=0;entryY=0.67;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="4" target="102" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1044" y="981"/></Array></mxGeometry></mxCell>
        <mxCell id="90" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;entryX=0;entryY=0.67;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="2" target="104" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1434" y="708"/></Array></mxGeometry></mxCell>
        <mxCell id="93" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="624" y="730" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="94" value="1210" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="624" y="749" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="95" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="944" y="460" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="96" value="1209" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="944" y="479" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="97" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1404" y="635.5" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="98" value="1211" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1404" y="654.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="99" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;entryX=0;entryY=0.67;entryPerimeter=0;endArrow=none;rounded=0" parent="1" source="97" target="104" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="1454" y="708"/></Array></mxGeometry></mxCell>
        <mxCell id="100" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="95" target="5" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="994" y="520"/></Array></mxGeometry></mxCell>
        <mxCell id="101" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="93" target="4" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/><Array as="points"><mxPoint x="674" y="790"/></Array></mxGeometry></mxCell>
        <mxCell id="102" value="" style="shape=mxgraph.pid.valves.motor_operated_valve;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1318" y="936" width="64" height="67.5" as="geometry"/></mxCell>
        <mxCell id="103" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=1;exitY=0.67;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="102" target="85" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="104" value="" style="shape=mxgraph.pid.valves.motor_operated_valve;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1482" y="662.5" width="64" height="67.5" as="geometry"/></mxCell>
        <mxCell id="106" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=1;exitY=0.67;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="104" target="88" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="107" value="" style="shape=mxgraph.pid.instruments.flow_transmitter;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1330" y="860" width="40" height="38.5" as="geometry"/></mxCell>
        <mxCell id="108" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="107" target="102" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="109" value="" style="shape=mxgraph.pid.instruments.flow_transmitter;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1494" y="594.5" width="40" height="38.5" as="geometry"/></mxCell>
        <mxCell id="112" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=0.5;exitY=1;exitPerimeter=0;endArrow=none;rounded=0" parent="1" source="109" target="104" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="113" value="1212" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1290" y="868.75" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="114" value="1213" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1454" y="603.25" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="115" value="10'' CWS" style="text" parent="1" vertex="1"><mxGeometry x="888" y="253" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="116" value="5'' GWS" style="text" parent="1" vertex="1"><mxGeometry x="384" y="307" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="117" value="5'' OWS" style="text" parent="1" vertex="1"><mxGeometry x="1310" y="266" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="119" value="" style="fillColor=none;strokeColor=none" parent="1" vertex="1"><mxGeometry x="794" y="307" width="50" height="60" as="geometry"/></mxCell>
        <mxCell id="120" value="" style="edgeStyle=elbowEdgeStyle;elbow=vertical;exitX=1;exitY=0.067;exitPerimeter=0;endArrow=none" parent="1" source="6" target="119" edge="1"><mxGeometry x="4" y="10" width="100" height="100" as="geometry"><mxPoint x="4" y="110" as="sourcePoint"/><mxPoint x="104" y="10" as="targetPoint"/></mxGeometry></mxCell>
        <mxCell id="121" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="384" y="77" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="122" value="1201" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="384" y="96" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="125" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="434" y="76" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="126" value="1202" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="434" y="95.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="127" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="702" y="76" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="128" value="1203" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="702" y="95.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="129" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="624" y="76" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="130" value="1210" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="624" y="95.5" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="131" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="944" y="77" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="132" value="1209" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="944" y="96" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="133" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="888" y="77" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="134" value="1204" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="888" y="97" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="135" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="999" y="77" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="136" value="1204" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="999" y="97" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="137" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1184" y="77" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="138" value="1205" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1184" y="97" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="139" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1127" y="77" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="140" value="1206" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1127" y="97" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="141" value="" style="shape=mxgraph.pid.instruments.flow_transmitter;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1320" y="78" width="40" height="38.5" as="geometry"/></mxCell>
        <mxCell id="142" value="1212" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1280" y="86.75" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="143" value="" style="shape=mxgraph.pid.instruments.pressure_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1370" y="77.25" width="40" height="38" as="geometry"/></mxCell>
        <mxCell id="144" value="1211" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1370" y="96.25" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="145" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1424" y="77" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="146" value="1207" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1424" y="97" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="147" value="" style="shape=mxgraph.pid.instruments.level_transmitter_2;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1474" y="78" width="40" height="40" as="geometry"/></mxCell>
        <mxCell id="148" value="1208" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1474" y="98" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="149" value="" style="shape=mxgraph.pid.instruments.flow_transmitter;fillColor=white;strokeColor=black" parent="1" vertex="1"><mxGeometry x="1574" y="78.25" width="40" height="38.5" as="geometry"/></mxCell>
        <mxCell id="150" value="1213" style="text;fontSize=8;align=center" parent="1" vertex="1"><mxGeometry x="1534" y="87" width="40" height="21" as="geometry"/></mxCell>
        <mxCell id="151" value="SCADA" style="horizontal=0" parent="1" vertex="1"><mxGeometry x="34" y="30" width="20" height="100" as="geometry"/></mxCell>
        <mxCell id="152" value="PRESS" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="384" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="153" value="PRESS" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="434" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="154" value="PRESS" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="624" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="155" value="PRESS" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="702" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="156" value="LEVEL" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="888" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="157" value="LEVEL" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="999" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="158" value="LEVEL" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1127" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="159" value="LEVEL" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1184" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="160" value="LEVEL" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1425" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="161" value="LEVEL" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1474" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="162" value="PRESS" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="944" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="163" value="PRESS" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1370" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="164" value="FLOW" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1320" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="165" value="FLOW" style="text;align=center;fontSize=10" parent="1" vertex="1"><mxGeometry x="1574" y="40" width="40" height="26" as="geometry"/></mxCell>
        <mxCell id="181" value="A" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="34" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="182" value="B" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="180" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="183" value="C" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="326" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="184" value="D" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="472" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="185" value="E" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="618" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="186" value="F" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="764." y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="187" value="G" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="910" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="188" value="H" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="1056" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="189" value="I" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="1202" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="190" value="J" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="1351" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="191" value="K" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="1496" y="10" width="146" height="20" as="geometry"/></mxCell>
        <mxCell id="192" value="" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="1642" y="10" width="92.44444444444457" height="20" as="geometry"/></mxCell>
        <mxCell id="193" value="1" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="30" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="194" value="2" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="130" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="195" value="3" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="229" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="196" value="4" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="329" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="197" value="5" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="429" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="198" value="6" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="529" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="199" value="7" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="629" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="200" value="8" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="729.0" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="202" value="9" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="829" width="22" height="100" as="geometry"/></mxCell>
        <mxCell id="203" value="10" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="929" width="22" height="92" as="geometry"/></mxCell>
        <mxCell id="204" value="" style="strokeWidth=3" parent="1" vertex="1"><mxGeometry x="12" y="1020" width="22" height="150" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **ISA instrument tags**: 4-digit numeric IDs (1201–1213) as `text;fontSize=8;align=center` cells positioned below each instrument
2. **Equipment labels**: bold text cells with equipment IDs (OT 01, OM 01, RT 01, OV 01/02)
3. **SCADA/RTU row**: horizontal band at top (y=30–230) with duplicated instrument symbols and type labels
4. **Elbow edge routing**: `edgeStyle=elbowEdgeStyle;elbow=horizontal` or `elbow=vertical` for pipe routing
5. **Grid reference frame**: lettered columns (A–K) and numbered rows (1–10) as border cells with `strokeWidth=3`
6. **Title block**: multi-cell table at bottom (y=1020) — company name, plant ID, page numbers
7. **Signal arrows**: `mxgraph.arrows.signal-in_arrow` for off-sheet process connections (crude oil in, refined oil out, water out)
8. **Pipe labels**: inline text on edges (e.g., `10'' CWS`, `5'' GWS`, `5'' OWS`) for pipe size and service
