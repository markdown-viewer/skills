# Home Floor Plan

A 2-bedroom apartment floor plan with open-plan living/kitchen area, bathroom, and entrance.

Based on templates: `plans/floor_plan_1.drawio`, `plans/floor_plan_2.drawio`, `plans/interior_design_1.drawio`

## Key Elements

| Component | Shape / Stencil | fillColor | strokeColor |
|-----------|----------------|-----------|-------------|
| Wall (straight) | `mxgraph.floorplan.wall` | `#000000` | — |
| Door (left swing) | `mxgraph.floorplan.doorLeft` | `#FFFFFF` | — |
| Door (right swing) | `mxgraph.floorplan.doorRight` | `#FFFFFF` | — |
| Window | `mxgraph.floorplan.window` | `#ffffff` | — |
| Double Bed | `mxgraph.floorplan.bed_double` | `#FFFFFF` | — |
| Single Bed | `mxgraph.floorplan.bed_single` | `#FFFFFF` | — |
| Bathtub | `mxgraph.floorplan.bathtub` | `#FFFFFF` | — |
| Toilet | `mxgraph.floorplan.toilet` | `#FFFFFF` | — |
| Sink | `mxgraph.floorplan.sink_1` | `#FFFFFF` | — |
| Couch | `mxgraph.floorplan.couch` | `#FFFFFF` | — |
| Sofa | `mxgraph.floorplan.sofa` | `#FFFFFF` | — |
| Table | `mxgraph.floorplan.table` | `#FFFFFF` | — |
| Chair | `mxgraph.floorplan.chair` | `#ffffff` | `#000000` |
| Office Chair | `mxgraph.floorplan.office_chair` | `#ffffff` | `#000000` |
| Flat TV | `mxgraph.floorplan.flat_tv` | `#FFFFFF` | — |
| Dresser | `mxgraph.floorplan.dresser` | `#FFFFFF` | — |
| Bookcase | `mxgraph.floorplan.bookcase` | `#FFFFFF` | — |
| Floor Lamp | `mxgraph.floorplan.floor_lamp` | `#FFFFFF` | — |
| Plant | `mxgraph.floorplan.plant` | `#FFFFFF` | — |
| Kitchen Sink | `mxgraph.floorplan.sink_double` | `#FFFFFF` | — |
| Stove | `mxgraph.floorplan.range_1` | `#FFFFFF` | — |
| Refrigerator | `mxgraph.floorplan.refrigerator` | `#FFFFFF` | — |

- **Wall style**: `shape=mxgraph.floorplan.wall;fillColor=#000000` — 10px thick. Use `direction=south` for vertical walls
- **Door style**: `shape=mxgraph.floorplan.doorLeft;fillColor=#FFFFFF` — 80×85 geometry. Split wall into segments to leave 80px gap where door is placed
- **Window style**: `shape=mxgraph.floorplan.window;fillColor=#ffffff` — 10px in thin dimension, placed overlapping the exterior wall
- **Furniture**: All use `fillColor=#FFFFFF` (white fill) consistent with floorplan stencil conventions

## Example

2-bedroom apartment (~8.5m × 6.5m) with master bedroom, study/bedroom, bathroom, semi-open kitchen, and living/dining area:

