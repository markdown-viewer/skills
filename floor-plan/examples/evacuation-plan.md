# Evacuation Plan

An emergency evacuation floor plan with exit routes, fire equipment locations, and assembly point.

Based on templates: `plans/evacuation_plan_1.drawio`, `plans/evacuation_plan_2.drawio`

## Key Elements

| Component | Shape / Stencil | fillColor | strokeColor |
|-----------|----------------|-----------|-------------|
| Exterior Wall | `mxgraph.floorplan.wall` | `#000000` | — |
| Interior Wall | `mxgraph.floorplan.wall` | `#000000` | — |
| Wall Corner | `mxgraph.floorplan.wallCorner` | `#000000` | — |
| U-Wall | `mxgraph.floorplan.wallU` | `#000000` | — |
| Door (left swing) | `mxgraph.floorplan.doorLeft` | `#FFFFFF` | — |
| Door (right swing) | `mxgraph.floorplan.doorRight` | `#FFFFFF` | — |
| Window | `mxgraph.floorplan.window` | `#ffffff` | — |
| Fire Extinguisher | `mxgraph.pid.vessels.gas_bottle` | `#FF0000` | `#FFFFFF` |
| Fire Alarm | `mxgraph.signs.safety.non-ionizing_radiation` | `#FF0000` | `none` |
| First Aid Kit | `mxgraph.signs.healthcare.first_aid` | `#FF0000` | `none` |
| Evacuation Arrow | edge with `endArrow=block;endFill=1` | — | `#FF0000` |

- **Wall style**: `shape=mxgraph.floorplan.wall;fillColor=#000000` — use `direction=south` for vertical walls
- **Door style**: `shape=mxgraph.floorplan.doorLeft;fillColor=#FFFFFF` — use `rotation` and `flipH`/`flipV` to orient
- **Evacuation arrows**: `endArrow=block;endFill=1;strokeColor=#FF0000;strokeWidth=6` — thick red arrows pointing toward exits, using `mxPoint` source/target coordinates (no source/target cell IDs)
- **Safety symbols**: All use `fillColor=#FF0000;strokeColor=none` and 30×30 or similar size

## Safety Symbol Reference

| Symbol | Stencil | Size | Style |
|--------|---------|------|-------|
| Fire Extinguisher | `mxgraph.pid.vessels.gas_bottle` | 22×60 | `fillColor=#FF0000;strokeColor=#FFFFFF;strokeWidth=4` |
| Fire Alarm | `mxgraph.signs.safety.non-ionizing_radiation` | 47×40 | `fillColor=#FF0000;strokeColor=none` |
| First Aid Kit | `mxgraph.signs.healthcare.first_aid` | 30×30 | `fillColor=#FF0000;strokeColor=none` |
| Evacuation Route | edge (no shape) | — | `endArrow=block;endFill=1;strokeColor=#FF0000;strokeWidth=6` |

## Example

Small office evacuation plan with 2 exits, fire extinguishers, alarm, and first aid:

