# Device Management

IoT device lifecycle management with provisioning, security monitoring, OTA updates, and fleet operations.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Device Management | `mxgraph.aws4.iot_device_management` |
| Device Fleet | `mxgraph.aws4.iot_device_management_fleet` |
| Device Defender | `mxgraph.aws4.iot_device_defender` |
| Device Tester | `mxgraph.aws4.iot_device_tester` |
| OTA Update | `mxgraph.aws4.iot_over_the_air_update` |
| Device Jobs | `mxgraph.aws4.iot_device_defender_iot_device_jobs` |
| IoT Core | `mxgraph.aws4.iot_core` |
| S3 | `mxgraph.aws4.s3` |

## Example

Device fleet lifecycle — from provisioning through monitoring to firmware updates:

```plantuml
@startuml
left to right direction

rectangle "Device Fleet" {
  mxgraph.aws4.iot_device_management_fleet "Fleet\n(10K devices)" as fleet
  mxgraph.aws4.iot_thing_freertos_device "FreeRTOS\nDevice" as dev1
  mxgraph.aws4.iot_thing_freertos_device "FreeRTOS\nDevice" as dev2
}

rectangle "Provisioning & Testing" {
  mxgraph.aws4.iot_device_management "Device\nManagement" as mgmt
  mxgraph.aws4.iot_device_tester "Device\nTester" as tester
}

rectangle "Security & Monitoring" {
  mxgraph.aws4.iot_core "IoT Core" as core
  mxgraph.aws4.iot_device_defender "Device\nDefender" as defender
}

rectangle "Update Pipeline" {
  mxgraph.aws4.s3 "Firmware\nBucket (S3)" as s3
  mxgraph.aws4.iot_over_the_air_update "OTA\nUpdate" as ota
  mxgraph.aws4.iot_device_defender_iot_device_jobs "Device\nJobs" as jobs
}

tester --> mgmt : "validate"
mgmt --> fleet : "provision"
dev1 --> core : telemetry
dev2 --> core : telemetry
core --> defender : "audit"
s3 --> ota : "firmware"
ota --> jobs
jobs ..> fleet : "rolling update"
@enduml
```

## Pattern Notes

1. **Provisioning flow**: Device Tester validates → Device Management provisions credentials → devices join fleet
2. **Device Defender**: continuously audits device behavior, detects anomalous MQTT patterns or policy violations
3. **OTA updates**: firmware stored in S3, rolled out via Device Jobs with configurable rollout rate and rollback
4. **Fleet groups**: devices organized into dynamic groups for targeted updates and monitoring

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Device Jobs | `mxgraph.aws4.iot_device_jobs_resource` | Showing individual job executions |
| Device Advisor | `mxgraph.aws4.iot_core_device_advisor` | Pre-production device testing |
| FreeRTOS | `mxgraph.aws4.freertos` | Edge OS platform icon |
| IoT EduKit | `mxgraph.aws4.iot_edukit` | Development & prototyping boards |
| ExpressLink | `mxgraph.aws4.iot_expresslink` | Simplified connectivity modules |
| CloudWatch | `mxgraph.aws4.cloudwatch` | Fleet health monitoring dashboard |
