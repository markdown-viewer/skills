# P&ID - Simple Process Flow

A basic chemical process with pump, heat exchanger, reactor, and instrumentation.

```drawio
<mxfile>
  <diagram name="Simple P&amp;ID">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- Title -->
        <mxCell id="title" value="Simple Chemical Process P&amp;ID" style="text;fontSize=18;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="400" y="20" width="400" height="30" as="geometry"/>
        </mxCell>
        
        <!-- Feed Tank -->
        <mxCell id="tank1" value="T-101&#xa;Feed Tank" style="shape=mxgraph.pid.vessels.tank_(dished_roof);html=1;fillColor=#ffffff;strokeColor=#000000;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="100" y="150" width="80" height="120" as="geometry"/>
        </mxCell>
        
        <!-- Level Indicator on Tank -->
        <mxCell id="li101" value="LI&#xa;101" style="shape=mxgraph.pid.instruments.level_indicator;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="60" y="180" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Feed Pump -->
        <mxCell id="pump1" value="P-101&#xa;Feed Pump" style="shape=mxgraph.pid.pumps.centrifugal_pump_1;html=1;fillColor=#ffffff;strokeColor=#000000;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="250" y="320" width="60" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Flow Transmitter -->
        <mxCell id="ft101" value="FT&#xa;101" style="shape=mxgraph.pid.instruments.flow_transmitter;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="340" y="260" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Control Valve -->
        <mxCell id="fv101" value="FV-101" style="shape=mxgraph.pid.valves.valve_(globe);html=1;fillColor=#ffffff;strokeColor=#000000;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="420" y="330" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Heat Exchanger -->
        <mxCell id="hex1" value="E-101&#xa;Preheater" style="shape=mxgraph.pid.heat_exchangers.shell_and_tube_heat_exchanger_1;html=1;fillColor=#ffffff;strokeColor=#000000;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="520" y="320" width="80" height="80" as="geometry"/>
        </mxCell>
        
        <!-- Temperature Indicator -->
        <mxCell id="ti101" value="TI&#xa;101" style="shape=mxgraph.pid.instruments.temperature_indicator;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="620" y="260" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Reactor -->
        <mxCell id="reactor" value="R-101&#xa;Reactor" style="shape=mxgraph.pid.vessels.reactor;html=1;fillColor=#ffffff;strokeColor=#000000;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="720" y="200" width="100" height="150" as="geometry"/>
        </mxCell>
        
        <!-- Pressure Indicator -->
        <mxCell id="pi101" value="PI&#xa;101" style="shape=mxgraph.pid.instruments.pressure_indicator;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="840" y="180" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Temperature Transmitter -->
        <mxCell id="tt101" value="TT&#xa;101" style="shape=mxgraph.pid.instruments.temperature_transmitter;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="840" y="240" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Product Tank -->
        <mxCell id="tank2" value="T-102&#xa;Product" style="shape=mxgraph.pid.vessels.tank_(dished_roof);html=1;fillColor=#ffffff;strokeColor=#000000;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="940" y="250" width="80" height="120" as="geometry"/>
        </mxCell>
        
        <!-- Piping -->
        <!-- Tank to Pump -->
        <mxCell id="p1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="140" y="270" as="sourcePoint"/>
            <mxPoint x="140" y="350" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="p2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="140" y="350" as="sourcePoint"/>
            <mxPoint x="250" y="350" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Pump to Flow Transmitter area -->
        <mxCell id="p3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="310" y="350" as="sourcePoint"/>
            <mxPoint x="420" y="350" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Control Valve to HEX -->
        <mxCell id="p4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="460" y="350" as="sourcePoint"/>
            <mxPoint x="520" y="350" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- HEX to Reactor -->
        <mxCell id="p5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="600" y="360" as="sourcePoint"/>
            <mxPoint x="680" y="360" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="p6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="680" y="360" as="sourcePoint"/>
            <mxPoint x="680" y="300" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="p7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="680" y="300" as="sourcePoint"/>
            <mxPoint x="720" y="300" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Reactor to Product Tank -->
        <mxCell id="p8" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="820" y="300" as="sourcePoint"/>
            <mxPoint x="880" y="300" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="p9" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="880" y="300" as="sourcePoint"/>
            <mxPoint x="880" y="310" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="p10" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="880" y="310" as="sourcePoint"/>
            <mxPoint x="940" y="310" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Instrument Signal Lines (dashed) -->
        <mxCell id="s1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;dashed=1;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="360" y="300" as="sourcePoint"/>
            <mxPoint x="360" y="330" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Steam input to HEX -->
        <mxCell id="steam_in" value="Steam" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="540" y="420" width="40" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="ps1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#FF0000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="560" y="440" as="sourcePoint"/>
            <mxPoint x="560" y="400" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Condensate output from HEX -->
        <mxCell id="cond_out" value="Cond." style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="540" y="280" width="40" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="pc1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="560" y="320" as="sourcePoint"/>
            <mxPoint x="560" y="300" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Legend -->
        <mxCell id="legend" value="Legend" style="text;fontSize=12;fontStyle=1;fillColor=#f5f5f5;strokeColor=#666666;rounded=1;" vertex="1" parent="1">
          <mxGeometry x="100" y="450" width="200" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="leg1" value="━━ Process Pipe" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="100" y="475" width="100" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="leg2" value="- - - Signal Line" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="100" y="495" width="100" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="leg3" value="━━ Steam (Red)" style="text;fontSize=10;fillColor=none;strokeColor=none;fontColor=#FF0000;" vertex="1" parent="1">
          <mxGeometry x="200" y="475" width="100" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="leg4" value="━━ Condensate (Blue)" style="text;fontSize=10;fillColor=none;strokeColor=none;fontColor=#0000FF;" vertex="1" parent="1">
          <mxGeometry x="200" y="495" width="120" height="20" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/pid.md`:

| Component | Stencil |
|-----------|---------|
| Tank | `mxgraph.pid.vessels.tank_(dished_roof)` |
| Reactor | `mxgraph.pid.vessels.reactor` |
| Centrifugal Pump | `mxgraph.pid.pumps.centrifugal_pump_1` |
| Shell & Tube HEX | `mxgraph.pid.heat_exchangers.shell_and_tube_heat_exchanger_1` |
| Globe Valve | `mxgraph.pid.valves.valve_(globe)` |
| Level Indicator | `mxgraph.pid.instruments.level_indicator` |
| Flow Transmitter | `mxgraph.pid.instruments.flow_transmitter` |
| Temperature Indicator | `mxgraph.pid.instruments.temperature_indicator` |
| Temperature Transmitter | `mxgraph.pid.instruments.temperature_transmitter` |
| Pressure Indicator | `mxgraph.pid.instruments.pressure_indicator` |

## ISA Instrument Tag Format

- **LI-101**: Level Indicator, Loop 101
- **FT-101**: Flow Transmitter, Loop 101
- **FV-101**: Flow Valve (Control), Loop 101
- **TI-101**: Temperature Indicator, Loop 101
- **TT-101**: Temperature Transmitter, Loop 101
- **PI-101**: Pressure Indicator, Loop 101
