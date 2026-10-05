---
name: documd-visuals
license: CC-BY-4.0
compatibility: >
  Figures are text in the Markdown — fenced blocks or bare HTML — and the host viewer renders them live:
  nothing to pre-render, build or install. Export to html / epub / docx / pdf is optional and needs
  Node 18+ and Chrome/Chromium, via `npx @markdown-viewer/documd`.
description: >
  Create text-driven visuals in Markdown: charts, diagrams, cards, architecture and page layouts.
  Charts and analytical views (bar, line, pie, heatmap, correlation, regression); reliability and
  operations (latency, incident, throughput, cycle time, OKR, standup, on-call); product and finance
  (funnel, retention, revenue, budget); process and workflow (approval, BPMN); software design and
  behaviour (class, state machine, sequence, C4); dependencies and impact (dependency graph, ER, causality);
  system architecture as HTML (layer stack, wings, zones, topology, service catalogue, request
  paths); infrastructure (cloud, Kubernetes, ETL, network, security, IAM, compliance); governance and people
  (ArchiMate, org chart, hiring); knowledge and planning (mind map, roadmap, Gantt, migration); documents
  (comparison, SWOT, memo, policy, catalogue, case study). Use when a document needs a diagram, chart or
  card. Figures render live. Not for slide decks or math notation. Not recommended: mermaid / canvas /
  drawio / dot.
---

# documd visuals

Routing for every diagram, chart, card and layout this document pipeline can render.

**Figures are text, in place.** A fence (`plantuml` · `vega` · `echarts` · `infographic`) or bare HTML
written into the Markdown *is* the figure: the viewer draws it live, the block stays editable, and nothing
is pre-rendered, built or exported first. `documd` is optional — export and verification only.

## Iron rules

1. **Allowed fences** — `plantuml` / `puml` · `vega` · `vega-lite` · `echarts` · `infographic`,
   plus **bare HTML** — which is how system architecture diagrams, cards and page layouts are drawn.
2. **Nothing outside that list.** A fence the list does not name is a bug, not a lesser option —
   there is no second-tier engine.
