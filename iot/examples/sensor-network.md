# Sensor Network

Distributed sensor network with LoRaWAN connectivity, gateway aggregation, and cloud analytics.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Sensor | `mxgraph.aws4.sensor` |
| Temperature Sensor | `mxgraph.aws4.iot_thing_temperature_sensor` |
| Humidity Sensor | `mxgraph.aws4.iot_thing_humidity_sensor` |
| LoRaWAN Protocol | `mxgraph.aws4.iot_lorawan_protocol` |
| IoT Device Gateway | `mxgraph.aws4.iot_device_gateway` |
| IoT Core | `mxgraph.aws4.iot_core` |
| IoT Analytics | `mxgraph.aws4.iot_analytics` |
| Lambda | `mxgraph.aws4.lambda_function` |

## Example

Agricultural sensor mesh with LoRaWAN gateways collecting environmental data:

```plantuml
@startuml
left to right direction

rectangle "Field Zone A" {
  mxgraph.aws4.iot_thing_temperature_sensor "Temp\nSensor" as t1
  mxgraph.aws4.iot_thing_humidity_sensor "Humidity\nSensor" as h1
  mxgraph.aws4.sensor "Soil\nMoisture" as sm1
}

rectangle "Field Zone B" {
  mxgraph.aws4.iot_thing_temperature_sensor "Temp\nSensor" as t2
  mxgraph.aws4.iot_thing_humidity_sensor "Humidity\nSensor" as h2
  mxgraph.aws4.sensor "Soil\nMoisture" as sm2
}

rectangle "Gateway Layer" {
  mxgraph.aws4.iot_lorawan_protocol "LoRaWAN" as lora
  mxgraph.aws4.iot_device_gateway "Device\nGateway" as gw
}

rectangle "Cloud Processing" {
  mxgraph.aws4.iot_core "IoT Core" as core
  mxgraph.aws4.lambda_function "Data\nTransform" as fn
  mxgraph.aws4.iot_analytics "IoT\nAnalytics" as analytics
  mxgraph.aws4.iot_events "Irrigation\nRules" as events
}

t1 --> lora
h1 --> lora
sm1 --> lora
t2 --> lora
h2 --> lora
sm2 --> lora
lora --> gw
gw --> core
core --> fn
fn --> analytics
core --> events
@enduml
```

## Pattern Notes

1. **LoRaWAN**: low-power, long-range wireless ideal for outdoor sensor fields — up to 10km range
2. **Device Gateway**: aggregates LoRaWAN packets and forwards to IoT Core via MQTT
3. **Lambda transform**: normalizes heterogeneous sensor payloads into a common schema
4. **IoT Events rules**: triggers irrigation actuators when soil moisture drops below threshold

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Temp+Humidity | `mxgraph.aws4.iot_thing_temperature_humidity_sensor` | Combined environmental sensor |
| Vibration Sensor | `mxgraph.aws4.iot_thing_vibration_sensor` | Structural or machine vibration |
| Actuator | `mxgraph.aws4.actuator` | Irrigation valves, motors |
| MQTT Protocol | `mxgraph.aws4.mqtt_protocol` | Showing MQTT broker connections |
| IoT Button | `mxgraph.aws4.iot_button` | Manual override triggers |
| S3 | `mxgraph.aws4.s3` | Archiving raw sensor data |
