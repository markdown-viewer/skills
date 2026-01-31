# Vega Examples Reference

Complete examples for various chart types. Load this when you need specific chart patterns.

---

## Vega-Lite Examples

### Horizontal Bar (Sorted)
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"item": "Alpha", "value": 28},
      {"item": "Beta", "value": 55},
      {"item": "Gamma", "value": 43}
    ]
  },
  "mark": "bar",
  "encoding": {
    "y": {"field": "item", "type": "nominal", "sort": "-x"},
    "x": {"field": "value", "type": "quantitative"}
  }
}
```

### Stacked Bar
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"category": "A", "group": "x", "value": 10},
      {"category": "A", "group": "y", "value": 20},
      {"category": "B", "group": "x", "value": 15},
      {"category": "B", "group": "y", "value": 25}
    ]
  },
  "mark": "bar",
  "encoding": {
    "x": {"field": "category", "type": "nominal"},
    "y": {"field": "value", "type": "quantitative"},
    "color": {"field": "group", "type": "nominal"}
  }
}
```

### Multi-series Line
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"month": 1, "series": "A", "value": 28},
      {"month": 2, "series": "A", "value": 55},
      {"month": 1, "series": "B", "value": 35},
      {"month": 2, "series": "B", "value": 48}
    ]
  },
  "mark": "line",
  "encoding": {
    "x": {"field": "month", "type": "ordinal"},
    "y": {"field": "value", "type": "quantitative"},
    "color": {"field": "series", "type": "nominal"}
  }
}
```

### Donut Chart
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {"values": [
    {"category": "A", "value": 30},
    {"category": "B", "value": 45},
    {"category": "C", "value": 25}
  ]},
  "mark": {"type": "arc", "innerRadius": 50},
  "encoding": {
    "theta": {"field": "value", "type": "quantitative"},
    "color": {"field": "category", "type": "nominal"}
  }
}
```

### Heatmap
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"x": "A", "y": "1", "value": 10},
      {"x": "A", "y": "2", "value": 20},
      {"x": "B", "y": "1", "value": 25},
      {"x": "B", "y": "2", "value": 30}
    ]
  },
  "mark": "rect",
  "encoding": {
    "x": {"field": "x", "type": "nominal"},
    "y": {"field": "y", "type": "nominal"},
    "color": {"field": "value", "type": "quantitative"}
  }
}
```

### Area Chart
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"x": 1, "y": 10},
      {"x": 2, "y": 30},
      {"x": 3, "y": 20}
    ]
  },
  "mark": "area",
  "encoding": {
    "x": {"field": "x", "type": "quantitative"},
    "y": {"field": "y", "type": "quantitative"}
  }
}
```

### Histogram
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"value": 12}, {"value": 15}, {"value": 18},
      {"value": 22}, {"value": 25}, {"value": 28}
    ]
  },
  "mark": "bar",
  "encoding": {
    "x": {"bin": {"maxbins": 10}, "field": "value", "type": "quantitative"},
    "y": {"aggregate": "count", "type": "quantitative"}
  }
}
```

### Faceting (Small Multiples)
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"x": 1, "y": 10, "cat": "A"},
      {"x": 2, "y": 20, "cat": "A"},
      {"x": 1, "y": 15, "cat": "B"},
      {"x": 2, "y": 25, "cat": "B"}
    ]
  },
  "facet": {"field": "cat", "type": "nominal", "columns": 2},
  "spec": {
    "mark": "point",
    "encoding": {
      "x": {"field": "x", "type": "quantitative"},
      "y": {"field": "y", "type": "quantitative"}
    }
  }
}
```