```drawio

<mxfile host="app.diagrams.net" agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/144.0.0.0 Safari/537.36" version="29.3.8" pages="3">
  <diagram name="Home Network" id="eXQgznGGrTij0EQSsH-2">
    <mxGraphModel dx="1596" dy="1110" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1169" pageHeight="827" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="0clUI7qCQcyf51FiKUfz-1" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="600" x="-40" y="-70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-2" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="440" width="10" x="-40" y="-70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-3" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="440" width="10" x="550" y="-70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-4" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="60" x="-40" y="360" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-5" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="200" x="100" y="360" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-6" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="180" x="380" y="360" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-7" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="240" x="50" y="170" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-8" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="60" width="10" x="290" y="-70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-9" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="100" width="10" x="290" y="70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-10" parent="1" style="shape=mxgraph.floorplan.doorLeft;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="-30" y="172" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-11" parent="1" style="shape=mxgraph.floorplan.doorLeft;html=1;fillColor=#FFFFFF;strokeWidth=1;rotation=-90;flipH=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="295" y="-12" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-12" parent="1" style="shape=mxgraph.floorplan.doorLeft;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="20" y="363" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-13" parent="1" style="shape=mxgraph.floorplan.doorRight;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="300" y="363" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-14" parent="1" style="shape=mxgraph.floorplan.window;html=1;fillColor=#ffffff;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="100" x="60" y="-70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-15" parent="1" style="shape=mxgraph.floorplan.window;html=1;fillColor=#ffffff;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="100" x="360" y="-70" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-16" parent="1" style="shape=rect;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="50" width="100" y="-20" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-17" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="43" width="40" x="30" y="35" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-18" parent="1" style="shape=mxgraph.floorplan.workstation;html=1;fillColor=#ffffff;strokeColor=#000000;flipV=1;rotation=180;" value="" vertex="1"><mxGeometry height="40" width="50" x="25" y="-20" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-19" parent="1" style="shape=rect;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="50" width="100" x="140" y="-20" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-20" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="43" width="40" x="170" y="35" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-21" parent="1" style="shape=mxgraph.floorplan.workstation;html=1;fillColor=#ffffff;strokeColor=#000000;flipV=1;rotation=180;" value="" vertex="1"><mxGeometry height="40" width="50" x="165" y="-20" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-22" parent="1" style="shape=mxgraph.floorplan.table;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="50" width="90" x="410" y="6.5" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-23" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="33" width="30" x="420" y="-38.5" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-24" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="33" width="30" x="465" y="-38.5" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-25" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="33" width="30" x="420" y="66.5" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-26" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="33" width="30" x="465" y="66.5" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-27" parent="1" style="shape=mxgraph.floorplan.dresser;html=1;fillColor=#FFFFFF;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="50" width="120" x="75" y="180" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-28" parent="1" style="shape=mxgraph.floorplan.bookcase;html=1;fillColor=#FFFFFF;strokeColor=#000000;flipV=1;" value="" vertex="1"><mxGeometry height="30" width="105" x="440" y="200" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-29" parent="1" style="text;html=1;fontSize=14;fontStyle=1;fontColor=#333333;align=center;" value="Office" vertex="1"><mxGeometry height="25" width="80" x="60" y="110" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-30" parent="1" style="text;html=1;fontSize=14;fontStyle=1;fontColor=#333333;align=center;" value="Meeting Room" vertex="1"><mxGeometry height="25" width="120" x="390" y="107.5" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-31" parent="1" style="text;html=1;fontSize=12;fontStyle=0;fontColor=#666666;align=center;" value="Corridor" vertex="1"><mxGeometry height="20" width="80" x="210" y="250" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-32" parent="1" style="text;html=1;fontSize=12;fontStyle=1;fontColor=#00AA00;align=center;" value="EXIT 1" vertex="1"><mxGeometry height="20" width="70" x="25" y="450" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-33" parent="1" style="text;html=1;fontSize=12;fontStyle=1;fontColor=#00AA00;align=center;" value="EXIT 2" vertex="1"><mxGeometry height="20" width="70" x="305" y="450" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-34" parent="1" style="shape=mxgraph.pid.vessels.gas_bottle;html=1;fillColor=#FF0000;strokeColor=#FFFFFF;strokeWidth=4;" value="" vertex="1"><mxGeometry height="60" width="22" x="255" y="175" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-35" parent="1" style="shape=mxgraph.pid.vessels.gas_bottle;html=1;fillColor=#FF0000;strokeColor=#FFFFFF;strokeWidth=4;" value="" vertex="1"><mxGeometry height="60" width="22" x="510" y="80" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-36" parent="1" style="shape=mxgraph.signs.safety.non-ionizing_radiation;html=1;fillColor=#FF0000;strokeColor=none;" value="" vertex="1"><mxGeometry height="34" width="40" x="-28" y="230" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-37" parent="1" style="shape=mxgraph.signs.safety.non-ionizing_radiation;html=1;fillColor=#FF0000;strokeColor=none;" value="" vertex="1"><mxGeometry height="34" width="40" x="450" y="230" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-38" parent="1" style="shape=mxgraph.signs.healthcare.first_aid;html=1;fillColor=#FF0000;strokeColor=none;" value="" vertex="1"><mxGeometry height="30" width="30" x="210" y="200" as="geometry" /></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-39" edge="1" parent="1" style="endArrow=block;html=1;strokeColor=#FF0000;strokeWidth=6;endFill=1;" value=""><mxGeometry relative="1" as="geometry"><mxPoint x="110" y="100" as="sourcePoint" /><mxPoint x="60" y="360" as="targetPoint" /></mxGeometry></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-40" edge="1" parent="1" style="endArrow=block;html=1;strokeColor=#FF0000;strokeWidth=6;endFill=1;" value=""><mxGeometry relative="1" as="geometry"><mxPoint x="440" y="150" as="sourcePoint" /><mxPoint x="340" y="360" as="targetPoint" /></mxGeometry></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-41" edge="1" parent="1" style="endArrow=block;html=1;strokeColor=#FF0000;strokeWidth=6;endFill=1;" value=""><mxGeometry relative="1" as="geometry"><mxPoint x="160" y="280" as="sourcePoint" /><mxPoint x="60" y="360" as="targetPoint" /></mxGeometry></mxCell>
        <mxCell id="0clUI7qCQcyf51FiKUfz-42" edge="1" parent="1" style="endArrow=block;html=1;strokeColor=#FF0000;strokeWidth=6;endFill=1;" value=""><mxGeometry relative="1" as="geometry"><mxPoint x="360" y="280" as="sourcePoint" /><mxPoint x="340" y="360" as="targetPoint" /></mxGeometry></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>

```

## Pattern Notes

1. **Walls use `mxgraph.floorplan.*` stencils** — `wall` for straight segments, `wallCorner` for L-shapes, `wallU` for U-shaped enclosures. Fill is `#000000`. Use `direction=south` for vertical walls. Walls are typically 10px thick
2. **Doors must be placed at wall openings** — split wall segments to leave 80px gaps, then place `doorLeft`/`doorRight` (`fillColor=#FFFFFF`) in the gap so the door aligns with the wall edge. Use `rotation` (90, -90) and `flipH`/`flipV` to orient the swing direction
3. **Evacuation arrows** are edges (not shapes) with `endArrow=block;endFill=1;strokeColor=#FF0000;strokeWidth=6`. They use `mxPoint` coordinates for source/target instead of cell references — this allows precise freeform routing through corridors toward exits
4. **Fire extinguishers** use `mxgraph.pid.vessels.gas_bottle` (from PID library, not floorplan) with `fillColor=#FF0000;strokeColor=#FFFFFF;strokeWidth=4` — the white stroke on red fill creates the classic extinguisher silhouette
5. **Fire alarms** use `mxgraph.signs.safety.non-ionizing_radiation` with `fillColor=#FF0000;strokeColor=none` — placed near corridor intersections and exit doors
6. **First aid kits** use `mxgraph.signs.healthcare.first_aid` with `fillColor=#FF0000;strokeColor=none` — typically placed in reception or corridor areas
7. **EXIT labels** use `text` cells with `fontColor=#00AA00;fontStyle=1` (bold green) placed below/beside exit doors
8. **Spatial diagram** — evacuation plans are spatial (no topology edges between devices). Proximity and arrow direction convey the escape routes. Furniture shapes provide spatial context but are not connected with edges
