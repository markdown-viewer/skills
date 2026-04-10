# CDC Pipeline

Change Data Capture pipeline streaming database changes to analytics warehouse in near real-time.

## Key Elements

| Component | Stencil |
|-----------|---------|
| DynamoDB | `mxgraph.aws4.dynamodb` |
| DynamoDB Stream | `mxgraph.aws4.dynamodb_stream` |
| Aurora | `mxgraph.aws4.aurora` |
| Kinesis Data Streams | `mxgraph.aws4.kinesis_data_streams` |
| Lambda | `mxgraph.aws4.lambda_function` |
| S3 | `mxgraph.aws4.s3` |
| Redshift | `mxgraph.aws4.redshift` |

## Example

DynamoDB and Aurora changes captured and replicated to Redshift for analytics:

```plantuml
@startuml
left to right direction

rectangle "Transactional Databases" {
  mxgraph.aws4.dynamodb "Orders\n(DynamoDB)" as ddb
  mxgraph.aws4.aurora "Users\n(Aurora)" as aurora
}

rectangle "Change Capture" {
  mxgraph.aws4.dynamodb_stream "DynamoDB\nStream" as ddbstream
  mxgraph.aws4.kinesis_data_streams "Kinesis\n(Aurora CDC)" as kds
}

rectangle "Transform" {
  mxgraph.aws4.lambda_function "CDC\nProcessor" as fn1
  mxgraph.aws4.lambda_function "Schema\nMapper" as fn2
}

rectangle "Analytics" {
  mxgraph.aws4.s3 "Staging\n(S3)" as s3
  mxgraph.aws4.redshift "Redshift\nWarehouse" as rs
}

ddb ..> ddbstream
aurora ..> kds : "binlog CDC"
ddbstream --> fn1
kds --> fn2
fn1 --> s3
fn2 --> s3
s3 --> rs : "COPY"
@enduml
```

## Pattern Notes

1. **DynamoDB Streams**: captures INSERT/UPDATE/DELETE with 24h retention — Lambda polls for new changes
2. **Aurora CDC**: binlog-based change capture streamed to Kinesis for decoupled processing
3. **Dashed arrows**: `..>` for async CDC events from source databases to streams
4. **S3 staging**: intermediate Parquet files enable idempotent Redshift COPY and replay on failure

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| DMS | `mxgraph.aws4.database_migration_service` | Ongoing replication from source DBs |
| AppFlow | `mxgraph.aws4.appflow` | SaaS-to-lake CDC integration |
| EventBridge | `mxgraph.aws4.eventbridge` | Change event fanout routing |
| Firehose | `mxgraph.aws4.kinesis_data_firehose` | Buffered delivery to S3/Redshift |
| Glue | `mxgraph.aws4.glue` | Schema evolution handling |
| MSK Connect | `mxgraph.aws4.msk_amazon_msk_connect` | Debezium CDC connectors |
