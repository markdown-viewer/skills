# Real-time Streaming

Real-time event stream processing with Kinesis ingestion, Lambda transformation, and OpenSearch visualization.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Kinesis Data Streams | `mxgraph.aws4.kinesis_data_streams` |
| Kinesis Data Analytics | `mxgraph.aws4.kinesis_data_analytics` |
| Kinesis Data Firehose | `mxgraph.aws4.kinesis_data_firehose` |
| Lambda | `mxgraph.aws4.lambda_function` |
| OpenSearch | `mxgraph.aws4.opensearch_service_data_node` |
| S3 | `mxgraph.aws4.s3` |
| DynamoDB | `mxgraph.aws4.dynamodb` |

## Example

Clickstream analytics with real-time aggregation and search indexing:

```plantuml
@startuml
left to right direction

rectangle "Event Sources" {
  mxgraph.aws4.users "Web\nClients" as web
  mxgraph.aws4.users "Mobile\nClients" as mobile
}

rectangle "Ingestion" {
  mxgraph.aws4.kinesis_data_streams "Kinesis\nData Streams" as kds
}

rectangle "Processing" {
  mxgraph.aws4.kinesis_data_analytics "Kinesis\nAnalytics" as kda
  mxgraph.aws4.lambda_function "Enrichment\nLambda" as fn
}

rectangle "Storage & Search" {
  mxgraph.aws4.dynamodb "Real-time\nAggregates" as ddb
  mxgraph.aws4.opensearch_service_data_node "OpenSearch" as os
  mxgraph.aws4.s3 "Archive\n(S3)" as s3
}

web ..> kds : events
mobile ..> kds : events
kds --> kda : "windowed agg"
kds --> fn : "enrich"
kda --> ddb
fn --> os
kds --> s3 : archive
@enduml
```

## Pattern Notes

1. **Kinesis fan-out**: single stream feeds multiple consumers — analytics, enrichment, and archival in parallel
2. **Kinesis Analytics**: SQL-based windowed aggregations (e.g., clicks per minute per page) in real-time
3. **Lambda enrichment**: adds geo-IP lookup, user profile join before indexing to OpenSearch
4. **Dashed arrows**: `..>` for async event flows from clients to Kinesis

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Firehose | `mxgraph.aws4.kinesis_data_firehose` | Delivery stream to S3/Redshift |
| Kinesis Video | `mxgraph.aws4.kinesis_video_streams` | Video/media stream processing |
| MSK Connect | `mxgraph.aws4.msk_amazon_msk_connect` | Kafka connector integration |
| EventBridge | `mxgraph.aws4.eventbridge` | Event-driven routing/filtering |
| Timestream | `mxgraph.aws4.timestream` | Time-series database for IoT |
| MSK | `mxgraph.aws4.managed_streaming_for_kafka` | Self-managed Kafka alternative |
