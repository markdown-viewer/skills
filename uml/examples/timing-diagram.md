# Timing Diagram

**Purpose**: Shows the state changes of objects over time.

**Key Elements**:
- Frame: `shape=umlFrame;width=130;fontStyle=1` - "td" prefix for timing diagram
- State labels: `text;align=right;verticalAlign=middle`
- Timeline: `line;strokeWidth=2`
- Tick marks: `line;strokeWidth=2;direction=south`
- Waypoints: `shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0`
- State lines: `curved=1;endArrow=none;endFill=0`

## Example

Parking system timing diagram showing multiple lifelines, time constraints, message triggers, and both full and compact notations:

```drawio
<mxfile><diagram id="timing-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1169" pageHeight="827" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="frame" value="td Parking System" style="shape=umlFrame;whiteSpace=wrap;html=1;pointerEvents=0;recursiveResize=0;container=1;collapsible=0;width=150;fontStyle=1" parent="1" vertex="1"><mxGeometry x="30" y="20" width="720" height="480" as="geometry"/></mxCell>
  <mxCell id="lifeline1-label" value="GateController" style="text;html=1;align=center;verticalAlign=middle;fontSize=14;fontStyle=1;fillColor=#dae8fc;strokeColor=#6c8ebf;rounded=1;" parent="frame" vertex="1"><mxGeometry x="10" y="50" width="100" height="30" as="geometry"/></mxCell>
  <mxCell id="g-idle" value="idle" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="90" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="g-validate" value="validate" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="115" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="g-open" value="open" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="140" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="g-close" value="close" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="165" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp1" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="120" y="90" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp2" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="200" y="90" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp3" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="200" y="115" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp4" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="280" y="115" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp5" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="280" y="140" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp6" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="440" y="140" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp7" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="440" y="165" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp8" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="520" y="165" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp9" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="520" y="90" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-wp10" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="660" y="90" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="g-line1" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp1" target="g-wp2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line2" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp2" target="g-wp3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line3" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp3" target="g-wp4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line4" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp4" target="g-wp5" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line5" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp5" target="g-wp6" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line6" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp6" target="g-wp7" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line7" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp7" target="g-wp8" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line8" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp8" target="g-wp9" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="g-line9" style="curved=1;endArrow=none;endFill=0;strokeColor=#6c8ebf;strokeWidth=2;" parent="frame" source="g-wp9" target="g-wp10" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="timeline1" value="" style="line;strokeWidth=2;html=1;" parent="frame" vertex="1"><mxGeometry x="70" y="195" width="620" height="10" as="geometry"/></mxCell>
  <mxCell id="t1-tick0" value="0" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="130" y="195" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t1-tick1" value="1" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="210" y="195" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t1-tick2" value="2" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="290" y="195" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t1-tick3" value="5" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="450" y="195" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t1-tick4" value="6" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="530" y="195" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t1-tick5" value="8 sec" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="670" y="195" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="lifeline2-label" value="Sensor" style="text;html=1;align=center;verticalAlign=middle;fontSize=14;fontStyle=1;fillColor=#d5e8d4;strokeColor=#82b366;rounded=1;" parent="frame" vertex="1"><mxGeometry x="10" y="230" width="100" height="30" as="geometry"/></mxCell>
  <mxCell id="s-idle1" value="Idle" style="shape=partialRectangle;whiteSpace=wrap;html=1;left=0;right=0;fillColor=none;fontSize=10;" parent="frame" vertex="1"><mxGeometry x="120" y="270" width="80" height="25" as="geometry"/></mxCell>
  <mxCell id="s-detect" value="Detect" style="shape=partialRectangle;whiteSpace=wrap;html=1;left=0;right=0;fillColor=#d5e8d4;strokeColor=#82b366;fontSize=10;" parent="frame" vertex="1"><mxGeometry x="200" y="270" width="240" height="25" as="geometry"/></mxCell>
  <mxCell id="s-idle2" value="Idle" style="shape=partialRectangle;whiteSpace=wrap;html=1;left=0;right=0;fillColor=none;fontSize=10;" parent="frame" vertex="1"><mxGeometry x="440" y="270" width="240" height="25" as="geometry"/></mxCell>
  <mxCell id="s-line1" style="curved=1;endArrow=none;endFill=0;strokeColor=#82b366;strokeWidth=2;exitX=1;exitY=0;exitDx=0;exitDy=0;entryX=0;entryY=1;entryDx=0;entryDy=0;" parent="frame" source="s-idle1" target="s-detect" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="s-line2" style="curved=1;endArrow=none;endFill=0;strokeColor=#82b366;strokeWidth=2;exitX=1;exitY=0;exitDx=0;exitDy=0;entryX=0;entryY=1;entryDx=0;entryDy=0;" parent="frame" source="s-detect" target="s-idle2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="lifeline3-label" value="Barrier" style="text;html=1;align=center;verticalAlign=middle;fontSize=14;fontStyle=1;fillColor=#ffe6cc;strokeColor=#d79b00;rounded=1;" parent="frame" vertex="1"><mxGeometry x="10" y="310" width="100" height="30" as="geometry"/></mxCell>
  <mxCell id="b-down" value="down" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="350" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="b-raising" value="raising" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="375" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="b-up" value="up" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="400" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="b-lowering" value="lowering" style="text;html=1;align=right;verticalAlign=middle;fontSize=11;" parent="frame" vertex="1"><mxGeometry x="15" y="425" width="50" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp1" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="120" y="350" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp2" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="280" y="350" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp3" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="280" y="375" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp4" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="320" y="375" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp5" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="320" y="400" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp6" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="440" y="400" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp7" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="440" y="425" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp8" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="520" y="425" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp9" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="520" y="350" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-wp10" value="" style="shape=waypoint;size=6;fillColor=none;resizable=0;rotatable=0;" parent="frame" vertex="1"><mxGeometry x="660" y="350" width="20" height="20" as="geometry"/></mxCell>
  <mxCell id="b-line1" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp1" target="b-wp2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line2" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp2" target="b-wp3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line3" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp3" target="b-wp4" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line4" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp4" target="b-wp5" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line5" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp5" target="b-wp6" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line6" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp6" target="b-wp7" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line7" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp7" target="b-wp8" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line8" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp8" target="b-wp9" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="b-line9" style="curved=1;endArrow=none;endFill=0;strokeColor=#d79b00;strokeWidth=2;" parent="frame" source="b-wp9" target="b-wp10" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="timeline2" value="" style="line;strokeWidth=2;html=1;" parent="frame" vertex="1"><mxGeometry x="70" y="455" width="620" height="10" as="geometry"/></mxCell>
  <mxCell id="t2-tick0" value="0" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="130" y="455" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t2-tick2" value="2" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="290" y="455" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t2-tick25" value="2.5" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="330" y="455" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t2-tick5" value="5" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="450" y="455" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t2-tick6" value="6" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="530" y="455" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="t2-tick8" value="8 sec" style="line;strokeWidth=2;direction=south;verticalAlign=bottom;spacingBottom=8;fontSize=9;" parent="frame" vertex="1"><mxGeometry x="670" y="455" width="10" height="12" as="geometry"/></mxCell>
  <mxCell id="dim1" value="3s (open time)" style="shape=dimension;whiteSpace=wrap;html=1;align=center;points=[];verticalAlign=bottom;spacingBottom=3;fontSize=10;fillColor=#fff2cc;strokeColor=#d6b656;" parent="frame" vertex="1"><mxGeometry x="290" y="138" width="150" height="20" as="geometry"/></mxCell>
  <mxCell id="dim2" value="0.5s" style="shape=dimension;whiteSpace=wrap;html=1;align=center;points=[];verticalAlign=bottom;spacingBottom=3;fontSize=10;fillColor=#fff2cc;strokeColor=#d6b656;" parent="frame" vertex="1"><mxGeometry x="290" y="418" width="30" height="16" as="geometry"/></mxCell>
  <mxCell id="msg1" value="ticket inserted" style="endArrow=classic;html=1;rounded=0;curved=1;fontSize=10;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" parent="frame" source="g-wp2" edge="1"><mxGeometry x="0.1" relative="1" as="geometry"><mxPoint x="210" y="270" as="targetPoint"/><mxPoint as="offset"/></mxGeometry></mxCell>
  <mxCell id="msg2" value="validated OK" style="endArrow=classic;html=1;rounded=0;curved=1;fontSize=10;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" parent="frame" source="g-wp5" edge="1"><mxGeometry relative="1" as="geometry"><mxPoint x="290" y="350" as="targetPoint"/></mxGeometry></mxCell>
  <mxCell id="msg3" value="car passed" style="endArrow=classic;html=1;rounded=0;curved=1;fontSize=10;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" parent="frame" source="b-wp6" target="g-wp6" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="event1" value="@ticket" style="text;html=1;align=center;verticalAlign=middle;fontSize=9;fontStyle=2;fillColor=#f5f5f5;strokeColor=#666666;rounded=1;" parent="frame" vertex="1"><mxGeometry x="180" y="75" width="50" height="16" as="geometry"/></mxCell>
  <mxCell id="event2" value="@timeout" style="text;html=1;align=center;verticalAlign=middle;fontSize=9;fontStyle=2;fillColor=#f5f5f5;strokeColor=#666666;rounded=1;" parent="frame" vertex="1"><mxGeometry x="420" y="155" width="55" height="16" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
