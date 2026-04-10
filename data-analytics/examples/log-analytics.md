# Log Analytics

Centralized log analytics with Kinesis Firehose ingestion, OpenSearch indexing, and alerting.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Kinesis Data Firehose | `mxgraph.aws4.kinesis_data_firehose` |
| Lambda | `mxgraph.aws4.lambda_function` |
| OpenSearch | `mxgraph.aws4.opensearch_service_data_node` |
| OpenSearch Ingestion | `mxgraph.aws4.opensearch_ingestion` |
| S3 | `mxgraph.aws4.s3` |
| CloudTrail | `mxgraph.aws4.cloudtrail` |
| EC2 | `mxgraph.aws4.ec2` |

## Example

Application and audit logs → Firehose → OpenSearch for search, dashboards, and alerting:

```plantuml
@startuml
left to right direction

rectangle "Log Sources" {
  mxgraph.aws4.ec2 "App\nServers" as apps
  mxgraph.aws4.lambda_function "Lambda\nFunctions" as fns
  mxgraph.aws4.cloudtrail "CloudTrail\nAudit" as trail
}

rectangle "Ingestion" {
  mxgraph.aws4.kinesis_data_firehose "Firehose" as fh
  mxgraph.aws4.lambda_function "Transform\nLambda" as transform
}

rectangle "Search & Analytics" {
  mxgraph.aws4.opensearch_service_data_node "OpenSearch\nCluster" as os
  mxgraph.aws4.opensearch_ingestion "Ingestion\nPipeline" as ingest
}

rectangle "Storage & Alerts" {
  mxgraph.aws4.s3 "Log Archive\n(S3)" as s3
}

apps ..> fh : "app logs"
fns ..> fh : "function logs"
trail ..> fh : "audit events"
fh --> transform : "enrich"
transform --> ingest
ingest --> os
fh --> s3 : "archive"
@enduml
```

## Pattern Notes

1. **Firehose buffering**: batches log events (1-5 min window) before delivery — reduces OpenSearch write pressure
2. **Lambda transform**: parses unstructured logs, adds fields (request-id, environment), normalizes timestamps
3. **Dual destination**: Firehose delivers to both OpenSearch (hot) and S3 (cold archive) simultaneously
4. **OpenSearch dashboards**: Kibana-compatible UI for log search, alerting rules, and operational dashboards

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| CloudWatch | `mxgraph.aws4.cloudwatch` | Metrics collection & alarms |
| CloudWatch Logs | `mxgraph.aws4.cloudwatch_logs` | Native log group ingestion |
| OS Dashboards | `mxgraph.aws4.opensearch_dashboards` | Visualization layer callout |
| OS Index | `mxgraph.aws4.opensearch_service_index` | Index lifecycle management |
| SNS | `mxgraph.aws4.sns` | Alert notifications |
| EventBridge | `mxgraph.aws4.eventbridge` | Log event routing rules |