### Layered Line + Point
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {"values": [{"x": 1, "y": 10}, {"x": 2, "y": 20}]},
  "layer": [
    {"mark": "line"},
    {"mark": "point"}
  ],
  "encoding": {
    "x": {"field": "x", "type": "quantitative"},
    "y": {"field": "y", "type": "quantitative"}
  }
}
```

### Dual Axis
```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {
    "values": [
      {"month": "Jan", "revenue": 120, "growth": 5},
      {"month": "Feb", "revenue": 150, "growth": 8}
    ]
  },
  "encoding": {"x": {"field": "month", "type": "ordinal"}},
  "layer": [
    {
      "mark": "bar",
      "encoding": {"y": {"field": "revenue", "type": "quantitative"}}
    },
    {
      "mark": {"type": "line", "color": "red"},
      "encoding": {"y": {"field": "growth", "type": "quantitative", "axis": {"orient": "right"}}}
    }
  ],
  "resolve": {"scale": {"y": "independent"}}
}
```

---

## Color Schemes

### Sequential
```json
"scale": {"scheme": "blues"}
"scale": {"scheme": "greens"}
"scale": {"scheme": "viridis"}
"scale": {"scheme": "plasma"}
```

### Diverging
```json
"scale": {"scheme": "redblue"}
"scale": {"scheme": "redyellowblue"}
```

### Categorical
```json
"scale": {"scheme": "category10"}
"scale": {"scheme": "set1"}
```

---

## Data Transformation

### Filter
```json
"transform": [{"filter": "datum.value > 100"}]
```

### Calculate
```json
"transform": [{"calculate": "datum.sales * 1.1", "as": "projected"}]
```

### Aggregate
```json
"transform": [{"aggregate": [{"op": "sum", "field": "value", "as": "total"}], "groupby": ["category"]}]
```

---

## Vega Advanced Examples

### Radar Chart
```vega
{
  "$schema": "https://vega.github.io/schema/vega/v6.json",
  "width": 400, "height": 400, "padding": 40,
  "autosize": {"type": "none", "contains": "padding"},
  "signals": [{"name": "radius", "update": "width / 2"}],
  "data": [
    {
      "name": "table",
      "values": [
        {"dim": "A", "val": 85, "cat": "X"},
        {"dim": "B", "val": 72, "cat": "X"},
        {"dim": "C", "val": 90, "cat": "X"},
        {"dim": "A", "val": 70, "cat": "Y"},
        {"dim": "B", "val": 88, "cat": "Y"},
        {"dim": "C", "val": 75, "cat": "Y"}
      ]
    }
  ],
  "scales": [
    {"name": "angular", "type": "point", "range": {"signal": "[-PI, PI]"}, "padding": 0.5, "domain": {"data": "table", "field": "dim"}},
    {"name": "radial", "type": "linear", "range": {"signal": "[0, radius]"}, "zero": true, "domain": [0, 100]},
    {"name": "color", "type": "ordinal", "domain": {"data": "table", "field": "cat"}, "range": ["#3b82f6", "#f59e0b"]}
  ],
  "encode": {"enter": {"x": {"signal": "radius"}, "y": {"signal": "radius"}}},
  "marks": [
    {
      "type": "group",
      "from": {"facet": {"data": "table", "name": "facet", "groupby": ["cat"]}},
      "marks": [
        {
          "type": "line",
          "from": {"data": "facet"},
          "encode": {
            "enter": {
              "interpolate": {"value": "linear-closed"},
              "x": {"signal": "scale('radial', datum.val) * cos(scale('angular', datum.dim))"},
              "y": {"signal": "scale('radial', datum.val) * sin(scale('angular', datum.dim))"},
              "stroke": {"scale": "color", "field": "cat"},
              "strokeWidth": {"value": 2},
              "fill": {"scale": "color", "field": "cat"},
              "fillOpacity": {"value": 0.1}
            }
          }
        }
      ]
    }
  ]
}
```

### Word Cloud
```vega
{
  "$schema": "https://vega.github.io/schema/vega/v6.json",
  "width": 500, "height": 300,
  "data": [
    {
      "name": "table",
      "values": [
        {"word": "JavaScript", "count": 85},
        {"word": "Python", "count": 78},
        {"word": "TypeScript", "count": 65},
        {"word": "React", "count": 58},
        {"word": "Node.js", "count": 52}
      ],
      "transform": [
        {"type": "wordcloud", "size": [500, 300], "text": {"field": "word"}, "fontSize": {"field": "count"}, "fontSizeRange": [16, 60], "padding": 2}
      ]
    }
  ],
  "scales": [{"name": "color", "type": "ordinal", "range": ["#3b82f6", "#10b981", "#f59e0b", "#ef4444", "#8b5cf6"]}],
  "marks": [
    {
      "type": "text",
      "from": {"data": "table"},
      "encode": {
        "enter": {
          "text": {"field": "word"},
          "x": {"field": "x"}, "y": {"field": "y"},
          "angle": {"field": "angle"},
          "fontSize": {"field": "fontSize"},
          "fill": {"scale": "color", "field": "word"},
          "align": {"value": "center"}
        }
      }
    }
  ]
}
```

---

## Formatting Reference

### Numbers
```json
"format": ",.0f"      // Thousands: 1,234
"format": "$.2f"      // Currency: $12.34
"format": ".1%"       // Percent: 12.3%
```

### Dates
```json
"format": "%Y-%m-%d"  // 2024-01-15
"format": "%b %Y"     // Jan 2024
```

### Tooltips
```json
"tooltip": [
  {"field": "category", "type": "nominal"},
  {"field": "value", "type": "quantitative", "format": ",.0f"}
]
```
