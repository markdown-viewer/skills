# Profile Diagram

**Purpose**: Shows UML extension mechanisms, defining custom stereotypes to extend UML metaclasses.

**Key Elements**:
- Profile package: `shape=folder;tabWidth=200;tabHeight=20;tabPosition=left;container=1`
- Metaclass box: `shape=rect` containing `<<metaclass>>` label
- Stereotype box: `shape=rect` containing `<<stereotype>>` label
- Extension arrow: `endArrow=block;endFill=1` (filled triangle)
- Apply relation: `dashed=1;endArrow=open;endSize=12`

## Example

Smart device Profile definition with multiple metaclasses, stereotypes, and profile applications:

```drawio
<mxfile><diagram id="profile-diagram-1" name="Page-1"><mxGraphModel dx="900" dy="620" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="900" pageHeight="620" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="mfr" value="Manufacturer" style="shape=folder;fontStyle=1;tabWidth=90;tabHeight=20;tabPosition=left;html=1;boundedLbl=1;whiteSpace=wrap;fillColor=#f5f5f5;strokeColor=#666666;" parent="1" vertex="1"><mxGeometry x="340" y="20" width="140" height="60" as="geometry"/></mxCell>
  <mxCell id="chromeOS" value="«profile»&#xa;ChromeOS" style="shape=folder;tabWidth=60;tabHeight=18;tabPosition=left;html=1;whiteSpace=wrap;align=center;" parent="1" vertex="1"><mxGeometry x="140" y="20" width="120" height="60" as="geometry"/></mxCell>        
  <mxCell id="interfaceProf" value="«profile»&#xa;Interface" style="shape=folder;tabWidth=60;tabHeight=18;tabPosition=left;html=1;whiteSpace=wrap;align=center;" parent="1" vertex="1"><mxGeometry x="560" y="20" width="120" height="60" as="geometry"/></mxCell>
  <mxCell id="profile" value="«profile» SmartDevice" style="shape=folder;fontStyle=1;tabWidth=150;tabHeight=22;tabPosition=left;html=1;boundedLbl=1;labelInHeader=1;container=1;collapsible=0;whiteSpace=wrap;fillColor=#dae8fc;strokeColor=#6c8ebf;" parent="1" vertex="1"><mxGeometry x="20" y="120" width="780" height="370" as="geometry"/></mxCell>
  <mxCell id="device" value="«metaclass»&#xa;Device" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#fff2cc;strokeColor=#d6b656;" parent="profile" vertex="1"><mxGeometry x="140" y="60" width="140" height="60" as="geometry"/></mxCell>
  <mxCell id="watch" value="«stereotype»&#xa;Watch" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="profile" vertex="1"><mxGeometry x="30" y="170" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="tablet" value="«stereotype»&#xa;Tablet" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="profile" vertex="1"><mxGeometry x="30" y="230" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="phone" value="«stereotype»&#xa;Phone" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="profile" vertex="1"><mxGeometry x="30" y="290" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="reqComp" value="«metaclass»&#xa;ReqComponent" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#fff2cc;strokeColor=#d6b656;" parent="profile" vertex="1"><mxGeometry x="380" y="60" width="140" height="60" as="geometry"/></mxCell>
  <mxCell id="optComp" value="«metaclass»&#xa;OptComponent" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#fff2cc;strokeColor=#d6b656;" parent="profile" vertex="1"><mxGeometry x="380" y="160" width="140" height="60" as="geometry"/></mxCell>
  <mxCell id="speaker" value="«stereotype»&#xa;Speaker" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="profile" vertex="1"><mxGeometry x="620" y="40" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="clock" value="«stereotype»&#xa;Clock" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="profile" vertex="1"><mxGeometry x="620" y="100" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="camera" value="«stereotype»&#xa;Camera" style="shape=rect;html=1;whiteSpace=wrap;align=center;fillColor=#d5e8d4;strokeColor=#82b366;" parent="profile" vertex="1"><mxGeometry x="620" y="180" width="120" height="50" as="geometry"/></mxCell>
  <mxCell id="ext1" style="curved=1;rounded=0;endArrow=block;endFill=1;endSize=10;" parent="profile" source="watch" target="device" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ext2" style="curved=1;rounded=0;endArrow=block;endFill=1;endSize=10;" parent="profile" source="tablet" target="device" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ext3" style="curved=1;rounded=0;endArrow=block;endFill=1;endSize=10;" parent="profile" source="phone" target="device" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ext4" style="curved=1;rounded=0;endArrow=block;endFill=1;endSize=10;" parent="profile" source="speaker" target="reqComp" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ext5" style="curved=1;rounded=0;endArrow=block;endFill=1;endSize=10;" parent="profile" source="clock" target="reqComp" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="ext6" style="curved=1;rounded=0;endArrow=block;endFill=1;endSize=10;" parent="profile" source="camera" target="optComp" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="req1" value="{required}" style="html=1;verticalAlign=bottom;endArrow=block;endFill=1;endSize=8;dashed=0;curved=1;fontSize=10;" parent="profile" source="reqComp" target="device" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="assoc1" style="curved=1;rounded=0;endArrow=none;endFill=0;" parent="profile" source="optComp" target="device" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="apply1" value="«apply»" style="html=1;endArrow=open;endSize=12;dashed=1;verticalAlign=bottom;curved=1;fontSize=10;" parent="1" source="mfr" target="profile" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="apply2" value="«apply»" style="html=1;endArrow=open;endSize=12;dashed=1;verticalAlign=bottom;curved=1;fontSize=10;" parent="1" source="mfr" target="chromeOS" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="apply3" value="«apply»" style="html=1;endArrow=open;endSize=12;dashed=1;verticalAlign=bottom;curved=1;fontSize=10;" parent="1" source="mfr" target="interfaceProf" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
