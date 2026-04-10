# Value Stream Mapping

Lean manufacturing value stream: supplier → production processes → customer, with inventory, kanban, and shipment.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Supplier / Customer | `mxgraph.lean_mapping.outside_sources` |
| Manufacturing Process | `mxgraph.lean_mapping.manufacturing_process` |
| Supermarket | `mxgraph.lean_mapping.supermarket` |
| FIFO Lane | `mxgraph.lean_mapping.fifo_lane` |
| Truck Shipment | `mxgraph.lean_mapping.truck_shipment` |
| Production Kanban | `mxgraph.lean_mapping.production_kanban` |
| Withdrawal Kanban | `mxgraph.lean_mapping.withdrawal_kanban` |
| Inventory Box | `mxgraph.lean_mapping.inventory_box` |
| Operator | `mxgraph.lean_mapping.operator` |
| Kaizen Burst | `mxgraph.lean_mapping.kaizen_lightening_burst` |
| MRP / ERP | `mxgraph.lean_mapping.mrp_erp` |
| Warehouse | `mxgraph.lean_mapping.warehouse` |
| Push Arrow | `mxgraph.lean_mapping.push_arrow` |

## Example

Auto parts manufacturing: steel supplier → stamping → welding → assembly → customer shipment with kanban pull system:

```plantuml
@startuml
left to right direction

mxgraph.lean_mapping.outside_sources "Steel\nSupplier" as supplier
mxgraph.lean_mapping.truck_shipment "Inbound\nWeekly" as truck_in
mxgraph.lean_mapping.warehouse "Raw Material\nWarehouse" as raw_wh
mxgraph.lean_mapping.inventory_box "5 Days" as inv_raw

mxgraph.lean_mapping.manufacturing_process "Stamping\nC/T 10s" as stamp
mxgraph.lean_mapping.operator "1 Op" as op1
mxgraph.lean_mapping.supermarket "WIP\nBuffer" as super1

mxgraph.lean_mapping.manufacturing_process "Welding\nC/T 25s" as weld
mxgraph.lean_mapping.operator "2 Op" as op2
mxgraph.lean_mapping.fifo_lane "FIFO" as fifo

mxgraph.lean_mapping.manufacturing_process "Assembly\nC/T 35s" as assy
mxgraph.lean_mapping.operator "3 Op" as op3

mxgraph.lean_mapping.warehouse "Finished Goods\nWarehouse" as fg_wh
mxgraph.lean_mapping.inventory_box "2 Days" as inv_fg
mxgraph.lean_mapping.truck_shipment "Outbound\nDaily" as truck_out
mxgraph.lean_mapping.outside_sources "Auto\nCustomer" as customer

mxgraph.lean_mapping.mrp_erp "MRP\nSystem" as mrp
mxgraph.lean_mapping.production_kanban "Production\nKanban" as pk
mxgraph.lean_mapping.withdrawal_kanban "Withdrawal\nKanban" as wk
mxgraph.lean_mapping.kaizen_lightening_burst "Reduce\nWIP" as kaizen

supplier --> truck_in
truck_in --> raw_wh
raw_wh --> inv_raw
inv_raw --> stamp
op1 --> stamp
stamp --> super1
super1 --> weld
op2 --> weld
weld --> fifo
fifo --> assy
op3 --> assy
assy --> fg_wh
fg_wh --> inv_fg
inv_fg --> truck_out
truck_out --> customer

mrp ..> supplier : "forecast"
mrp ..> pk
pk ..> stamp
customer ..> wk
wk ..> super1
kaizen ..> super1
@enduml
```

## Pattern Notes

1. **Outside Sources** — `mxgraph.lean_mapping.outside_sources` represents the supplier (left) and customer (right) — the two ends of the value stream
2. **Process boxes** — `mxgraph.lean_mapping.manufacturing_process` with cycle time (C/T) in the label; `mxgraph.lean_mapping.operator` shows staffing per station
3. **Pull system** — Supermarket buffer (`mxgraph.lean_mapping.supermarket`) + Withdrawal Kanban creates a pull signal from downstream; Production Kanban triggers upstream replenishment
4. **FIFO Lane** — `mxgraph.lean_mapping.fifo_lane` between welding and assembly ensures first-in-first-out sequencing without a supermarket
5. **Inventory indicators** — `mxgraph.lean_mapping.inventory_box` shows days of inventory at raw material and finished goods stages
6. **Information flow** — Dashed arrows (`..>`) represent information/kanban signals; solid arrows (`-->`) represent physical material flow
7. **Kaizen Burst** — `mxgraph.lean_mapping.kaizen_lightening_burst` marks improvement opportunities (reduce WIP at supermarket buffer)

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Boat Shipment | `mxgraph.lean_mapping.boat_shipment` | Maritime logistics routes |
| Signal Kanban | `mxgraph.lean_mapping.signal_kanban` | Batch-triggered replenishment |
| Work Cell | `mxgraph.lean_mapping.work_cell` | U-shaped cell layout |
| Shared Process | `mxgraph.lean_mapping.manufacturing_process_shared` | Shared equipment stations |
| Timeline | `mxgraph.lean_mapping.timeline2` | Lead time visualization |
| Load Leveling | `mxgraph.lean_mapping.load_leveling` | Heijunka box smoothing |
