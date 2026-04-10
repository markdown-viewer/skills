# Digital Twin

Digital twin architecture using IoT TwinMaker and SiteWise for modeling and visualizing physical assets.

## Key Elements

| Component | Stencil |
|-----------|---------|
| TwinMaker | `mxgraph.aws4.iot_twinmaker` |
| SiteWise | `mxgraph.aws4.iot_sitewise` |
| SiteWise Asset | `mxgraph.aws4.iot_sitewise_asset` |
| SiteWise Asset Model | `mxgraph.aws4.iot_sitewise_asset_model` |
| SiteWise Data Streams | `mxgraph.aws4.iot_sitewise_data_streams` |
| Greengrass | `mxgraph.aws4.greengrass` |
| S3 | `mxgraph.aws4.s3` |

## Example

Building digital twin with asset hierarchy, real-time telemetry, and 3D visualization:

```plantuml
@startuml
left to right direction

rectangle "Physical Assets" {
  mxgraph.aws4.factory "Factory\nBuilding" as bldg
  mxgraph.aws4.iot_thing_plc "HVAC\nController" as hvac
  mxgraph.aws4.sensor "Energy\nMeter" as meter
}

rectangle "Edge" {
  mxgraph.aws4.greengrass "Greengrass\nGateway" as gg
}

rectangle "Asset Modeling" {
  mxgraph.aws4.iot_sitewise "SiteWise" as sw
  mxgraph.aws4.iot_sitewise_asset_model "Asset\nModel" as model
  mxgraph.aws4.iot_sitewise_asset "Asset\nInstances" as assets
  mxgraph.aws4.iot_sitewise_data_streams "Data\nStreams" as streams
}

rectangle "Visualization" {
  mxgraph.aws4.iot_twinmaker "TwinMaker" as twin
  mxgraph.aws4.s3 "3D Models\n(S3)" as s3
}

bldg --> gg
hvac --> gg : OPC-UA
meter --> gg : Modbus
gg --> sw
sw --> model
model --> assets
sw --> streams
streams --> twin
s3 --> twin : "3D scenes"
@enduml
```

## Pattern Notes

1. **SiteWise asset hierarchy**: Model → Asset instances mirrors physical hierarchy (Building → Floor → Room → Equipment)
2. **Protocol bridging**: Greengrass converts OPC-UA and Modbus to SiteWise ingest format
3. **TwinMaker scenes**: combines real-time data streams with 3D models stored in S3 for immersive visualization
4. **Modeling first**: define asset models (properties, metrics, transforms) before creating asset instances

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Asset Hierarchy | `mxgraph.aws4.iot_sitewise_asset_hierarchy` | Showing parent-child asset trees |
| Asset Properties | `mxgraph.aws4.iot_sitewise_asset_properties` | Displaying measurement attributes |
| Grafana | `mxgraph.aws4.managed_service_for_grafana` | Adding operational dashboards |
| Timestream | `mxgraph.aws4.timestream` | Time-series data storage |
| IoT Analytics | `mxgraph.aws4.iot_analytics` | Historical data processing pipeline |
| QuickSight | `mxgraph.aws4.quicksight` | Business intelligence reports |
