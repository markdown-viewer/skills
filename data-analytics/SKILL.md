---
name: data-analytics
description: Create data analytics and data pipeline diagrams using PlantUML syntax with analytics/database stencil icons. Best for ETL pipelines, data lakes, real-time streaming, data warehousing, and BI dashboards. NOT for general software modeling (use uml) or general cloud infra (use cloud skill).
metadata:
  author: Data analytics diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Data Analytics Diagram Generator

**Quick Start:** Define data sources → Declare ingestion/ETL icons → Connect to storage/warehouse → Add BI/visualization → Wrap in ` ```plantuml ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use `left to right direction` for data pipelines (Source → Ingest → Transform → Store → Visualize)
- Use `mxgraph.aws4.*` stencil syntax for analytics, database, and storage icons
- Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`
- Use `rectangle "Zone" { ... }` or `package "Layer" { ... }` for grouping pipeline stages
- Directed flows use `-->`, async/streaming flows use `..>` (dashed)

**Full stencil reference:** See [stencils/README.md](../uml/stencils/README.md) for 9500+ available icons.

## Mxgraph Stencil Syntax

```
mxgraph.aws4.<icon> "Label" as <alias>
```

### Analytics & ETL Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| Query Engine | `athena`, `athena_data_source_connectors` | Serverless SQL on S3 data |
| ETL | `glue`, `glue_crawlers`, `glue_data_catalog`, `aws_glue_data_quality`, `aws_glue_for_ray` | Data integration & cataloging |
| Streaming | `kinesis`, `kinesis_data_streams`, `kinesis_data_firehose`, `kinesis_data_analytics`, `kinesis_video_streams` | Real-time data streaming |
| MapReduce | `emr`, `emr_engine`, `emr_engine_mapr_m3`, `emr_engine_mapr_m5` | Big data processing (Spark, Hive) |
| Data Warehouse | `redshift`, `redshift_ra3`, `redshift_streaming_ingestion`, `redshift_ml` | Columnar analytics warehouse |
| Search | `opensearch_service_data_node`, `opensearch_ingestion`, `cloudsearch` | Full-text search & log analytics |
| BI | `quicksight` | Dashboards & visualizations |
| Data Lake | `lake_formation`, `s3`, `glacier`, `glacier_deep_archive` | Governed data lake storage |
| Catalog | `datazone_custom_asset_type`, `data_exchange` | Data governance & sharing |
| Streaming Kafka | `msk`, `msk_connect` | Managed Kafka streaming |

### Database Stencils

| Category | Stencils | Purpose |
|----------|----------|---------|
| Relational | `aurora`, `aurora_instance`, `rds`, `rds_instance`, `rds_mysql_instance`, `rds_postgresql_instance` | Transactional databases |
| NoSQL | `dynamodb`, `dynamodb_table`, `dynamodb_global_secondary_index`, `dynamodb_stream` | Key-value & document store |
| Graph | `neptune` | Graph database |
| In-Memory | `elasticache`, `elasticache_for_redis`, `elasticache_for_memcached` | Cache & session store |
| Document | `documentdb`, `documentdb_with_mongodb_compatibility` | Document database |
| Ledger | `quantum_ledger_database` | Immutable transaction log |
| Wide-Column | `keyspaces` | Cassandra-compatible |

### Connection Types

| Syntax | Meaning | Use Case |
|--------|---------|----------|
| `A --> B` | Solid arrow | Batch data flow / API call |
| `A ..> B` | Dashed arrow | Streaming / async / CDC |
| `A -- B` | Solid line | Bidirectional sync |
| `A --> B : "label"` | Labeled connection | Describe data format or volume |

### Quick Example

```plantuml
@startuml
left to right direction
mxgraph.aws4.s3 "Data Lake\n(S3)" as s3
mxgraph.aws4.glue "Glue\nETL" as glue
mxgraph.aws4.redshift "Redshift" as rs
mxgraph.aws4.quicksight "QuickSight" as qs

s3 --> glue
glue --> rs
rs --> qs
@enduml
```

## Data Analytics Architecture Types

| Type | Purpose | Key Stencils | Example |
|------|---------|--------------|---------|
| Data Lake | Centralized raw data store | `s3`, `lake_formation`, `glue`, `athena` | [data-lake.md](examples/data-lake.md) |
| Real-time Streaming | Event stream processing | `kinesis`, `msk`, `lambda_function`, `opensearch_service` | [real-time-streaming.md](examples/real-time-streaming.md) |
| Data Warehouse | Star-schema analytics | `redshift`, `glue`, `quicksight` | [data-warehouse.md](examples/data-warehouse.md) |
| ETL Pipeline | Extract-transform-load | `glue`, `glue_crawlers`, `glue_data_catalog`, `s3` | [etl-pipeline.md](examples/etl-pipeline.md) |
| Log Analytics | Centralized logging | `kinesis_data_firehose`, `opensearch_service`, `lambda_function` | [log-analytics.md](examples/log-analytics.md) |
| ML Feature Store | Feature engineering pipeline | `glue`, `s3`, `athena`, `emr` | [ml-feature-pipeline.md](examples/ml-feature-pipeline.md) |
| CDC Pipeline | Database change capture | `dynamodb_streams`, `kinesis`, `lambda_function`, `redshift` | [cdc-pipeline.md](examples/cdc-pipeline.md) |
| Multi-source BI | Cross-database reporting | `aurora`, `dynamodb`, `redshift`, `quicksight` | [multi-source-bi.md](examples/multi-source-bi.md) |
