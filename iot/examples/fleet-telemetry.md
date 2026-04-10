# Fleet Telemetry

Connected vehicle fleet architecture with real-time telemetry collection, edge processing, and cloud analytics.

## Key Elements

| Component | Stencil |
|-----------|---------|
| FleetWise | `mxgraph.aws4.iot_fleetwise` |
| IoT Core | `mxgraph.aws4.iot_core` |
| Greengrass | `mxgraph.aws4.greengrass` |
| Kinesis | `mxgraph.aws4.kinesis_data_streams` |
| S3 | `mxgraph.aws4.s3` |
| IoT Analytics | `mxgraph.aws4.iot_analytics` |
| QuickSight | `mxgraph.aws4.quicksight` |

## Example

Vehicle fleet sending telemetry via FleetWise to a cloud analytics pipeline:

```plantuml
@startuml
left to right direction

rectangle "Vehicle Fleet" {
  rectangle "Vehicle A" {
    mxgraph.aws4.sensor "OBD-II\nSensor" as obd1
    mxgraph.aws4.greengrass "Edge\nAgent" as gg1
  }
  rectangle "Vehicle B" {
    mxgraph.aws4.sensor "OBD-II\nSensor" as obd2
    mxgraph.aws4.greengrass "Edge\nAgent" as gg2
  }
}

rectangle "Telemetry Ingestion" {
  mxgraph.aws4.iot_fleetwise "FleetWise" as fw
  mxgraph.aws4.iot_core "IoT Core" as core
}

rectangle "Analytics Pipeline" {
  mxgraph.aws4.kinesis_data_streams "Kinesis" as kin
  mxgraph.aws4.s3 "Data Lake\n(S3)" as s3
  mxgraph.aws4.iot_analytics "IoT\nAnalytics" as analytics
  mxgraph.aws4.quicksight "QuickSight\nDashboard" as qs
}

obd1 --> gg1
obd2 --> gg2
gg1 --> fw : telemetry
gg2 --> fw : telemetry
fw --> core
core --> kin
kin --> s3
kin --> analytics
analytics --> qs
@enduml
```

## Pattern Notes

1. **FleetWise**: collects vehicle signals (CAN bus, OBD-II) and sends only relevant data to cloud
2. **Edge agent**: Greengrass on each vehicle pre-filters and compresses telemetry locally
3. **Kinesis fan-out**: stream data goes both to S3 (archival) and IoT Analytics (real-time)
4. **QuickSight**: fleet dashboards for fuel efficiency, driver behavior, predictive maintenance

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Car | `mxgraph.aws4.car` | Representing individual vehicles |
| Location Service | `mxgraph.aws4.location_service` | GPS tracking and geofencing |
| Location Track | `mxgraph.aws4.location_service_track` | Vehicle route tracking |
| Timestream | `mxgraph.aws4.timestream` | Time-series DB for telemetry storage |
| IoT Events | `mxgraph.aws4.iot_events` | Triggering alerts on anomalous readings |
| SiteWise | `mxgraph.aws4.iot_sitewise` | Modeling fleet asset hierarchy |