3. **One diagram per fence.** Do not put two engines in one block, and never nest fences.
4. **HTML is bare, never ` ```html `** — a fenced block becomes an image. Start from a real file rather
   than inventing one: [`layered-with-wings.md`](examples/system-architecture/layered-with-wings.md) for a
   system, [`executive-brief-summary.md`](examples/internal-documents/executive-brief-summary.md) for a card.
5. **Inline the data.** `vega` / `vega-lite` / `echarts` must carry their own `values` / `series` data;
   external URLs are unreliable on the export path.
6. **State the reading in the copy.** Every figure answers one question — put it in the prose or the
   block's `title`.
7. **Pick a theme, then colour from it.** Colours come from one of the themes indexed in
   [`styles/palette.md`](styles/palette.md); copy that theme's block for your engine and take every
   value from it — a hex picked by hand, or two themes in one figure, is a bug. Charts pass the
   categorical ramp in order; cards use one accent plus neutrals.

## Route by goal

Find the reader's goal, open the goal guide, pick an example. Engines are suggestions; the guide and
examples are authoritative.

### A — data & metrics

| Goal | Trigger keywords | Engines | Read |
|---|---|---|---|
| service-reliability | latency · p95/p99 · SLO · SLA · error budget · burn rate · availability · uptime · reliability | echarts vega infographic | [goals/service-reliability.md](goals/service-reliability.md) |
| ops-monitoring | incident load · alert volume · outliers · anomalies · service scorecard · support volume | echarts vega infographic | [goals/ops-monitoring.md](goals/ops-monitoring.md) |
| delivery-throughput | throughput · cycle time · lead time · velocity · capacity · staffing · backlog · WIP · rank movement | echarts vega infographic | [goals/delivery-throughput.md](goals/delivery-throughput.md) |
| goal-and-status-reporting | OKR · KPI · target vs actual · goal attainment · status board · dashboard · scorecard | echarts vega infographic html-css | [goals/goal-and-status-reporting.md](goals/goal-and-status-reporting.md) |
| product-metrics | conversion · funnel · adoption · retention · churn · activation · signup · cohorts · experiment | echarts infographic | [goals/product-metrics.md](goals/product-metrics.md) |
| business-reporting | quarterly results · revenue · ARR · revenue mix · margin · periodic results · forecast | infographic vega echarts | [goals/business-reporting.md](goals/business-reporting.md) |
| go-to-market | pipeline · channel · partner · partner tiers · market entry · sales funnel · SWOT · campaigns | echarts infographic | [goals/go-to-market.md](goals/go-to-market.md) |
| cost-and-budget | cost · spend · budget · cloud bill · savings · cost reduction · capex · unit economics | echarts infographic vega | [goals/cost-and-budget.md](goals/cost-and-budget.md) |
| data-exploration | correlation · distribution · regression · outlier detection · missing data · small multiples · density | vega echarts | [goals/data-exploration.md](goals/data-exploration.md) |

### B — process & systems

| Goal | Trigger keywords | Engines | Read |
|---|---|---|---|
| engineering-operations | standup · sprint ritual · team rhythm · on-call · coverage · shift handover · deploy cadence · checklist | infographic vega echarts | [goals/engineering-operations.md](goals/engineering-operations.md) |
| incident-management | incident · postmortem · escalation · triage · runbook · change request · launch readiness · review | infographic echarts html-css | [goals/incident-management.md](goals/incident-management.md) |
| process-and-workflow | approval · workflow · swimlane · SOP · process map · BPMN · gate · procurement | plantuml infographic | [goals/process-and-workflow.md](goals/process-and-workflow.md) |
| software-design | class · domain model · component · package · layering · use case · object · C4 container · SysML | plantuml | [goals/software-design.md](goals/software-design.md) |
| software-behaviour | state machine · lifecycle · sequence · interaction · messaging · event flow · EIP · deployment | plantuml | [goals/software-behaviour.md](goals/software-behaviour.md) |
| dependencies-and-relations | dependency · call graph · impact analysis · coupling · ownership · causality · fishbone | plantuml vega echarts infographic | [goals/dependencies-and-relations.md](goals/dependencies-and-relations.md) |
| system-architecture | system architecture · layer stack · zones · pipeline stages · service catalog · request path · connectors | html-css | [goals/system-architecture.md](goals/system-architecture.md) |

### C — infrastructure & governance

| Goal | Trigger keywords | Engines | Read |
|---|---|---|---|
| cloud-architecture | AWS · Azure · Kubernetes · container · serverless · IoT · edge · VPC · observability | plantuml infographic | [goals/cloud-architecture.md](goals/cloud-architecture.md) |
| data-platform | ETL · lakehouse · warehouse · CDC · streaming · ingestion · catalog · ML pipeline · ER model | plantuml | [goals/data-platform.md](goals/data-platform.md) |
| network-topology | network · topology · DMZ · wireless · firewall · switch · packet · route · traffic | plantuml echarts | [goals/network-topology.md](goals/network-topology.md) |
| security-and-compliance | zero trust · IAM · encryption · threat model · trust boundary · controls · evidence · audit · compliance · risk | plantuml infographic html-css | [goals/security-and-compliance.md](goals/security-and-compliance.md) |
| enterprise-architecture | ArchiMate · capability map · value stream · stakeholder map · business architecture | plantuml infographic | [goals/enterprise-architecture.md](goals/enterprise-architecture.md) |
| organization-and-roles | org chart · reporting line · workforce · capability coverage · capability maturity · handoffs · responsibilities | infographic vega echarts html-css | [goals/organization-and-roles.md](goals/organization-and-roles.md) |
| people-and-hiring | hiring · headcount plan · interview loop · onboarding · career ladder · certifications · progression | infographic | [goals/people-and-hiring.md](goals/people-and-hiring.md) |

### D — knowledge & expression

| Goal | Trigger keywords | Engines | Read |
|---|---|---|---|
| knowledge-and-outline | mind map · outline · knowledge map · concept map · topics · word cloud | plantuml infographic vega echarts | [goals/knowledge-and-outline.md](goals/knowledge-and-outline.md) |
| planning-and-roadmap | roadmap · milestone · timeline · Gantt · quarterly plan · release schedule · strategy focus | infographic vega plantuml html-css | [goals/planning-and-roadmap.md](goals/planning-and-roadmap.md) |
| migration-and-rollout | migration · cutover · rollout waves · phased delivery · programme · work breakdown | plantuml infographic | [goals/migration-and-rollout.md](goals/migration-and-rollout.md) |
| comparison-and-selection | compare · versus · build or buy · decision record · quadrant · vendor selection · trade-off · priority | infographic html-css | [goals/comparison-and-selection.md](goals/comparison-and-selection.md) |
| internal-documents | memo · brief · charter · abstract · policy · quote · principles | html-css infographic | [goals/internal-documents.md](goals/internal-documents.md) |
| catalogues-and-inventories | catalogue · inventory · entitlements · offerings · standard tools · support tiers | infographic | [goals/catalogues-and-inventories.md](goals/catalogues-and-inventories.md) |
| customer-and-partner-comms | customer story · case study · sales brief · bulletin · announcement · partner brief · education module | html-css | [goals/customer-and-partner-comms.md](goals/customer-and-partner-comms.md) |
| theme-and-tone | print · photocopy · handout · low vision · large print · colour-blind · slide · projected · long-form | infographic echarts plantuml | [goals/theme-and-tone.md](goals/theme-and-tone.md) |

## Engine cheat sheet

| Engine | Reach for it when | Look elsewhere when |
|---|---|---|
| `plantuml` | UML/ArchiMate/BPMN semantics, **brand and device icons** (9,514 stencils), or a relationship graph that should lay itself out | It is a chart |
| `vega` / `vega-lite` | The data needs work first — join, window, fold, regression, density, facets, small multiples | One polished chart with heavy styling (`echarts`) |
| `echarts` | Report-grade chart or KPI dashboard: axes, series, thresholds, annotations, gauges | The data must be transformed first |
| `infographic` | A designed-looking board: roadmap, timeline, checklist, comparison, quadrant, knowledge map | Axes, several series or statistical shapes (`echarts`) |
| HTML/CSS | Cards, memos, overviews, page-level layouts | Another engine already renders that diagram |

Details, limits and pitfalls: [`plantuml`](engines/plantuml.md) ·
[`echarts`](engines/echarts.md) · [`vega`](engines/vega.md) · [`infographic`](engines/infographic.md) ·
[`html-css`](engines/html-css.md).

## Capability boundaries

These are **not possible**; pick the fallback instead of retrying.

| Want | Fallback |
|---|---|
| 3D / globe / WebGL charts (no `echarts-gl`) | 2D `echarts`; `scatter`/`graph` for shape |
| Geographic maps (no bundled map data, no GeoJSON offline) | schematic rectangle layout, or an HTML/CSS region diagram |
| `dataset.transform` in ECharts (throws `RangeError` in 6.1.0) | sort and derive upstream, then `dataset.source` |
| Functions in an `echarts` option (parsed as JSON) | template strings (`"{c}%"`), per-item label objects |
| External data or images (`data.url`, remote URLs) | inline `values`, data URLs |
| PlantUML WBS / Salt / Timing / ditaa / JSON / YAML / EBNF / nwdiag / SDL / math (parse, draw nothing useful) | `@startmindmap`, a boxed rectangle tree, HTML/CSS mockups, or a code fence |
| Interactive charts (tooltip, zoom, brush) | annotate directly: labels, thresholds, callouts |
| Icons in `vega` / `echarts` | `plantuml` stencils |
| Free-form positioning in `infographic` | HTML/CSS for pixel control |

## Reading a document

To read a document in the browser or in VS Code, install **docu.md Markdown Viewer**:
<https://docu.md>.

## Exporting & verifying — optional

Authoring never needs this. The **`documd` CLI** converts a document or a diagram source to a file,
extracts figures as images, and verifies that blocks render — for when the output is a file. Nothing to
install: `npx @markdown-viewer/documd in.md out.docx`. Flags, formats and the npm-scope warning:
[converting.md](converting.md).

## When a block does not render

1. Fence in the allowed list? Exactly one block per figure?
2. Is it a listed anti-pattern in that engine's reference (see **Engine cheat sheet**) — or strict
   syntax (JSON for `echarts`/`vega`, no empty lines in bare HTML)?
3. Then switch to the alternative engine the goal guide names; most scenarios have two.
4. Or verify by rendering: `npx @markdown-viewer/documd file.md --assets /tmp/figs`.

## Where everything lives

[`catalog/scenarios.md`](catalog/scenarios.md) indexes every scenario with its domain, engines, tier and
example path — start there; then `goals/<domain>.md`, `engines/<engine>.md`, `examples/<domain>/<file>.md`.
