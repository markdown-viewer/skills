# ML Feature Pipeline

Feature engineering pipeline for machine learning — from raw data to curated feature store.

## Key Elements

| Component | Stencil |
|-----------|---------|
| EMR | `mxgraph.aws4.emr` |
| EMR Engine | `mxgraph.aws4.emr_engine` |
| Glue | `mxgraph.aws4.glue` |
| Glue Data Catalog | `mxgraph.aws4.glue_data_catalog` |
| Athena | `mxgraph.aws4.athena` |
| S3 | `mxgraph.aws4.s3` |
| DynamoDB | `mxgraph.aws4.dynamodb` |
| Lambda | `mxgraph.aws4.lambda_function` |

## Example

Batch and real-time feature computation feeding an online/offline feature store:

```plantuml
@startuml
left to right direction

rectangle "Data Sources" {
  mxgraph.aws4.s3 "Event\nLogs (S3)" as logs
  mxgraph.aws4.rds "User\nDB (RDS)" as rds
  mxgraph.aws4.kinesis_data_streams "Click\nStream" as clicks
}

rectangle "Batch Features" {
  mxgraph.aws4.emr "EMR\nCluster" as emr
  mxgraph.aws4.emr_engine "Spark\nJobs" as spark
  mxgraph.aws4.glue "Glue\nETL" as glue
}

rectangle "Real-time Features" {
  mxgraph.aws4.lambda_function "Feature\nLambda" as fn
}

rectangle "Feature Store" {
  mxgraph.aws4.s3 "Offline Store\n(S3/Parquet)" as offline
  mxgraph.aws4.dynamodb "Online Store\n(DynamoDB)" as online
  mxgraph.aws4.glue_data_catalog "Feature\nCatalog" as catalog
}

logs --> emr
rds --> glue
emr --> spark
spark --> offline
glue --> offline
offline --> catalog
clicks ..> fn
fn --> online
@enduml
```

## Pattern Notes

1. **Dual store**: offline (S3 Parquet) for model training, online (DynamoDB) for low-latency inference
2. **EMR + Spark**: heavy feature computation (aggregations, joins across billions of rows) on batch schedule
3. **Real-time features**: Lambda computes sliding-window features from Kinesis and writes to DynamoDB
4. **Feature Catalog**: Glue Data Catalog tracks feature schemas, versions, and lineage

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| SageMaker | `mxgraph.aws4.sagemaker` | Model training & deployment |
| SageMaker Model | `mxgraph.aws4.sagemaker_model` | Trained model artifact |
| Step Functions | `mxgraph.aws4.step_functions` | Orchestrating feature pipelines |
| Athena | `mxgraph.aws4.athena` | Ad-hoc feature validation SQL |
| Redshift | `mxgraph.aws4.redshift` | Warehouse-based feature source |
| Glue DataBrew | `mxgraph.aws4.glue_databrew` | Visual feature transformation |
