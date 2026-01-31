# Infographic Template Reference

Complete list of all available templates with descriptions.

---

## Template Categories

| Category | Prefix | Best For |
|----------|--------|----------|
| List | `list-*` | Feature lists, KPI cards, checklists |
| Sequence | `sequence-*` | Timelines, processes, funnels, roadmaps |
| Compare | `compare-*` | A vs B, SWOT analysis |
| Hierarchy | `hierarchy-*` | Org charts, tree structures |
| Chart | `chart-*` | Pie, bar, column, word cloud |
| Quadrant | `quadrant-*` | 2×2 matrices, priority grids |
| Relation | `relation-*` | Central concepts, relationships |

---

## List Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `list-grid-badge-card` ⭐ | Grid cards with badges | KPI cards, metrics |
| `list-grid-candy-card-lite` | Colorful grid cards | Features, services |
| `list-grid-ribbon-card` | Cards with ribbon decoration | Highlights, awards |
| `list-row-horizontal-icon-arrow` | Horizontal row with arrows | Process steps |
| `list-row-simple-illus` | Row with illustrations | Features with visuals |
| `list-sector-plain-text` | Radial sector layout | Categories |
| `list-column-done-list` ⭐ | Checklist with checkmarks | Tasks, checklists |
| `list-column-vertical-icon-arrow` | Vertical with arrows | Vertical process |
| `list-column-simple-vertical-arrow` | Simple vertical arrows | Simple flow |
| `list-zigzag-down-compact-card` | Zigzag down cards | Journey steps |
| `list-zigzag-down-simple` | Simple zigzag down | Simple journey |
| `list-zigzag-up-compact-card` | Zigzag up cards | Growth path |
| `list-zigzag-up-simple` | Simple zigzag up | Simple growth |

---

## Sequence Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `sequence-timeline-simple` ⭐ | Simple timeline | History, milestones |
| `sequence-timeline-rounded-rect-node` | Timeline with rounded nodes | Detailed timeline |
| `sequence-timeline-simple-illus` | Timeline with illustrations | Visual timeline |
| `sequence-roadmap-vertical-simple` ⭐ | Vertical roadmap | Product roadmap |
| `sequence-roadmap-vertical-plain-text` | Plain text roadmap | Simple roadmap |
| `sequence-filter-mesh-simple` ⭐ | Funnel chart | Sales funnel, conversion |
| `sequence-funnel-simple` | Simple funnel | Basic funnel |
| `sequence-snake-steps-simple` | Snake path steps | Long processes |
| `sequence-snake-steps-compact-card` | Snake with cards | Detailed steps |
| `sequence-snake-steps-underline-text` | Snake with underline | Minimal steps |
| `sequence-stairs-front-compact-card` | Front stairs cards | Growth/levels |
| `sequence-stairs-front-pill-badge` | Stairs with badges | Achievement levels |
| `sequence-ascending-steps` | Ascending steps | Progress |
| `sequence-ascending-stairs-3d-underline-text` | 3D stairs | Visual hierarchy |
| `sequence-circular-simple` | Circular flow | Cycles, loops |
| `sequence-pyramid-simple` | Pyramid structure | Hierarchies, priorities |
| `sequence-mountain-underline-text` | Mountain milestones | Achievements |
| `sequence-cylinders-3d-simple` | 3D cylinders | Data flow |
| `sequence-zigzag-steps-underline-text` | Zigzag steps | Alternating steps |
| `sequence-zigzag-pucks-3d-simple` | 3D pucks zigzag | Visual zigzag |
| `sequence-horizontal-zigzag-underline-text` | Horizontal zigzag | Wide processes |
| `sequence-horizontal-zigzag-simple-illus` | Zigzag illustrations | Visual process |
| `sequence-color-snake-steps-horizontal-icon-line` | Colorful snake | Eye-catching flow |

---

## Compare Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `compare-binary-horizontal-underline-text-vs` ⭐ | A vs B comparison | Product comparison |
| `compare-binary-horizontal-simple-fold` | Folded comparison | Compact compare |
| `compare-binary-horizontal-badge-card-arrow` | Badge cards with arrows | Feature compare |
| `compare-hierarchy-left-right-circle-node-pill-badge` | Hierarchy comparison | Structure compare |
| `compare-swot` ⭐ | SWOT analysis (4 quadrants) | Strategic analysis |

### SWOT Template Rules
- Must have exactly 4 root items
- Labels must be in English: `Strengths`, `Weaknesses`, `Opportunities`, `Threats`
- Each item should have `children` for details

---

## Hierarchy Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `hierarchy-tree-tech-style-capsule-item` ⭐ | Tech style tree | Org charts |
| `hierarchy-tree-curved-line-rounded-rect-node` | Curved tree | Soft org charts |
| `hierarchy-tree-tech-style-badge-card` | Tree with badge cards | Detailed hierarchy |
| `hierarchy-structure` | Generic hierarchy (max 3 levels) | Flexible structure |

### Hierarchy Rules
- `hierarchy-structure` supports maximum 3 levels
- Use `children` for nesting

---

## Chart Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `chart-pie-plain-text` | Pie chart | Simple distribution |
| `chart-pie-compact-card` | Pie with cards | Detailed pie |
| `chart-pie-donut-plain-text` ⭐ | Donut chart | Distribution |
| `chart-pie-donut-pill-badge` | Donut with badges | Labeled donut |
| `chart-bar-plain-text` | Horizontal bar chart | Comparisons |
| `chart-column-simple` | Vertical column chart | Time series |
| `chart-line-plain-text` | Line chart | Trends |
| `chart-wordcloud` | Word cloud | Keywords, topics |

### Chart Rules
- Use `value` field (numeric) for data
- Values represent relative proportions for pie/donut

---

## Quadrant Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `quadrant-quarter-simple-card` ⭐ | Quadrant cards | Priority matrix |
| `quadrant-quarter-circular` | Circular quadrant | Visual matrix |
| `quadrant-simple-illus` | Illustrated quadrant | Creative matrix |

### Quadrant Rules
- Must have exactly 4 items for quadrant templates
- Each item represents one quadrant

---

## Relation Templates

| Template | Description | Best For |
|----------|-------------|----------|
| `relation-circle-icon-badge` | Circle with badges | Central concept |
| `relation-circle-circular-progress` | Circular progress | Progress rings |

---

## Template Selection Guide

| Use Case | Recommended Template |
|----------|---------------------|
| KPI dashboard | `list-grid-badge-card` |
| Feature list | `list-grid-candy-card-lite` |
| Task checklist | `list-column-done-list` |
| Company history | `sequence-timeline-simple` |
| Product roadmap | `sequence-roadmap-vertical-simple` |
| Sales funnel | `sequence-filter-mesh-simple` |
| Onboarding flow | `sequence-snake-steps-simple` |
| Career ladder | `sequence-stairs-front-compact-card` |
| Product comparison | `compare-binary-horizontal-underline-text-vs` |
| SWOT analysis | `compare-swot` |
| Organization chart | `hierarchy-tree-tech-style-capsule-item` |
| Revenue breakdown | `chart-pie-donut-plain-text` |
| Priority matrix | `quadrant-quarter-simple-card` |
| Trending topics | `chart-wordcloud` |

---

## Item Count Guidelines

| Items | Recommendation |
|-------|----------------|
| 2 | Compare templates |
| 3-4 | Most templates work well |
| 4 | Quadrant templates (required) |
| 5-6 | Optimal for sequences |
| 7-8 | Maximum for visual clarity |
| 8+ | Consider splitting into multiple infographics |
