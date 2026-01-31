---
name: vega
description: Create data-driven charts with Vega-Lite (simple) and Vega (advanced). Best for bar, line, scatter, heatmap, area charts, and multi-series analytics. Use when you have numeric data arrays needing statistical visualization. Vega for radar charts and word clouds. NOT for process diagrams (use mermaid) or quick KPI cards (use infographic).
auth: Vega is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Vega / Vega-Lite Visualizer

**Quick Start:** Structure data as array of objects → Choose mark type (bar/line/point/area/arc/rect) → Map encodings (x, y, color, size) to fields → Set data types (quantitative/nominal/ordinal/temporal) → Wrap in ` ```vega-lite ` or ` ```vega ` fence. Always include `$schema`, use valid JSON with double quotes, field names are case-sensitive. **Use Vega-Lite for 90% of charts; Vega only for radar, word cloud, force-directed.**

---

## Critical Syntax Rules

### Rule 1: Always Include Schema
```json
"$schema": "https://vega.github.io/schema/vega-lite/v5.json"
```

### Rule 2: Valid JSON Only
```
❌ {field: "x",}     → Trailing comma, unquoted key
✅ {"field": "x"}    → Proper JSON
```

### Rule 3: Field Names Must Match Data
```
❌ "field": "Category"  when data has "category"
✅ "field": "category"  → Case-sensitive match
```

### Rule 4: Type Must Be Valid
```
✅ quantitative | nominal | ordinal | temporal
❌ numeric | string | date
```

---

## Common Pitfalls

| Issue | Solution |
|-------|----------|
| Chart not rendering | Check JSON validity, verify `$schema` |
| Data not showing | Field names must match exactly |
| Wrong chart type | Match mark to data structure |
| Colors not visible | Check color scale contrast |
| Dual-axis issues | Add `resolve: {scale: {y: "independent"}}` |

---

## Output Format

````markdown
```vega-lite
{...}
```
````

Or for full Vega:

````markdown
```vega
{...}
```
````

---

## Related Files

> For advanced chart patterns and complex visualizations, refer to references below:

- [examples.md](references/examples.md) — Stacked bar, grouped bar, multi-series line, area, heatmap, radar (Vega), word cloud (Vega), and interactive chart examples
