# GCP Log Processing Pipeline

Log processing architecture with batch and streaming paths using Kubernetes Engine, Pub/Sub, Dataflow, and BigQuery.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Kubernetes Engine | `mxgraph.gcp2.container_engine` |
| Logging | `mxgraph.gcp2.logging` |
| Cloud Storage | `mxgraph.gcp2.cloud_storage` |
| Pub/Sub | `mxgraph.gcp2.cloud_pubsub` |
| Dataflow | `mxgraph.gcp2.cloud_dataflow` |
| BigQuery | `mxgraph.gcp2.bigquery` |

## Example

```plantuml
@startuml
left to right direction

rectangle "Google Cloud Platform" {
  mxgraph.gcp2.container_engine "Microservices\nKubernetes Engine" as ke
  mxgraph.gcp2.logging "Log Collection\nLogging" as logging

  rectangle "Batch" {
    mxgraph.gcp2.cloud_storage "Log Storage\nCloud Storage" as cs
  }

  rectangle "Streaming" {
    mxgraph.gcp2.cloud_pubsub "Log Streaming\nPub/Sub" as pubsub
  }

  mxgraph.gcp2.cloud_dataflow "Log Processing\nDataflow" as df
  mxgraph.gcp2.bigquery "Log Analytics\nBigQuery" as bq
}

ke --> logging
logging --> cs : batch
logging --> pubsub : streaming
cs --> df
pubsub --> df
df --> bq
@enduml
```

## Pattern Notes

1. **Platform container**: Use `rectangle "Google Cloud Platform"` to group all GCP services
2. **Batch vs Streaming**: Separate paths grouped in nested rectangles, both converge at Dataflow
3. **Stencil naming**: All GCP stencils use `mxgraph.gcp2.<service_name>` prefix
4. **Two-line labels**: Role in first line, service name in second (e.g. `"Log Collection\nLogging"`)

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Cloud Monitoring | `mxgraph.gcp2.cloud_monitoring` | Metrics and alerting |
| Cloud Functions | `mxgraph.gcp2.cloud_functions` | Serverless processing |
| Cloud Composer | `mxgraph.gcp2.cloud_composer` | Workflow orchestration |
| Cloud IAM | `mxgraph.gcp2.cloud_iam` | Access control |
| Data Studio | `mxgraph.gcp2.data_studio` | BI dashboards |
| Error Reporting | `mxgraph.gcp2.error_reporting` | Error tracking |
 