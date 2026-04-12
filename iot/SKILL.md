---
name: iot
description: Create IoT architecture diagrams using PlantUML syntax with device/sensor stencil icons. Best for smart home, industrial IoT (IIoT), fleet management, edge computing, and sensor network diagrams. NOT for general cloud infra (use cloud skill) or general software modeling (use uml).
metadata:
  author: IoT diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# IoT Architecture Diagram Generator

**Quick Start:** Select device/sensor icons → Place edge gateways → Connect to cloud services → Group into zones → Wrap in ` ```plantuml ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use `left to right direction` for typical IoT data flows (Device → Edge → Cloud)
- Use `mxgraph.aws4.*` stencil syntax for IoT service and device icons
- Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`
- Use `rectangle "Zone"  { ... }` or `package "Site" { ... }` for grouping
- Directed flows use `-->`, async/event-driven flows use `..>` (dashed)

**Full stencil reference:** See [stencils/README.md](../uml/stencils/README.md) for 9500+ available icons.

## Mxgraph Stencil Syntax

```
mxgraph.aws4.<icon> "Label" as <alias>
```

### Core IoT Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| IoT Platform | `iot_core`, `internet_of_things`, `iot_1click` | Central IoT hub / message broker |
| Edge/Gateway | `greengrass`, `iot_device_gateway`, `freertos`, `iot_expresslink` | Edge computing & device gateway |
| Greengrass | `iot_greengrass_component`, `iot_greengrass_nucleus`, `iot_greengrass_stream_manager` | Edge runtime components |
| Device Mgmt | `iot_device_management`, `iot_device_defender`, `iot_device_tester`, `iot_over_the_air_update` | Fleet provisioning, security, OTA |
| Analytics | `iot_analytics`, `iot_analytics_channel`, `iot_analytics_pipeline`, `iot_analytics_dataset`, `iot_analytics_data_store` | IoT data processing pipeline |
| Events/Rules | `iot_events`, `iot_device_defender_iot_device_jobs` | Event detection & job execution |
| Digital Twin | `iot_twinmaker`, `iot_sitewise`, `iot_sitewise_asset`, `iot_sitewise_asset_model` | Asset modeling & visualization |
| Fleet | `iot_fleetwise`, `iot_device_management_fleet` | Vehicle & device fleet telemetry |

### Device & Sensor Stencils

| Category | Stencils |
|----------|----------|
| Sensors | `sensor`, `iot_thing_temperature_sensor`, `iot_thing_humidity_sensor`, `iot_thing_vibration_sensor`, `iot_thing_temperature_humidity_sensor`, `iot_thing_temperature_vibration_sensor` |
| Actuators | `actuator`, `iot_thing_relay`, `iot_thing_stacklight` |
| Industrial | `factory`, `iot_thing_industrial_pc`, `iot_thing_plc` |
| Smart Home | `thermostat`, `alexa_enabled_device`, `alexa_smart_home_skill`, `camera`, `camera2` |
| Protocols | `mqtt_protocol`, `iot_lorawan_protocol`, `iot_greengrass_protocol` |
| Boats/Vehicles | `iot_sailboat`, `iot_fleetwise` |
| Robotics | `robomaker`, `iot_roborunner` |

### Connection Types

| Syntax | Meaning | Use Case |
|--------|---------|----------|
| `A --> B` | Solid arrow | Sync API / data flow |
| `A ..> B` | Dashed arrow | Async telemetry / MQTT publish |
| `A -- B` | Solid line | Physical / bidirectional link |
| `A --> B : "label"` | Labeled connection | Describe protocol or data |

### Quick Example

```plantuml
@startuml
left to right direction
rectangle "Factory Floor" {
  mxgraph.aws4.sensor "Temp\nSensor" as s1
  mxgraph.aws4.iot_thing_plc "PLC" as plc
}
mxgraph.aws4.greengrass "Greengrass\nEdge" as gg
mxgraph.aws4.iot_core "IoT Core" as core
mxgraph.aws4.iot_analytics "IoT\nAnalytics" as analytics

s1 --> gg : MQTT
plc --> gg
gg --> core
core --> analytics
@enduml
```

## IoT Architecture Types

| Type | Purpose | Key Stencils | Example |
|------|---------|--------------|---------|
| Smart Factory | Industrial IoT monitoring | `sensor`, `iot_thing_plc`, `greengrass`, `iot_sitewise` | [smart-factory.md](examples/smart-factory.md) |
| Smart Home | Home automation | `thermostat`, `alexa_enabled_device`, `camera`, `iot_core` | [smart-home.md](examples/smart-home.md) |
| Fleet Telemetry | Vehicle fleet tracking | `iot_fleetwise`, `iot_core`, `iot_analytics` | [fleet-telemetry.md](examples/fleet-telemetry.md) |
| Edge Computing | Local processing at edge | `greengrass`, `freertos`, `iot_greengrass_component` | [edge-computing.md](examples/edge-computing.md) |
| Digital Twin | Asset modeling & simulation | `iot_twinmaker`, `iot_sitewise_asset_model`, `iot_sitewise` | [digital-twin.md](examples/digital-twin.md) |
| Sensor Network | Distributed sensor mesh | `sensor`, `iot_lorawan_protocol`, `iot_device_gateway` | [sensor-network.md](examples/sensor-network.md) |
| Device Management | Fleet provisioning & OTA | `iot_device_management`, `iot_device_defender`, `iot_over_the_air_update` | [device-management.md](examples/device-management.md) |
| Robotics | Robot fleet orchestration | `robomaker`, `iot_roborunner`, `greengrass` | [robotics.md](examples/robotics.md) |
