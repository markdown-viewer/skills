# Smart Factory

Industrial IoT architecture with sensors, PLCs, edge gateway, and cloud analytics for manufacturing line monitoring.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Temperature Sensor | `mxgraph.aws4.iot_thing_temperature_sensor` |
| Vibration Sensor | `mxgraph.aws4.iot_thing_vibration_sensor` |
| PLC | `mxgraph.aws4.iot_thing_plc` |
| Industrial PC | `mxgraph.aws4.iot_thing_industrial_pc` |
| Greengrass Edge | `mxgraph.aws4.greengrass` |
| IoT Core | `mxgraph.aws4.iot_core` |
| IoT SiteWise | `mxgraph.aws4.iot_sitewise` |
| IoT Analytics | `mxgraph.aws4.iot_analytics` |
| IoT Events | `mxgraph.aws4.iot_events` |

## Example

Manufacturing line with edge processing and cloud-based OEE monitoring:

```plantuml
@startuml
left to right direction

rectangle "Production Line A" {
  mxgraph.aws4.iot_thing_temperature_sensor "Temp\nSensor" as ts1
  mxgraph.aws4.iot_thing_vibration_sensor "Vibration\nSensor" as vs1
  mxgraph.aws4.iot_thing_plc "PLC" as plc1
}

rectangle "Production Line B" {
  mxgraph.aws4.iot_thing_temperature_sensor "Temp\nSensor" as ts2
  mxgraph.aws4.iot_thing_industrial_pc "Industrial\nPC" as ipc
}

rectangle "Edge Layer" {
  mxgraph.aws4.greengrass "Greengrass\nEdge" as gg
  mxgraph.aws4.iot_greengrass_stream_manager "Stream\nManager" as sm
}

rectangle "Cloud Platform" {
  mxgraph.aws4.iot_core "IoT Core" as core
  mxgraph.aws4.iot_sitewise "SiteWise" as sw
  mxgraph.aws4.iot_analytics "IoT\nAnalytics" as analytics
  mxgraph.aws4.iot_events "IoT\nEvents" as events
}

ts1 --> gg : MQTT
vs1 --> gg : MQTT
plc1 --> gg : OPC-UA
ts2 --> gg
ipc --> gg
gg --> sm
sm --> core
core --> sw
core --> analytics
core --> events
@enduml
```

## Pattern Notes

1. **Edge layer**: Greengrass runs ML inference and local rules at the factory, reducing cloud round-trips
2. **Protocol diversity**: Sensors use MQTT, PLCs use OPC-UA — Greengrass bridges both
3. **SiteWise**: models physical assets and hierarchies for operational dashboards
4. **IoT Events**: triggers alarms when sensor readings exceed thresholds

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Stacklight | `mxgraph.aws4.iot_thing_stacklight` | Adding visual alarm indicators on the line |
| Relay | `mxgraph.aws4.iot_thing_relay` | Controlling actuators from edge rules |
| Monitron | `mxgraph.aws4.monitron` | Predictive maintenance vibration monitoring |
| TwinMaker | `mxgraph.aws4.iot_twinmaker` | Adding 3D digital twin visualization |
| CloudWatch | `mxgraph.aws4.cloudwatch` | Operational metrics & dashboards |
| Device Defender | `mxgraph.aws4.iot_device_defender` | Auditing device security posture |