```drawio

<mxfile host="app.diagrams.net" agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/144.0.0.0 Safari/537.36" version="29.3.8" pages="3">
  <diagram name="Home Network" id="eXQgznGGrTij0EQSsH-2">
    <mxGraphModel dx="1596" dy="1110" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="1169" pageHeight="827" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="HvxwAYeQlGz0nul37BQV-1" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="850" x="-160" y="-10" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-2" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="650" width="10" x="-160" y="-10" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-3" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="650" width="10" x="680" y="-10" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-4" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="150" x="-160" y="630" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-5" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="620" x="70" y="630" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-6" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="300" width="10" x="140" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-7" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="300" width="10" x="310" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-8" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="120" x="-150" y="300" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-9" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="110" x="50" y="300" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-10" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="90" x="240" y="300" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-11" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="270" x="410" y="300" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-12" parent="1" style="shape=mxgraph.floorplan.wall;html=1;fillColor=#000000;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="120" width="10" x="390" y="510" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-13" parent="1" style="shape=mxgraph.floorplan.window;html=1;fillColor=#ffffff;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="120" x="-70" y="-10" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-14" parent="1" style="shape=mxgraph.floorplan.window;html=1;fillColor=#ffffff;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="160" x="420" y="-10" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-15" parent="1" style="shape=mxgraph.floorplan.window;html=1;fillColor=#ffffff;strokeWidth=1;" value="" vertex="1"><mxGeometry height="10" width="120" x="140" y="630" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-16" parent="1" style="shape=mxgraph.floorplan.window;html=1;fillColor=#ffffff;direction=south;strokeWidth=1;" value="" vertex="1"><mxGeometry height="80" width="10" x="680" y="420" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-17" parent="1" style="shape=mxgraph.floorplan.doorLeft;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="-30" y="302" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-18" parent="1" style="shape=mxgraph.floorplan.doorRight;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="160" y="302" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-19" parent="1" style="shape=mxgraph.floorplan.doorLeft;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="330" y="302" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-20" parent="1" style="shape=mxgraph.floorplan.doorLeft;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="85" width="80" x="-10" y="633" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-21" parent="1" style="shape=mxgraph.floorplan.bed_double;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="200" width="170" x="-135" y="20" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-22" parent="1" style="shape=mxgraph.floorplan.floor_lamp;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="30" width="30" x="60" y="20" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-23" parent="1" style="shape=mxgraph.floorplan.dresser;html=1;fillColor=#FFFFFF;strokeWidth=1;flipV=1;" value="" vertex="1"><mxGeometry height="30" width="70" x="60" y="245" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-24" parent="1" style="shape=mxgraph.floorplan.bathtub;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="55" width="140" x="160" y="15" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-25" parent="1" style="shape=mxgraph.floorplan.sink_1;html=1;fillColor=#FFFFFF;strokeWidth=1;rotation=90;" value="" vertex="1"><mxGeometry height="35" width="40" x="270" y="220" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-26" parent="1" style="shape=mxgraph.floorplan.toilet;html=1;fillColor=#FFFFFF;strokeWidth=1;flipV=1;rotation=-90;" value="" vertex="1"><mxGeometry height="67" width="50" x="250" y="123" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-27" parent="1" style="shape=mxgraph.floorplan.bed_single;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="200" width="100" x="560" y="20" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-28" parent="1" style="shape=rect;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="50" width="130" x="330" y="15" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-29" parent="1" style="shape=mxgraph.floorplan.workstation;html=1;fillColor=#ffffff;strokeColor=#000000;flipV=1;rotation=180;" value="" vertex="1"><mxGeometry height="40" width="50" x="375" y="20" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-30" parent="1" style="shape=mxgraph.floorplan.office_chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="43" width="40" x="375" y="80" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-31" parent="1" style="shape=mxgraph.floorplan.bookcase;html=1;fillColor=#FFFFFF;strokeWidth=1;flipV=1;" value="" vertex="1"><mxGeometry height="25" width="130" x="525" y="260" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-32" parent="1" style="shape=mxgraph.floorplan.couch;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="70" width="170" x="-145" y="440" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-33" parent="1" style="shape=mxgraph.floorplan.sofa;html=1;fillColor=#FFFFFF;strokeWidth=1;rotation=90;" value="" vertex="1"><mxGeometry height="60" width="68" x="50" y="455" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-34" parent="1" style="shape=mxgraph.floorplan.table;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="50" width="100" x="-110" y="530" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-35" parent="1" style="shape=mxgraph.floorplan.flat_tv;html=1;fillColor=#FFFFFF;strokeWidth=1;flipV=1;" value="" vertex="1"><mxGeometry height="10" width="100" x="-110" y="620" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-36" parent="1" style="shape=mxgraph.floorplan.plant;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="45" width="40" x="330" y="585" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-37" parent="1" style="shape=mxgraph.floorplan.table;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="70" width="120" x="190" y="480" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-38" parent="1" style="shape=mxgraph.floorplan.chair;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="35" width="30" x="220" y="445" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-39" parent="1" style="shape=mxgraph.floorplan.chair;html=1;fillColor=#ffffff;strokeColor=#000000;" value="" vertex="1"><mxGeometry height="35" width="30" x="265" y="445" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-40" parent="1" style="shape=mxgraph.floorplan.chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="35" width="30" x="220" y="550" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-41" parent="1" style="shape=mxgraph.floorplan.chair;html=1;fillColor=#ffffff;strokeColor=#000000;rotation=180;" value="" vertex="1"><mxGeometry height="35" width="30" x="265" y="550" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-42" parent="1" style="shape=mxgraph.floorplan.sink_double;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="35" width="60" x="415" y="315" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-43" parent="1" style="shape=mxgraph.floorplan.range_1;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="55" width="55" x="490" y="315" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-44" parent="1" style="shape=mxgraph.floorplan.refrigerator;html=1;fillColor=#FFFFFF;strokeWidth=1;" value="" vertex="1"><mxGeometry height="60" width="55" x="610" y="315" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-45" parent="1" style="text;html=1;fontSize=10;fontStyle=1;fontColor=#333333;align=center;" value="Master Bedroom&#xa;2.9m × 3.0m" vertex="1"><mxGeometry height="30" width="130" x="-90" y="230" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-46" parent="1" style="text;html=1;fontSize=9;fontStyle=1;fontColor=#333333;align=center;" value="Bathroom" vertex="1"><mxGeometry height="20" width="80" x="185" y="220" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-47" parent="1" style="text;html=1;fontSize=10;fontStyle=1;fontColor=#333333;align=center;" value="Bedroom 2&#xa;3.6m × 3.0m" vertex="1"><mxGeometry height="30" width="120" x="430" y="210" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-48" parent="1" style="text;html=1;fontSize=11;fontStyle=1;fontColor=#333333;align=center;" value="Living Room" vertex="1"><mxGeometry height="20" width="110" x="-100" y="400" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-49" parent="1" style="text;html=1;fontSize=10;fontStyle=1;fontColor=#333333;align=center;" value="Kitchen&#xa;2.8m × 3.2m" vertex="1"><mxGeometry height="30" width="110" x="480" y="490" as="geometry" /></mxCell>
        <mxCell id="HvxwAYeQlGz0nul37BQV-50" parent="1" style="text;html=1;fontSize=9;fontStyle=0;fontColor=#666666;align=center;" value="Entrance" vertex="1"><mxGeometry height="15" width="65" x="-2" y="655" as="geometry" /></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **Walls use `mxgraph.floorplan.wall`** with `fillColor=#000000` and thickness 10px. Horizontal walls use default direction; vertical walls use `direction=south`. Split walls into segments to create door openings
