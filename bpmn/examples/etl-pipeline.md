# ETL Pipeline

Data extraction from multiple sources, transformation, quality validation, and loading to data warehouse.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Start Event | `mxgraph.bpmn.event.start` |
| End Event | `mxgraph.bpmn.event.end` |
| Timer Start | `mxgraph.bpmn.event.timerStart` |
| Error End | `mxgraph.bpmn.event.errorEnd` |
| Parallel Gateway | `mxgraph.bpmn.gateway2.parallel` |
| Exclusive Gateway | `mxgraph.bpmn.gateway2.exclusive` |
| Channel Adapter | `mxgraph.eip.channel_adapter` |
| Message Translator | `mxgraph.eip.message_translator` |
| Aggregator | `mxgraph.eip.aggregator` |
| Content Enricher | `mxgraph.eip.content_enricher` |
| Dead Letter Channel | `mxgraph.eip.deadLetterChannel` |
| Data Object | `mxgraph.bpmn.data2.dataObject` |

## Example

Nightly ETL: extract from CRM + ERP + logs in parallel, transform, validate, load to warehouse:

```plantuml
@startuml
left to right direction

mxgraph.bpmn.event.timerStart "Daily\n02:00 AM" as timer

mxgraph.bpmn.gateway2.parallel "Extract\nFork" as fork_extract

rectangle "Extract" {
  mxgraph.eip.channel_adapter "CRM\nExtract" as ext_crm
  mxgraph.eip.channel_adapter "ERP\nExtract" as ext_erp
  mxgraph.eip.channel_adapter "Log\nExtract" as ext_log
}

mxgraph.bpmn.gateway2.parallel "Extract\nJoin" as join_extract

rectangle "Transform" {
  mxgraph.eip.message_translator "Normalize\nSchema" as normalize
  mxgraph.eip.content_enricher "Enrich\nDimensions" as enrich
  rectangle "Deduplication" as dedup
}

mxgraph.bpmn.gateway2.exclusive "Quality\nCheck?" as gw_quality

rectangle "Load" {
  rectangle "Load to\nStaging" as staging
  rectangle "Merge to\nWarehouse" as warehouse
  rectangle "Update\nIndexes" as index
}

mxgraph.bpmn.event.end "ETL\nComplete" as end_ok
mxgraph.eip.deadLetterChannel "Error\nQueue" as dlq
rectangle "Alert\nOps Team" as alert
mxgraph.bpmn.event.errorEnd "ETL\nFailed" as end_fail

timer --> fork_extract
fork_extract --> ext_crm
fork_extract --> ext_erp
fork_extract --> ext_log
ext_crm --> join_extract
ext_erp --> join_extract
ext_log --> join_extract

join_extract --> normalize
normalize --> enrich
enrich --> dedup
dedup --> gw_quality

gw_quality --> staging : "Pass"
gw_quality --> dlq : "Fail"

staging --> warehouse
warehouse --> index
index --> end_ok

dlq --> alert
alert --> end_fail
@enduml
```

## Pattern Notes

1. **Timer Start Event** — `mxgraph.bpmn.event.timerStart` kicks off the scheduled nightly ETL batch at 02:00 AM
2. **Parallel extraction** — Parallel Gateway forks to extract from CRM, ERP, and logs concurrently, then joins when all sources are ready
3. **EIP + BPMN hybrid** — Channel Adapters (`mxgraph.eip.channel_adapter`) for source connectors, Message Translator for schema normalization, Content Enricher for dimension lookups
4. **Quality gate** — Exclusive Gateway checks data quality after deduplication; failures route to Dead Letter Channel
5. **Three-stage load** — staging → warehouse merge → index update follows standard ETL loading pattern

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Content Filter | `mxgraph.eip.content_filter` | Strip unnecessary source fields |
| Normalizer | `mxgraph.eip.normalizer` | Multi-format data normalization |
| Resequencer | `mxgraph.eip.resequencer` | Record ordering before load |
| Timer Catching | `mxgraph.bpmn.event.timerCatching` | Wait/delay between ETL stages |
| Message Store | `mxgraph.eip.message_store` | Checkpoint/staging buffer |
| Control Bus | `mxgraph.eip.control_bus` | Pipeline monitoring/control |
