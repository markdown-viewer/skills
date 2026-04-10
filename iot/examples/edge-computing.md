# Edge Computing

Edge computing architecture with Greengrass components running ML inference and local rules close to devices.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Greengrass | `mxgraph.aws4.greengrass` |
| Nucleus | `mxgraph.aws4.iot_greengrass_component_nucleus` |
| ML Component | `mxgraph.aws4.iot_greengrass_component_machine_learning` |
| Stream Manager | `mxgraph.aws4.iot_greengrass_stream_manager` |
| FreeRTOS Device | `mxgraph.aws4.iot_thing_freertos_device` |
| Sensor | `mxgraph.aws4.sensor` |
| IoT Core | `mxgraph.aws4.iot_core` |
| S3 | `mxgraph.aws4.s3` |

## Example

Edge gateway running ML anomaly detection on sensor data before sending results to cloud:

```plantuml
@startuml
left to right direction

rectangle "Field Devices" {
  mxgraph.aws4.sensor "Pressure\nSensor" as s1
  mxgraph.aws4.sensor "Flow\nSensor" as s2
  mxgraph.aws4.iot_thing_freertos_device "FreeRTOS\nMCU" as mcu
}

rectangle "Edge Gateway" {
  mxgraph.aws4.greengrass "Greengrass" as gg
  mxgraph.aws4.iot_greengrass_component_nucleus "Nucleus" as nucleus
  mxgraph.aws4.iot_greengrass_component_machine_learning "ML\nInference" as ml
  mxgraph.aws4.iot_greengrass_stream_manager "Stream\nManager" as sm
}

rectangle "Cloud" {
  mxgraph.aws4.iot_core "IoT Core" as core
  mxgraph.aws4.s3 "Model\nStore (S3)" as s3
  mxgraph.aws4.iot_analytics "IoT\nAnalytics" as analytics
}

s1 --> gg : MQTT
s2 --> gg : MQTT
mcu --> gg : MQTT
gg --> nucleus
nucleus --> ml : "raw data"
ml --> sm : "anomalies"
sm --> core
core --> analytics
s3 ..> ml : "model update"
@enduml
```

## Pattern Notes

1. **Greengrass Nucleus**: core runtime managing component lifecycle on the edge device
2. **ML at the edge**: inference component runs anomaly detection locally — only anomalies are sent to cloud, reducing bandwidth 90%+
3. **Stream Manager**: buffers and batches outbound data, handles intermittent connectivity
4. **Model update**: S3 stores trained models, Greengrass deployment pushes new versions to edge

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Private Component | `mxgraph.aws4.iot_greengrass_component_private` | Custom business-logic components |
| Public Component | `mxgraph.aws4.iot_greengrass_component_public` | Community/shared edge components |
| Recipe | `mxgraph.aws4.iot_greengrass_recipe` | Component deployment definitions |
| IPC | `mxgraph.aws4.iot_greengrass_interprocess_communication` | Local inter-component messaging |
| OTA Update | `mxgraph.aws4.iot_over_the_air_update` | Firmware updates to edge devices |
| SageMaker | `mxgraph.aws4.sagemaker` | Training ML models in the cloud |
