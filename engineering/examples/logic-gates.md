# Logic Gates - Digital Circuit

A basic digital logic circuit demonstrating common logic gates: AND, OR, NOT, NAND, and XOR.

```drawio
<mxfile>
  <diagram name="Logic Gates" id="logic-gates-diagram">
    <mxGraphModel dx="800" dy="600" grid="1" gridSize="10">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- Title -->
        <mxCell id="title" value="Digital Logic Circuit" style="text;fontSize=16;fontStyle=1;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="280" y="20" width="200" height="30" as="geometry"/>
        </mxCell>
        
        <!-- Input Signals -->
        <mxCell id="inputA" value="A" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="40" y="80" width="40" height="40" as="geometry"/>
        </mxCell>
        <mxCell id="inputB" value="B" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="40" y="180" width="40" height="40" as="geometry"/>
        </mxCell>
        <mxCell id="inputC" value="C" style="ellipse;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="40" y="280" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- NOT Gate (Inverter) -->
        <mxCell id="not1" value="" style="shape=mxgraph.electrical.logic_gates.inverter;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="140" y="270" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="not1_label" value="NOT" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="150" y="330" width="40" height="20" as="geometry"/>
        </mxCell>
        
        <!-- AND Gate -->
        <mxCell id="and1" value="" style="shape=mxgraph.electrical.logic_gates.and;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="260" y="120" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="and1_label" value="AND" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="270" y="180" width="40" height="20" as="geometry"/>
        </mxCell>
        
        <!-- OR Gate -->
        <mxCell id="or1" value="" style="shape=mxgraph.electrical.logic_gates.or;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="260" y="220" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="or1_label" value="OR" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="275" y="280" width="30" height="20" as="geometry"/>
        </mxCell>
        
        <!-- NAND Gate -->
        <mxCell id="nand1" value="" style="shape=mxgraph.electrical.logic_gates.nand;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="400" y="170" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="nand1_label" value="NAND" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="405" y="230" width="50" height="20" as="geometry"/>
        </mxCell>
        
        <!-- XOR Gate -->
        <mxCell id="xor1" value="" style="shape=mxgraph.electrical.logic_gates.xor;html=1;fillColor=#ffffff;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="520" y="170" width="60" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="xor1_label" value="XOR" style="text;fontSize=10;fillColor=none;strokeColor=none;" vertex="1" parent="1">
          <mxGeometry x="530" y="230" width="40" height="20" as="geometry"/>
        </mxCell>
        
        <!-- Output -->
        <mxCell id="output" value="Y" style="ellipse;whiteSpace=wrap;html=1;fillColor=#f8cecc;strokeColor=#b85450;" vertex="1" parent="1">
          <mxGeometry x="640" y="180" width="40" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Wires -->
        <!-- Input A to AND -->
        <mxCell id="w1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="80" y="100" as="sourcePoint"/>
            <mxPoint x="260" y="140" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="120" y="100"/>
              <mxPoint x="120" y="140"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- Input B to AND and OR -->
        <mxCell id="w2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="80" y="200" as="sourcePoint"/>
            <mxPoint x="260" y="160" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="220" y="200"/>
              <mxPoint x="220" y="160"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <mxCell id="w3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="220" y="200" as="sourcePoint"/>
            <mxPoint x="260" y="240" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="220" y="240"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- Input C to NOT -->
        <mxCell id="w4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="80" y="300" as="sourcePoint"/>
            <mxPoint x="140" y="300" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- NOT to OR -->
        <mxCell id="w5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="200" y="300" as="sourcePoint"/>
            <mxPoint x="260" y="260" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="230" y="300"/>
              <mxPoint x="230" y="260"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- AND to NAND -->
        <mxCell id="w6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="320" y="150" as="sourcePoint"/>
            <mxPoint x="400" y="190" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="360" y="150"/>
              <mxPoint x="360" y="190"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- OR to NAND -->
        <mxCell id="w7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="320" y="250" as="sourcePoint"/>
            <mxPoint x="400" y="210" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="360" y="250"/>
              <mxPoint x="360" y="210"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- NAND to XOR -->
        <mxCell id="w8" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="460" y="200" as="sourcePoint"/>
            <mxPoint x="520" y="190" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="490" y="200"/>
              <mxPoint x="490" y="190"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- Input A branch to XOR -->
        <mxCell id="w9" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="120" y="100" as="sourcePoint"/>
            <mxPoint x="520" y="210" as="targetPoint"/>
            <Array as="points">
              <mxPoint x="120" y="60"/>
              <mxPoint x="500" y="60"/>
              <mxPoint x="500" y="210"/>
            </Array>
          </mxGeometry>
        </mxCell>
        
        <!-- XOR to Output -->
        <mxCell id="w10" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeWidth=1;strokeColor=#000000;endArrow=none;" edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="580" y="200" as="sourcePoint"/>
            <mxPoint x="640" y="200" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        
        <!-- Junction Points -->
        <mxCell id="j1" value="" style="ellipse;whiteSpace=wrap;html=1;fillColor=#000000;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="118" y="98" width="4" height="4" as="geometry"/>
        </mxCell>
        <mxCell id="j2" value="" style="ellipse;whiteSpace=wrap;html=1;fillColor=#000000;strokeColor=#000000;" vertex="1" parent="1">
          <mxGeometry x="218" y="198" width="4" height="4" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names verified from `skills/drawio/stencils/electrical.md`:

| Component | Stencil |
|-----------|---------|
| Inverter (NOT) | `mxgraph.electrical.logic_gates.inverter` |
| AND Gate | `mxgraph.electrical.logic_gates.and` |
| OR Gate | `mxgraph.electrical.logic_gates.or` |
| NAND Gate | `mxgraph.electrical.logic_gates.nand` |
| XOR Gate | `mxgraph.electrical.logic_gates.xor` |

## Logic Function

The circuit implements: **Y = (A AND B) NAND (B OR NOT C) XOR A**

- Inputs: A, B, C (green circles)
- Output: Y (red circle)
- Junction points show wire connections
