# Data Lake

Governed data lake with Lake Formation access control, Glue catalog, and multi-engine query access.

## Key Elements

| Component | Stencil |
|-----------|---------|
| S3 | `mxgraph.aws4.s3` |
| Lake Formation | `mxgraph.aws4.lake_formation` |
| Glue | `mxgraph.aws4.glue` |
| Glue Crawlers | `mxgraph.aws4.glue_crawlers` |
| Glue Data Catalog | `mxgraph.aws4.glue_data_catalog` |
| Athena | `mxgraph.aws4.athena` |
| Redshift | `mxgraph.aws4.redshift` |
| QuickSight | `mxgraph.aws4.quicksight` |

## Example

Multi-source data lake with governance, catalog, and query engines:

```plantuml
@startuml
left to right direction

rectangle "Data Sources" {
  mxgraph.aws4.rds "App DB\n(RDS)" as rds
  mxgraph.aws4.dynamodb "User Events\n(DynamoDB)" as ddb
  mxgraph.aws4.s3 "Log Files\n(S3)" as logs
}

rectangle "Ingestion" {
  mxgraph.aws4.glue "Glue\nETL Jobs" as glue
  mxgraph.aws4.glue_crawlers "Glue\nCrawlers" as crawlers
}

rectangle "Data Lake" {
  mxgraph.aws4.lake_formation "Lake\nFormation" as lf
  mxgraph.aws4.s3 "Data Lake\n(S3)" as lake
  mxgraph.aws4.glue_data_catalog "Data\nCatalog" as catalog
}

rectangle "Query & Analytics" {
  mxgraph.aws4.athena "Athena" as athena
  mxgraph.aws4.redshift "Redshift\nSpectrum" as rs
  mxgraph.aws4.quicksight "QuickSight" as qs
}

rds --> glue
ddb --> glue
logs --> glue
glue --> lake
crawlers --> catalog
lake --> lf : "govern"
lf --> athena
lf --> rs
athena --> qs
rs --> qs
@enduml
```

## Pattern Notes

1. **Lake Formation**: centralized permissions — grant table/column-level access across Athena, Redshift, EMR
2. **Glue Crawlers**: auto-discover schemas from S3 data, populate the Data Catalog
3. **Dual query engines**: Athena for ad-hoc SQL, Redshift Spectrum for complex joins with warehouse data
4. **S3 partitioning**: organize by `year/month/day` for Athena partition pruning

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| EMR | `mxgraph.aws4.emr` | Spark/Hive processing on lake data |
| Firehose | `mxgraph.aws4.kinesis_data_firehose` | Streaming ingestion into lake |
| DataZone | `mxgraph.aws4.datazone` | Data governance & catalog portal |
| Data Exchange | `mxgraph.aws4.data_exchange` | Third-party data subscriptions |
| Glacier | `mxgraph.aws4.glacier` | Cold-tier archival storage |
| S3 Storage Lens | `mxgraph.aws4.s3_storage_lens` | Storage usage analytics |
