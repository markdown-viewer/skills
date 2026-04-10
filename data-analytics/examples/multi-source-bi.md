# Multi-source BI

Cross-database business intelligence with federated queries, materialized views, and interactive dashboards.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Aurora | `mxgraph.aws4.aurora` |
| DynamoDB | `mxgraph.aws4.dynamodb` |
| Redshift | `mxgraph.aws4.redshift` |
| Athena | `mxgraph.aws4.athena` |
| QuickSight | `mxgraph.aws4.quicksight` |
| S3 | `mxgraph.aws4.s3` |
| Glue | `mxgraph.aws4.glue` |

## Example

Enterprise BI unifying operational databases, data lake, and warehouse into unified dashboards:

```plantuml
@startuml
left to right direction

rectangle "Operational" {
  mxgraph.aws4.aurora "Sales DB\n(Aurora)" as sales
  mxgraph.aws4.dynamodb "Product\nCatalog" as catalog
  mxgraph.aws4.rds_postgresql_instance "Finance DB\n(PostgreSQL)" as finance
}

rectangle "Integration" {
  mxgraph.aws4.glue "Glue ETL" as glue
  mxgraph.aws4.s3 "Data Lake\n(S3)" as lake
}

rectangle "Analytics Engines" {
  mxgraph.aws4.redshift "Redshift" as rs
  mxgraph.aws4.athena "Athena" as athena
}

rectangle "Dashboards" {
  mxgraph.aws4.quicksight "Revenue\nDashboard" as rev
  mxgraph.aws4.quicksight "Inventory\nDashboard" as inv
  mxgraph.aws4.quicksight "Finance\nReports" as fin
}

sales --> glue
catalog --> glue
finance --> glue
glue --> lake
lake --> rs
lake --> athena
rs --> rev
rs --> fin
athena --> inv
@enduml
```

## Pattern Notes

1. **Glue unification**: ETL normalizes heterogeneous sources (Aurora, DynamoDB, PostgreSQL) into common Parquet schema
2. **Dual query engines**: Redshift for heavy joins/aggregations (revenue, finance), Athena for ad-hoc inventory queries
3. **QuickSight SPICE**: in-memory cache enables sub-second dashboard interactions without direct DB queries
4. **Separate dashboards**: different teams get purpose-built views — revenue, inventory, finance — all from the same data lake

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Data Exchange | `mxgraph.aws4.data_exchange` | Third-party data set subscriptions |
| DataZone | `mxgraph.aws4.datazone` | Data governance catalog portal |
| Lake Formation | `mxgraph.aws4.lake_formation` | Fine-grained access control |
| Clean Rooms | `mxgraph.aws4.clean_rooms` | Cross-org collaborative analytics |
| Glue Catalog | `mxgraph.aws4.glue_data_catalog` | Centralized schema registry |
| API Gateway | `mxgraph.aws4.api_gateway` | Exposing data APIs to partners |
