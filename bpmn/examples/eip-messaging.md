# EIP Messaging Integration

Enterprise Integration Patterns: content-based routing, message transformation, and dead letter handling.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Messaging Gateway | `mxgraph.eip.messaging_gateway` |
| Content-Based Router | `mxgraph.eip.content_based_router` |
| Message Translator | `mxgraph.eip.message_translator` |
| Content Enricher | `mxgraph.eip.content_enricher` |
| Splitter | `mxgraph.eip.splitter` |
| Aggregator | `mxgraph.eip.aggregator` |
| Message Filter | `mxgraph.eip.message_filter` |
| Message Channel | `mxgraph.eip.messageChannel` |
| Dead Letter Channel | `mxgraph.eip.deadLetterChannel` |
| Wire Tap | `mxgraph.eip.wire_tap` |
| Channel Adapter | `mxgraph.eip.channel_adapter` |
| Recipient List | `mxgraph.eip.recipient_list` |

## Example

Order messages routed by type, transformed, enriched, split into line items, and aggregated for fulfillment:

```plantuml
@startuml
left to right direction

mxgraph.eip.messaging_gateway "API\nGateway" as gw
mxgraph.eip.wire_tap "Audit\nLog" as audit
mxgraph.eip.content_based_router "Order\nRouter" as router

rectangle "Standard Order" {
  mxgraph.eip.message_translator "Normalize\nFormat" as translate
  mxgraph.eip.content_enricher "Add Customer\nProfile" as enrich
  mxgraph.eip.splitter "Split Line\nItems" as split
  mxgraph.eip.aggregator "Aggregate\nResults" as agg
}

rectangle "Priority Order" {
  mxgraph.eip.message_filter "Validate\nPriority" as filter
  mxgraph.eip.channel_adapter "Express\nFulfillment" as express
}

rectangle "Bulk Order" {
  mxgraph.eip.recipient_list "Distribute to\nWarehouses" as dist
  mxgraph.eip.channel_adapter "Warehouse\nA" as wh_a
  mxgraph.eip.channel_adapter "Warehouse\nB" as wh_b
}

mxgraph.eip.messageChannel "Fulfillment\nQueue" as fulfill_q
mxgraph.eip.deadLetterChannel "Dead Letter\nQueue" as dlq

gw --> audit
gw --> router
router --> translate : "standard"
router --> filter : "priority"
router --> dist : "bulk"

translate --> enrich
enrich --> split
split --> agg
agg --> fulfill_q

filter --> express
express --> fulfill_q

dist --> wh_a
dist --> wh_b
wh_a --> fulfill_q
wh_b --> fulfill_q

router ..> dlq : "unknown type"
filter ..> dlq : "invalid"
@enduml
```

## Pattern Notes

1. **Content-Based Router** — `mxgraph.eip.content_based_router` inspects message content (order type) and routes to the correct processing pipeline
2. **Wire Tap** — `mxgraph.eip.wire_tap` sends a copy of every message to the audit log without affecting the main flow
3. **Splitter → Aggregator** — `mxgraph.eip.splitter` breaks a multi-line order into individual items; `mxgraph.eip.aggregator` collects results back into a single message
4. **Recipient List** — `mxgraph.eip.recipient_list` distributes bulk orders to multiple warehouses based on availability
5. **Dead Letter Channel** — `mxgraph.eip.deadLetterChannel` captures unroutable or invalid messages; dashed arrows (`..>`) indicate error/fallback flows
6. **Channel Adapter** — `mxgraph.eip.channel_adapter` bridges between the messaging system and external services (fulfillment, warehouses)

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Dynamic Router | `mxgraph.eip.dynamic_router` | Rule-based adaptive routing |
| Routing Slip | `mxgraph.eip.routing_slip` | Multi-step processing chains |
| Normalizer | `mxgraph.eip.normalizer` | Multi-format message normalization |
| Resequencer | `mxgraph.eip.resequencer` | Out-of-order message reordering |
| Claim Check | `mxgraph.eip.claim_check` | Large payload store-and-retrieve |
| Content Filter | `mxgraph.eip.content_filter` | Strip unnecessary message fields |
