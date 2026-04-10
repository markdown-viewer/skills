# Robotics

Robot fleet orchestration with RoboMaker simulation, Greengrass edge runtime, and cloud coordination.

## Key Elements

| Component | Stencil |
|-----------|---------|
| RoboMaker | `mxgraph.aws4.robomaker` |
| RoboRunner | `mxgraph.aws4.iot_roborunner` |
| Greengrass | `mxgraph.aws4.greengrass` |
| ML Component | `mxgraph.aws4.iot_greengrass_component_machine_learning` |
| IoT Core | `mxgraph.aws4.iot_core` |
| Camera | `mxgraph.aws4.camera` |
| S3 | `mxgraph.aws4.s3` |

## Example

Warehouse robot fleet with simulation, edge ML, and centralized coordination:

```plantuml
@startuml
left to right direction

rectangle "Warehouse Floor" {
  rectangle "Robot A" {
    mxgraph.aws4.camera "Vision\nCamera" as cam1
    mxgraph.aws4.greengrass "Greengrass\nRuntime" as gg1
    mxgraph.aws4.iot_greengrass_component_machine_learning "Navigation\nML" as ml1
  }
  rectangle "Robot B" {
    mxgraph.aws4.camera "Vision\nCamera" as cam2
    mxgraph.aws4.greengrass "Greengrass\nRuntime" as gg2
    mxgraph.aws4.iot_greengrass_component_machine_learning "Navigation\nML" as ml2
  }
}

rectangle "Cloud Orchestration" {
  mxgraph.aws4.iot_core "IoT Core" as core
  mxgraph.aws4.iot_roborunner "RoboRunner\nOrchestrator" as runner
  mxgraph.aws4.robomaker "RoboMaker\nSimulation" as sim
  mxgraph.aws4.s3 "ML Models\n(S3)" as s3
}

cam1 --> gg1
gg1 --> ml1
cam2 --> gg2
gg2 --> ml2
gg1 --> core : status
gg2 --> core : status
core --> runner
runner --> sim : "test scenarios"
s3 ..> gg1 : "model deploy"
s3 ..> gg2 : "model deploy"
@enduml
```

## Pattern Notes

1. **Edge ML per robot**: each robot runs Greengrass with local navigation ML — no cloud latency for real-time decisions
2. **RoboRunner**: centralized task orchestration across heterogeneous robot fleets, manages task assignment and routing
3. **RoboMaker simulation**: test new navigation algorithms in virtual warehouse before deploying to physical robots
4. **Model deployment**: trained models stored in S3, pushed to robot fleet via Greengrass deployment

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Kinesis Video | `mxgraph.aws4.kinesis_video_streams` | Streaming robot camera feeds |
| Rekognition | `mxgraph.aws4.rekognition` | Visual object/defect detection |
| SageMaker | `mxgraph.aws4.sagemaker` | Training navigation models |
| IoT FleetWise | `mxgraph.aws4.iot_fleetwise` | Multi-robot fleet telemetry |
| Device Mgmt | `mxgraph.aws4.iot_device_management` | Robot provisioning & grouping |
| Industrial PC | `mxgraph.aws4.iot_thing_industrial_pc` | On-robot compute hardware |
