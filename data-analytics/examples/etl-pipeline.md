# ETL Pipeline

Glue-based ETL pipeline with crawlers, data quality checks, and multi-format data integration.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Glue | `mxgraph.aws4.glue` |
| Glue Crawlers | `mxgraph.aws4.glue_crawlers` |
| Glue Data Catalog | `mxgraph.aws4.glue_data_catalog` |
| Glue Data Quality | `mxgraph.aws4.aws_glue_data_quality` |
| S3 | `mxgraph.aws4.s3` |
| Lambda | `mxgraph.aws4.lambda_function` |
| Redshift | `mxgraph.aws4.redshift` |

## Example

Multi-stage ETL with data quality gates and automatic schema discovery:

```plantuml
@startuml
left to right direction

rectangle "Raw Data" {
  mxgraph.aws4.s3 "JSON\nLogs" as json
  mxgraph.aws4.s3 "CSV\nExports" as csv
  mxgraph.aws4.s3 "Parquet\nArchive" as parquet
}

rectangle "Discovery" {
  mxgraph.aws4.glue_crawlers "Schema\nCrawler" as crawler
  mxgraph.aws4.glue_data_catalog "Data\nCatalog" as catalog
}

rectangle "Transform" {
  mxgraph.aws4.glue "ETL Job\n(Spark)" as etl
  mxgraph.aws4.aws_glue_data_quality "Quality\nCheck" as dq
}

rectangle "Targets" {
  mxgraph.aws4.s3 "Curated\nData (S3)" as curated
  mxgraph.aws4.redshift "Redshift" as rs
  mxgraph.aws4.lambda_function "Alert on\nFailure" as alert
}

json --> crawler
csv --> crawler
parquet --> crawler
crawler --> catalog
catalog --> etl
etl --> dq
dq --> curated : "pass"
dq --> alert : "fail"
curated --> rs
@enduml
```

## Pattern Notes

1. **Crawlers first**: auto-discover schemas from raw S3 data, register in catalog before ETL reads
2. **Data Quality gate**: Glue Data Quality validates row counts, null checks, and custom rules mid-pipeline
3. **Branching on quality**: passed data flows to curated bucket → Redshift; failures trigger Lambda alerts
4. **Multi-format**: crawlers handle JSON, CSV, Parquet, Avro — ETL normalizes to Parquet for curated layer

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Glue DataBrew | `mxgraph.aws4.glue_databrew` | Visual data preparation |
| Step Functions | `mxgraph.aws4.step_functions` | Orchestrating multi-stage ETL |
| EventBridge | `mxgraph.aws4.eventbridge` | Schedule or event triggers |
| CloudWatch | `mxgraph.aws4.cloudwatch` | Job monitoring & alerts |
| MWAA | `mxgraph.aws4.managed_workflows_for_apache_airflow` | Airflow-based orchestration |
| Athena | `mxgraph.aws4.athena` | SQL validation on curated data |
