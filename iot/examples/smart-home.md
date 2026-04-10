# Smart Home

Home automation architecture with Alexa voice control, smart devices, and cloud integration.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Alexa Device | `mxgraph.aws4.alexa_enabled_device` |
| Alexa Skill | `mxgraph.aws4.alexa_smart_home_skill` |
| Thermostat | `mxgraph.aws4.thermostat` |
| Camera | `mxgraph.aws4.camera` |
| Sensor | `mxgraph.aws4.sensor` |
| Actuator | `mxgraph.aws4.actuator` |
| IoT Core | `mxgraph.aws4.iot_core` |
| Lambda | `mxgraph.aws4.lambda_function` |

## Example

Smart home with voice control, security cameras, and climate automation:

```plantuml
@startuml
left to right direction

rectangle "Living Room" {
  mxgraph.aws4.alexa_enabled_device "Echo\nDevice" as echo
  mxgraph.aws4.thermostat "Smart\nThermostat" as therm
  mxgraph.aws4.sensor "Motion\nSensor" as motion
}

rectangle "Entry" {
  mxgraph.aws4.camera "Doorbell\nCam" as cam
  mxgraph.aws4.actuator "Smart\nLock" as lock
}

rectangle "Cloud Services" {
  mxgraph.aws4.alexa_smart_home_skill "Alexa\nSkill" as skill
  mxgraph.aws4.lambda_function "Lambda" as fn
  mxgraph.aws4.iot_core "IoT Core" as core
  mxgraph.aws4.iot_events "IoT\nEvents" as events
  mxgraph.aws4.dynamodb "DynamoDB" as db
}

echo --> skill : "voice cmd"
skill --> fn
fn --> core
therm --> core : MQTT
motion --> core : MQTT
cam --> core : MQTT
lock --> core : MQTT
core --> events
events --> fn : "trigger rules"
fn --> db : "log state"
@enduml
```

## Pattern Notes

1. **Voice-first**: Alexa Echo triggers smart home skill → Lambda → IoT Core for device control
2. **Bidirectional MQTT**: Devices both publish state and subscribe to commands via IoT Core
3. **Event rules**: IoT Events detects patterns (motion + time of day) and triggers automations
4. **State logging**: DynamoDB stores device state history for dashboards and analytics

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Door Lock | `mxgraph.aws4.door_lock` | Adding smart lock control |
| Echo | `mxgraph.aws4.echo` | Showing specific Echo hardware |
| Alexa Voice Service | `mxgraph.aws4.alexa_voice_service` | Custom voice assistant integration |
| IoT 1-Click | `mxgraph.aws4.iot_1click` | One-press button triggers (e.g. doorbell) |
| Kinesis Video | `mxgraph.aws4.kinesis_video_streams` | Streaming camera feeds to cloud |
| SNS | `mxgraph.aws4.sns` | Push notifications to homeowner mobile |