2. **Doors placed at wall openings** — split the wall into 2 segments with an 80px gap, then place `doorLeft`/`doorRight` (80×85) at the gap edge. Use `flipV`/`flipH` or `rotation` to control swing direction
3. **Windows overlap walls** — place `mxgraph.floorplan.window` (`fillColor=#ffffff`, 10px thick) directly on top of exterior walls. The white fill visually replaces the black wall. Use `direction=south` (or `rotation=90`) for windows on vertical walls
4. **All furniture uses white fill** — `fillColor=#FFFFFF` (or `#ffffff`) with optional `strokeColor=#000000`. This is the standard convention for draw.io floorplan stencils
5. **Room labels** use `text` cells with `fontStyle=1` (bold) and `fontColor=#333333`. Room dimensions can be included on a second line with `&#xa;` line break
6. **No floor/background fills** — standard floor plans leave rooms unfilled. Wall structure alone defines room boundaries
7. **Scale convention** — 10px ≈ 10cm. A standard door is 80px = 80cm wide. Maintain consistent scale throughout the diagram
8. **Furniture clearance** — never place furniture in a door’s swing arc or blocking the doorway path. Plan door positions first, then arrange furniture in the remaining clear space
9. **Spatial diagram** — floor plans are purely spatial with no connecting edges. Furniture shapes are positioned within room boundaries defined by walls
