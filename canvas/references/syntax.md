# Canvas Syntax Reference

Complete attribute reference for JSON Canvas diagrams.

---

## Node Attributes

| Attribute | Required | Type | Description |
|-----------|----------|------|-------------|
| `id` | Yes | string | Unique identifier (alphanumeric, hyphen, underscore) |
| `type` | Yes | string | `text`, `file`, `link`, or `group` |
| `x` | Yes | integer | X position in pixels |
| `y` | Yes | integer | Y position in pixels |
| `width` | Yes | integer | Width in pixels |
| `height` | Yes | integer | Height in pixels |
| `text` | Conditional | string | Text content (required for text nodes) |
| `file` | Conditional | string | File path (required for file nodes) |
| `url` | Conditional | string | URL (required for link nodes) |
| `label` | Conditional | string | Label text (for group nodes) |
| `color` | No | string | Color preset `"1"`-`"6"` or hex `"#RRGGBB"` |

---

## Node Type Examples

### Text Node
```json
{
  "id": "node1",
  "type": "text",
  "text": "Your text content here",
  "x": 100,
  "y": 100,
  "width": 200,
  "height": 100
}
```
**Supports:** Multi-line text (use `\n`), Unicode characters, emojis

### File Node
```json
{
  "id": "file1",
  "type": "file",
  "file": "path/to/document.md",
  "x": 100,
  "y": 100,
  "width": 160,
  "height": 60
}
```

### Link Node
```json
{
  "id": "link1",
  "type": "link",
  "url": "https://example.com",
  "x": 100,
  "y": 100,
  "width": 160,
  "height": 60
}
```

### Group Node
```json
{
  "id": "group1",
  "type": "group",
  "label": "Group Title",
  "x": 0,
  "y": 0,
  "width": 600,
  "height": 400,
  "color": "5"
}
```
**Note:** Group nodes are visual containers; position child nodes within bounds.

---

## Edge Attributes

| Attribute | Required | Default | Description |
|-----------|----------|---------|-------------|
| `id` | Yes | - | Unique identifier |
| `fromNode` | Yes | - | Source node ID |
| `toNode` | Yes | - | Target node ID |
| `fromSide` | No | - | `top`, `right`, `bottom`, `left` |
| `toSide` | No | - | `top`, `right`, `bottom`, `left` |
| `fromEnd` | No | `none` | `none` or `arrow` |
| `toEnd` | No | `arrow` | `none` or `arrow` |
| `label` | No | - | Edge label text |
| `color` | No | - | Color preset `"1"`-`"6"` or hex |

---

## Edge Type Examples

### Simple Connection (Directional)
```json
{
  "id": "edge1",
  "fromNode": "n1",
  "fromSide": "right",
  "toNode": "n2",
  "toSide": "left",
  "toEnd": "arrow"
}
```

### Labeled Edge
```json
{
  "id": "edge2",
  "fromNode": "n1",
  "fromSide": "bottom",
  "toNode": "n3",
  "toSide": "top",
  "label": "depends on",
  "color": "2"
}
```

### Bidirectional Edge
```json
{
  "id": "edge3",
  "fromNode": "n1",
  "toNode": "n2",
  "fromEnd": "arrow",
  "toEnd": "arrow",
  "label": "communicates"
}
```

---

## Color Reference

### Presets
| Value | Color | Usage |
|-------|-------|-------|
| `"1"` | Red | Warnings, blockers, critical items |
| `"2"` | Orange | Actions, processes, important items |
| `"3"` | Yellow | Questions, notes, considerations |
| `"4"` | Green | Success, completed, positive outcomes |
| `"5"` | Cyan | Information, details, neutral items |
| `"6"` | Purple | Concepts, ideas, abstract items |

### Custom Colors (Hex)
```json
"color": "#FF6B6B"
```
Use uppercase hex format.

---

## Coordinate System

```
(0,0) ───────────────── (+X)
  │
  │   Node 1 (100,50)
  │   ┌─────────────┐
  │   │  Example    │
  │   └─────────────┘
  │           │
  │           │ edge
  │           ▼
  │   ┌─────────────┐
  │   │  Node 2     │
  │   │  (100,200)  │
  │   └─────────────┘
  │
(+Y)
```

**Rules:**
- Origin (0,0) at top-left
- X increases to the right
- Y increases downward
- No negative coordinates allowed

---

## Layout Patterns

