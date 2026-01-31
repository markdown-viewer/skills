---
name: infographic
description: Create beautiful infographics with pre-designed templates. Best for KPI cards, timelines, roadmaps, step-by-step processes, A vs B comparisons, SWOT analysis, funnels, org trees, pie/bar charts. Use when you need quick visual impact with 4-8 items. Simple YAML-like syntax. NOT for complex data analysis (use vega) or technical flowcharts (use mermaid).
auth: Infographic is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Infographic Visualizer

> **⚠️ CHECK TEMPLATES:** Wrong template names WILL cause render failures.

## When to Use & Available Templates

**✅ Use infographic when:**
- **Feature list / checklist**: `list-grid-badge-card`, `list-grid-candy-card-lite`, `list-grid-ribbon-card`, `list-column-done-list`, `list-column-vertical-icon-arrow`, `list-column-simple-vertical-arrow`, `list-row-horizontal-icon-arrow`, `list-row-simple-illus`, `list-sector-plain-text`, `list-zigzag-down-compact-card`, `list-zigzag-down-simple`, `list-zigzag-up-compact-card`, `list-zigzag-up-simple`
- **Timeline / milestones**: `sequence-timeline-simple`, `sequence-timeline-rounded-rect-node`, `sequence-timeline-simple-illus`
- **Step-by-step process**: `sequence-snake-steps-simple`, `sequence-snake-steps-compact-card`, `sequence-snake-steps-underline-text`, `sequence-stairs-front-compact-card`, `sequence-stairs-front-pill-badge`, `sequence-ascending-steps`, `sequence-ascending-stairs-3d-underline-text`, `sequence-circular-simple`, `sequence-pyramid-simple`, `sequence-mountain-underline-text`, `sequence-cylinders-3d-simple`, `sequence-zigzag-steps-underline-text`, `sequence-zigzag-pucks-3d-simple`, `sequence-horizontal-zigzag-underline-text`, `sequence-horizontal-zigzag-simple-illus`, `sequence-color-snake-steps-horizontal-icon-line`
- **Product roadmap**: `sequence-roadmap-vertical-simple`, `sequence-roadmap-vertical-plain-text`
- **Funnel / conversion**: `sequence-filter-mesh-simple`, `sequence-funnel-simple`
- **A vs B comparison**: `compare-binary-horizontal-underline-text-vs`, `compare-binary-horizontal-simple-fold`, `compare-binary-horizontal-badge-card-arrow`, `compare-hierarchy-left-right-circle-node-pill-badge`
- **SWOT analysis**: `compare-swot`
- **Priority matrix 2×2**: `quadrant-quarter-simple-card`, `quadrant-quarter-circular`, `quadrant-simple-illus`
- **Org tree / hierarchy**: `hierarchy-tree-tech-style-capsule-item`, `hierarchy-tree-curved-line-rounded-rect-node`, `hierarchy-tree-tech-style-badge-card`, `hierarchy-structure`
- **Pie / donut chart**: `chart-pie-plain-text`, `chart-pie-compact-card`, `chart-pie-donut-plain-text`, `chart-pie-donut-pill-badge`
- **Bar / column chart**: `chart-bar-plain-text`, `chart-column-simple`, `chart-line-plain-text`
- **Word cloud**: `chart-wordcloud`
- **Relation / circle**: `relation-circle-icon-badge`, `relation-circle-circular-progress`

## Syntax Structure

```plain
infographic <template-name>
data
  title Title
  desc Description
  items
    - label Label
      value 12.5
      desc Explanation
      icon mdi/rocket-launch
theme
  palette #3b82f6 #8b5cf6 #f97316
```

**Rules:** First line `infographic <template-name>` (must match template list) | 2-space indentation | `key value` pairs | `-` prefix for arrays | Compare templates need exactly 2 root items with `children` | SWOT needs exactly 4 items (Strengths/Weaknesses/Opportunities/Threats in English) | list templates use `desc` not `value` | `hierarchy-structure` max 3 levels

## Data Fields

