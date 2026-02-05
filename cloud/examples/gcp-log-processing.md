# GCP Log Processing Pipeline

This example demonstrates a GCP architecture for log processing with batch and streaming paths.

Reference: Based on `temp/drawio/gcp/big_data_log_processing.drawio`

## Architecture Overview

Log data flows from microservices through two processing paths:
- **Batch Path**: Logs → Cloud Storage → Dataflow → BigQuery
- **Streaming Path**: Logs → Pub/Sub → Dataflow → BigQuery

## Key Components

| Service | Purpose |
|---------|---------|
| Kubernetes Engine | Runs microservices that generate logs |
| Logging | Collects logs from all services |
| Cloud Storage | Stores logs for batch processing |
| Pub/Sub | Streams logs in real-time |
| Dataflow | Processes logs (both batch and streaming) |
| BigQuery | Analytics warehouse for log data |

## GCP Stencils Used

This diagram uses `mxgraph.gcp2.*` stencils with embedded SVG icons:
- Service cards with shadow: `strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;`
- GCP Platform container: `fillColor=#F6F6F6;strokeColor=none;`
- Dashed group boxes: `strokeColor=#4284F3;fillColor=none;dashed=1;dashPattern=1 2;strokeWidth=2;`
- Flow arrows: `strokeColor=#4284F3;strokeWidth=2;endArrow=blockThin;endFill=1;`

## Diagram