### Linear Flow (Vertical)
```canvas
{
  "nodes": [
    {"id": "n1", "type": "text", "text": "Start", "x": 100, "y": 50, "width": 100, "height": 50},
    {"id": "n2", "type": "text", "text": "Process", "x": 100, "y": 150, "width": 100, "height": 50},
    {"id": "n3", "type": "text", "text": "End", "x": 100, "y": 250, "width": 100, "height": 50}
  ],
  "edges": [
    {"id": "e1", "fromNode": "n1", "toNode": "n2", "fromSide": "bottom", "toSide": "top"},
    {"id": "e2", "fromNode": "n2", "toNode": "n3", "fromSide": "bottom", "toSide": "top"}
  ]
}
```

### Horizontal Flow
```canvas
{
  "nodes": [
    {"id": "n1", "type": "text", "text": "Input", "x": 50, "y": 100, "width": 100, "height": 50},
    {"id": "n2", "type": "text", "text": "Process", "x": 200, "y": 100, "width": 100, "height": 50},
    {"id": "n3", "type": "text", "text": "Output", "x": 350, "y": 100, "width": 100, "height": 50}
  ],
  "edges": [
    {"id": "e1", "fromNode": "n1", "toNode": "n2", "fromSide": "right", "toSide": "left"},
    {"id": "e2", "fromNode": "n2", "toNode": "n3", "fromSide": "right", "toSide": "left"}
  ]
}
```

### Tree Structure
```canvas
{
  "nodes": [
    {"id": "root", "type": "text", "text": "Root", "x": 200, "y": 20, "width": 100, "height": 50},
    {"id": "c1", "type": "text", "text": "Child 1", "x": 50, "y": 120, "width": 100, "height": 50},
    {"id": "c2", "type": "text", "text": "Child 2", "x": 200, "y": 120, "width": 100, "height": 50},
    {"id": "c3", "type": "text", "text": "Child 3", "x": 350, "y": 120, "width": 100, "height": 50},
    {"id": "g1", "type": "text", "text": "Grandchild", "x": 50, "y": 220, "width": 100, "height": 50}
  ],
  "edges": [
    {"id": "e1", "fromNode": "root", "fromSide": "bottom", "toNode": "c1", "toSide": "top"},
    {"id": "e2", "fromNode": "root", "fromSide": "bottom", "toNode": "c2", "toSide": "top"},
    {"id": "e3", "fromNode": "root", "fromSide": "bottom", "toNode": "c3", "toSide": "top"},
    {"id": "e4", "fromNode": "c1", "fromSide": "bottom", "toNode": "g1", "toSide": "top"}
  ]
}
```

### Radial Mind Map
```canvas
{
  "nodes": [
    {"id": "center", "type": "text", "text": "Central Topic", "x": 200, "y": 200, "width": 140, "height": 60, "color": "4"},
    {"id": "n1", "type": "text", "text": "North", "x": 220, "y": 50, "width": 100, "height": 50},
    {"id": "n2", "type": "text", "text": "East", "x": 380, "y": 210, "width": 100, "height": 50},
    {"id": "n3", "type": "text", "text": "South", "x": 220, "y": 350, "width": 100, "height": 50},
    {"id": "n4", "type": "text", "text": "West", "x": 50, "y": 210, "width": 100, "height": 50}
  ],
  "edges": [
    {"id": "e1", "fromNode": "center", "toNode": "n1", "fromSide": "top", "toSide": "bottom"},
    {"id": "e2", "fromNode": "center", "toNode": "n2", "fromSide": "right", "toSide": "left"},
    {"id": "e3", "fromNode": "center", "toNode": "n3", "fromSide": "bottom", "toSide": "top"},
    {"id": "e4", "fromNode": "center", "toNode": "n4", "fromSide": "left", "toSide": "right"}
  ]
}
```

---

## ID Rules

IDs must be:
- **Unique** across all nodes and edges
- **Alphanumeric** (a-z, A-Z, 0-9)
- **Hyphens and underscores** allowed
- **8-12 characters** recommended
- **Readable** (use semantic names when possible)

### Good Examples
```
"n1", "node-1", "start_node", "process_a"
```

### Avoid
```
"Node 1" (space), "node@1" (special char), "中文" (non-ASCII)
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Nodes overlapping | Increase spacing, adjust coordinates |
| Edges not visible | Check node IDs match, verify sides |
| Layout looks messy | Use groups, increase canvas size |
| Nodes too crowded | Split into multiple diagrams |
| IDs invalid | Use only alphanumeric, hyphen, underscore |
| JSON syntax error | Validate quotes, commas, brackets |