| Field | Description | Example |
|-------|-------------|---------|
| `label` | Item title/name (required) | `label Q1 Sales` |
| `desc` | Description text | `desc 12.8 亿元 \| +20%` |
| `value` | Numeric value (charts/funnels only) | `value 128` |
| `icon` | Icon: `mdi/icon-name` ([Iconify](https://icon-sets.iconify.design/)) | `icon mdi/star` |
| `illus` | Illustration name ([unDraw](https://undraw.co/illustrations)) | `illus coding` |
| `children` | Nested items (hierarchy/compare) | See examples |
| `done` | Completion status (checklist) | `done true` |

## Core Examples

### Feature Grid (list-grid-badge-card)
```infographic
infographic list-grid-badge-card
data
  title Key Metrics
  desc Annual performance overview
  items
    - label Total Revenue
      desc 12.8 亿元 | YoY +23.5%
    - label New Customers
      desc 3280 | YoY +45%
    - label Satisfaction
      desc 94.6% | Industry leading
    - label Market Share
      desc 18.5% | Rank #2
```

### Timeline (sequence-timeline-simple)
```infographic
infographic sequence-timeline-simple
data
  title Product Roadmap
  items
    - label Q1 2024
      desc Research phase
    - label Q2 2024
      desc Design phase
    - label Q3 2024
      desc Development
    - label Q4 2024
      desc Launch
```

### Funnel Chart (sequence-filter-mesh-simple)
```infographic
infographic sequence-filter-mesh-simple
data
  title Sales Funnel
  items
    - label Leads
      value 10000
      desc Market leads
    - label Qualified
      value 2500
      desc 25% conversion
    - label Proposals
      value 800
      desc 32% conversion
    - label Closed
      value 328
      desc 41% conversion
```

### Checklist (list-column-done-list)
```infographic
infographic list-column-done-list
data
  title Launch Checklist
  items
    - label Code review completed
      done true
    - label Tests passing
      done true
    - label Documentation updated
      done false
    - label Deploy to production
      done false
```

### A vs B Comparison (compare-binary-horizontal-underline-text-vs)
```infographic
infographic compare-binary-horizontal-underline-text-vs
data
  title Cloud vs On-Premise
  items
    - label Cloud
      children
        - label Scalable on demand
        - label Pay as you go
    - label On-Premise
      children
        - label Full control
        - label One-time cost
```

### SWOT Analysis (compare-swot)
Must have exactly 4 items with English labels: Strengths, Weaknesses, Opportunities, Threats
```infographic
infographic compare-swot
data
  title Strategic Analysis
  items
    - label Strengths
      children
        - label Strong R&D
        - label Complete supply chain
    - label Weaknesses
      children
        - label Limited brand awareness
        - label High costs
    - label Opportunities
      children
        - label Digital transformation
        - label Emerging markets
    - label Threats
      children
        - label Intense competition
        - label Market changes
```

### Pie/Donut Chart (chart-pie-donut-plain-text)
```infographic
infographic chart-pie-donut-plain-text
data
  title Revenue by Product
  items
    - label Enterprise Software
      value 42
    - label Cloud Services
      value 28
    - label Hardware
      value 18
    - label Services
      value 12
```

### Organization Tree (hierarchy-tree-tech-style-capsule-item)
```infographic
infographic hierarchy-tree-tech-style-capsule-item
data
  title Organization Structure
  items
    - label CEO
      children
        - label VP Engineering
          children
            - label Frontend Team
            - label Backend Team
        - label VP Product
          children
            - label Design
            - label Research
```


## Output Format

````markdown
```infographic
infographic <template-name>
data
  title Your Title
  items
    - label Item 1
      desc Description here
```
````

## Related Files

> For detailed syntax, templates, and examples, refer to references below:

- [syntax.md](references/syntax.md) — Complete syntax specification and rules
- [templates.md](references/templates.md) — All available templates with descriptions
- [examples.md](references/examples.md) — Full examples for each template category

## Resources

- [AntV Infographic Gallery](https://infographic.antv.vision/examples)
- [Iconify Icons](https://icon-sets.iconify.design/)
- [unDraw Illustrations](https://undraw.co/illustrations)
