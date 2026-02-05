# Fluid Power - Hydraulic Circuit

A basic hydraulic circuit with pump, directional control valve, and double-acting cylinder.

```drawio
<mxfile>
  <diagram name="Hydraulic Circuit" id="hydraulic-circuit">
    <mxGraphModel dx="800" dy="600" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- Title -->
        <mxCell id="title" value="Basic Hydraulic Circuit" style="text;fontSize=16;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="260" y="20" width="200" height="30" as="geometry"/>
        </mxCell>
        
        <!-- Reservoir (Tank) -->
        <mxCell id="tank" value="" style="shape=mxgraph.fluid_power.x11490;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="80" y="400" width="60" height="40" as="geometry"/>
        </mxCell>
        <mxCell id="tank_label" value="Tank" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="90" y="445" width="40" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Hydraulic Pump -->
        <mxCell id="pump" value="" style="shape=mxgraph.fluid_power.x11350;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="80" y="300" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="pump_label" value="Pump" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="85" y="360" width="50" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Electric Motor -->
        <mxCell id="motor" value="M" style="ellipse;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="170" y="310" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Pressure Relief Valve -->
        <mxCell id="prv" value="" style="shape=mxgraph.fluid_power.x11180;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="80" y="200" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="prv_label" value="PRV" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="85" y="260" width="50" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Filter -->
        <mxCell id="filter" value="" style="shape=mxgraph.fluid_power.x11510;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="200" y="200" width="40" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="filter_label" value="Filter" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="200" y="260" width="40" height="20" as="geometry"/>
        </mxCell>
        
        <!-- 4/3 Directional Control Valve -->
        <mxCell id="dcv" value="" style="shape=mxgraph.fluid_power.x10300;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="300" y="200" width="100" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="dcv_label" value="4/3 DCV" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="320" y="260" width="60" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Double Acting Cylinder -->
        <mxCell id="cylinder" value="" style="shape=mxgraph.fluid_power.x10590;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="480" y="180" width="100" height="100" as="geometry"/>
        </mxCell>
        <mxCell id="cyl_label" value="Cylinder" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="500" y="280" width="60" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Pressure Gauge -->
        <mxCell id="gauge" value="" style="shape=mxgraph.fluid_power.x11460;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="200" y="120" width="40" height="40" as="geometry"/>
        </mxCell>
        <mxCell id="gauge_label" value="P" style="text;fontSize=10;fillColor=none;strokeColor=none;align=center;" vertex="1" parent="1">
          <mxGeometry x="210" y="160" width="20" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Hydraulic Lines (Pressure - solid) -->
        <!-- Tank to Pump -->
        <mxCell id="line1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="110" y="400" as="sourcePoint"/>
            <mxPoint x="110" y="360" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Pump to PRV -->
        <mxCell id="line2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="110" y="300" as="sourcePoint"/>
            <mxPoint x="110" y="260" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- PRV to Filter -->
        <mxCell id="line3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="110" y="200" as="sourcePoint"/>
            <mxPoint x="200" y="230" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="110" y="170"/>
              <mxPoint x="180" y="170"/>
              <mxPoint x="180" y="230"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- Filter to DCV -->
        <mxCell id="line4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="240" y="230" as="sourcePoint"/>
            <mxPoint x="300" y="230" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- DCV to Cylinder (Port A) -->
        <mxCell id="line5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="400" y="215" as="sourcePoint"/>
            <mxPoint x="480" y="215" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- DCV to Cylinder (Port B) -->
        <mxCell id="line6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="400" y="245" as="sourcePoint"/>
            <mxPoint x="480" y="245" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Return Line (DCV to Tank) - dashed -->
        <mxCell id="line7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;dashed=1;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="350" y="260" as="sourcePoint"/>
            <mxPoint x="140" y="420" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="350" y="420"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- PRV Return to Tank - dashed -->
        <mxCell id="line8" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=2;strokeColor=#0000FF;dashed=1;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="80" y="230" as="sourcePoint"/>
            <mxPoint x="80" y="420" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="60" y="230"/>
              <mxPoint x="60" y="420"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- Pressure Gauge Connection -->
        <mxCell id="line9" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#0000FF;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="220" y="200" as="sourcePoint"/>
            <mxPoint x="220" y="160" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Motor connection -->
        <mxCell id="motor_conn" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="140" y="330" as="sourcePoint"/>
            <mxPoint x="170" y="330" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Legend -->
        <mxCell id="legend_box" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;" vertex="1" parent="1">
          <mxGeometry x="480" y="340" width="120" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="legend_title" value="Legend" style="text;fontSize=10;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="520" y="345" width="40" height="15" as="geometry"/>
        </mxCell>
        <mxCell id="legend1" value="━━ Pressure Line" style="text;fontSize=9;fillColor=none;strokeColor=none;fontColor=#0000FF;" vertex="1" parent="1">
          <mxGeometry x="490" y="365" width="100" height="15" as="geometry"/>
        </mxCell>
        <mxCell id="legend2" value="- - - Return Line" style="text;fontSize=9;fillColor=none;strokeColor=none;fontColor=#0000FF;" vertex="1" parent="1">
          <mxGeometry x="490" y="385" width="100" height="15" as="geometry"/>
        </mxCell>
        <mxCell id="legend3" value="━━ Mechanical" style="text;fontSize=9;fillColor=none;strokeColor=none;fontColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="490" y="405" width="100" height="15" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/fluid_power.md`:

| Component | Stencil | Description |
|-----------|---------|-------------|
| Reservoir | `mxgraph.fluid_power.x11490` | Hydraulic tank/reservoir |
| Pump | `mxgraph.fluid_power.x11350` | Fixed displacement pump |
| Relief Valve | `mxgraph.fluid_power.x11180` | Pressure relief valve |
| Filter | `mxgraph.fluid_power.x11510` | Line filter |
| 4/3 DCV | `mxgraph.fluid_power.x10300` | 4-way, 3-position directional control valve |
| Cylinder | `mxgraph.fluid_power.x10590` | Double-acting cylinder |
| Pressure Gauge | `mxgraph.fluid_power.x11460` | Pressure indicator |

## Circuit Description

1. **Power Unit**: Electric motor (M) drives the hydraulic pump
2. **Pressure Control**: Relief valve (PRV) limits maximum system pressure
3. **Filtration**: Filter cleans the hydraulic fluid
4. **Direction Control**: 4/3 DCV controls cylinder movement (extend/retract/hold)
5. **Actuator**: Double-acting cylinder converts hydraulic energy to linear motion

**Line Types:**
- Solid blue lines: Pressure lines (working fluid)
- Dashed blue lines: Return/drain lines (low pressure)
- Black lines: Mechanical connections