```drawio
<mxfile>
  <diagram id="gcp-log-processing" name="Log Processing">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="600" background="none" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="title" value="Architecture: Big Data &gt; Log Processing" style="fillColor=#4DA1F5;strokeColor=none;shadow=1;fontSize=14;align=left;spacingLeft=50;fontColor=#ffffff;html=1;" vertex="1" parent="1"><mxGeometry x="40" y="40" width="1020" height="40" as="geometry"/></mxCell>
        <mxCell id="gcp-container" value="Google Cloud Platform" style="fillColor=#F6F6F6;strokeColor=none;shadow=0;fontSize=14;align=left;spacing=10;fontColor=#717171;verticalAlign=top;spacingTop=-4;spacingLeft=40;html=1;rounded=1;" vertex="1" parent="1"><mxGeometry x="60" y="100" width="980" height="450" as="geometry"/></mxCell>
        <mxCell id="batch-group" value="Batch" style="rounded=1;absoluteArcSize=1;arcSize=2;html=1;strokeColor=#4284F3;fillColor=none;dashed=1;fontSize=12;fontColor=#9E9E9E;align=left;verticalAlign=top;spacing=10;spacingTop=-4;dashPattern=1 2;strokeWidth=2;" vertex="1" parent="1"><mxGeometry x="380" y="180" width="280" height="120" as="geometry"/></mxCell>
        <mxCell id="stream-group" value="Streaming" style="rounded=1;absoluteArcSize=1;arcSize=2;html=1;strokeColor=#4284F3;fillColor=none;dashed=1;fontSize=12;fontColor=#9E9E9E;align=left;verticalAlign=top;spacing=10;spacingTop=-4;dashPattern=1 2;strokeWidth=2;" vertex="1" parent="1"><mxGeometry x="380" y="320" width="280" height="120" as="geometry"/></mxCell>
        <mxCell id="k8s-card" value="" style="strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;fillColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="90" y="200" width="180" height="60" as="geometry"/></mxCell>
        <mxCell id="k8s-icon" value="Microservices&#xa;Kubernetes Engine" style="shape=mxgraph.gcp2.container_engine_icon;html=1;fillColor=#5184F3;strokeColor=none;verticalLabelPosition=middle;verticalAlign=middle;labelPosition=right;align=left;spacingLeft=10;fontColor=#999999;fontSize=11;" vertex="1" parent="1"><mxGeometry x="105" y="215" width="27" height="30" as="geometry"/></mxCell>
        <mxCell id="logging-card" value="" style="strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;fillColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="90" y="310" width="180" height="60" as="geometry"/></mxCell>
        <mxCell id="logging-icon" value="Log Collection&#xa;Logging" style="shape=mxgraph.gcp2.logging;html=1;fillColor=#5184F3;strokeColor=none;verticalLabelPosition=middle;verticalAlign=middle;labelPosition=right;align=left;spacingLeft=10;fontColor=#999999;fontSize=11;" vertex="1" parent="1"><mxGeometry x="105" y="325" width="34" height="30" as="geometry"/></mxCell>
        <mxCell id="storage-card" value="" style="strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;fillColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="400" y="210" width="160" height="60" as="geometry"/></mxCell>
        <mxCell id="storage-icon" value="Log Storage&#xa;Cloud Storage" style="shape=mxgraph.gcp2.cloud_storage;html=1;fillColor=#5184F3;strokeColor=none;verticalLabelPosition=middle;verticalAlign=middle;labelPosition=right;align=left;spacingLeft=10;fontColor=#999999;fontSize=11;" vertex="1" parent="1"><mxGeometry x="415" y="225" width="34" height="30" as="geometry"/></mxCell>
        <mxCell id="pubsub-card" value="" style="strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;fillColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="400" y="350" width="160" height="60" as="geometry"/></mxCell>
        <mxCell id="pubsub-icon" value="Log Streaming&#xa;Pub/Sub" style="shape=mxgraph.gcp2.cloud_pubsub;html=1;fillColor=#5184F3;strokeColor=none;verticalLabelPosition=middle;verticalAlign=middle;labelPosition=right;align=left;spacingLeft=10;fontColor=#999999;fontSize=11;" vertex="1" parent="1"><mxGeometry x="415" y="365" width="34" height="30" as="geometry"/></mxCell>
        <mxCell id="dataflow-card" value="" style="strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;fillColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="700" y="280" width="160" height="60" as="geometry"/></mxCell>
        <mxCell id="dataflow-icon" value="Log Processing&#xa;Dataflow" style="shape=mxgraph.gcp2.cloud_dataflow_icon;html=1;fillColor=#5184F3;strokeColor=none;verticalLabelPosition=middle;verticalAlign=middle;labelPosition=right;align=left;spacingLeft=10;fontColor=#999999;fontSize=11;" vertex="1" parent="1"><mxGeometry x="715" y="295" width="21" height="30" as="geometry"/></mxCell>
        <mxCell id="bigquery-card" value="" style="strokeColor=#dddddd;shadow=1;strokeWidth=1;rounded=1;absoluteArcSize=1;arcSize=2;fillColor=#ffffff;" vertex="1" parent="1"><mxGeometry x="900" y="280" width="120" height="60" as="geometry"/></mxCell>
        <mxCell id="bigquery-icon" value="Analytics&#xa;BigQuery" style="shape=mxgraph.gcp2.bigquery;html=1;fillColor=#5184F3;strokeColor=none;verticalLabelPosition=middle;verticalAlign=middle;labelPosition=right;align=left;spacingLeft=10;fontColor=#999999;fontSize=11;" vertex="1" parent="1"><mxGeometry x="910" y="295" width="34" height="30" as="geometry"/></mxCell>
        <mxCell id="conn1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#4284F3;strokeWidth=2;endArrow=blockThin;endFill=1;endSize=4;" edge="1" parent="1" source="k8s-card" target="logging-card"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#4284F3;strokeWidth=2;endArrow=blockThin;endFill=1;endSize=4;" edge="1" parent="1" source="logging-card" target="storage-card"><mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="320" y="340"/>
              <mxPoint x="320" y="240"/>
            </Array>
          </mxGeometry></mxCell>
        <mxCell id="conn3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#9E9E9E;strokeWidth=2;endArrow=blockThin;endFill=1;endSize=4;" edge="1" parent="1" source="logging-card" target="pubsub-card"><mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="320" y="340"/>
              <mxPoint x="320" y="380"/>
            </Array>
          </mxGeometry></mxCell>
        <mxCell id="conn4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#4284F3;strokeWidth=2;endArrow=blockThin;endFill=1;endSize=4;" edge="1" parent="1" source="storage-card" target="dataflow-card"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="conn5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#9E9E9E;strokeWidth=2;endArrow=blockThin;endFill=1;endSize=4;" edge="1" parent="1" source="pubsub-card" target="dataflow-card"><mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="640" y="380"/>
              <mxPoint x="640" y="310"/>
            </Array>
          </mxGeometry></mxCell>
        <mxCell id="conn6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;strokeColor=#4284F3;strokeWidth=2;endArrow=blockThin;endFill=1;endSize=4;" edge="1" parent="1" source="dataflow-card" target="bigquery-card"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Pattern Notes

1. **Service Card Pattern**: GCP diagrams use white cards with shadow containing service icon and label
2. **Container Pattern**: Platform boundary with gray background, dashed groups for logical separation
3. **Connection Pattern**: Blue arrows for primary flow, gray for secondary/streaming paths
4. **Icon Style**: GCP2 stencils use embedded SVG, referenced as `shape=mxgraph.gcp2.<service>`
