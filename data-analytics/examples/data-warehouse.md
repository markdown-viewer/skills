# Data Warehouse

Star-schema data warehouse with Redshift, Glue ETL, and QuickSight dashboards.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Redshift | `mxgraph.aws4.redshift` |
| Redshift RA3 | `mxgraph.aws4.redshift_ra3` |
| Glue | `mxgraph.aws4.glue` |
| Glue Data Catalog | `mxgraph.aws4.glue_data_catalog` |
| QuickSight | `mxgraph.aws4.quicksight` |
| S3 | `mxgraph.aws4.s3` |
| RDS | `mxgraph.aws4.rds` |

## Example

Enterprise data warehouse with multi-source ETL and executive dashboards:

```plantuml
@startuml
left to right direction

rectangle "Operational Sources" {
  mxgraph.aws4.rds "Orders DB\n(RDS)" as orders
  mxgraph.aws4.rds "CRM DB\n(RDS)" as crm
  mxgraph.aws4.s3 "Marketing\nCSVs (S3)" as csvs
}

rectangle "ETL Layer" {
  mxgraph.aws4.glue "Glue\nETL" as glue
  mxgraph.aws4.glue_data_catalog "Data\nCatalog" as catalog
  mxgraph.aws4.s3 "Staging\n(S3)" as staging
}

rectangle "Data Warehouse" {
  mxgraph.aws4.redshift "Redshift\nCluster" as rs
  mxgraph.aws4.redshift_ra3 "RA3\nNodes" as nodes
}

rectangle "BI Layer" {
  mxgraph.aws4.quicksight "Executive\nDashboard" as dash
  mxgraph.aws4.quicksight "Sales\nReports" as sales
}

orders --> glue
crm --> glue
csvs --> glue
glue --> catalog
glue --> staging
staging --> rs
rs --> nodes
rs --> dash
rs --> sales
@enduml
```

## Pattern Notes

1. **Glue ETL**: extracts from RDS/S3 sources, transforms to star schema (fact + dimension tables), loads to Redshift
2. **Data Catalog**: metadata registry — tables, schemas, and data lineage for governance
3. **Staging in S3**: intermediate Parquet files before COPY into Redshift for fault tolerance
4. **Multiple dashboards**: QuickSight SPICE datasets connected to Redshift for sub-second queries

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Redshift ML | `mxgraph.aws4.redshift_ml` | In-warehouse ML inference |
| Streaming Ingestion | `mxgraph.aws4.redshift_streaming_ingestion` | Real-time Kinesis ingestion |
| Athena | `mxgraph.aws4.athena` | Serverless SQL on S3 fallback |
| Lake Formation | `mxgraph.aws4.lake_formation` | Cross-account governance |
| Data Exchange | `mxgraph.aws4.data_exchange` | Third-party data sets |
| EMR | `mxgraph.aws4.emr` | Heavy ETL before warehouse load |
