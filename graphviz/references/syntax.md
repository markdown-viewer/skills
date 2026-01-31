# Graphviz Syntax Reference

Detailed syntax rules for advanced graph features. Load this when you need specific syntax details.

---

## Node Definition

### Basic Syntax
```dot
digraph G {
    node_id [label="Display Name"];
    "node with space" [label="Displayed"];
}
```

### Node Attributes
```dot
digraph G {
    node_id [
        label="Display Name",
        shape=box,
        style=filled,
        fillcolor="#4A90E2",
        fontcolor=white,
        fontsize=12,
        width=2,
        height=1
    ];
}
```

### Record Nodes (Structured Data)
```dot
digraph G {
    struct [shape=record, label="{name: string|age: int|email: string}"];
    table [shape=record, label="{<f0> id|<f1> name|<f2> value}"];
}
```

---

## Edge Definition

### Basic Syntax
```dot
digraph G {
    A -> B;                    // Simple edge
    A -> B [label="calls"];    // Labeled edge
    A -> {B; C; D};            // One to many
}
```

### Edge Attributes
```dot
digraph G {
    A -> B [
        label="relationship",
        style=dashed,
        color="#FF6B6B",
        penwidth=2,
        arrowhead=normal,
        arrowtail=none,
        dir=both
    ];
}
```

### Edge Styles

| Style | Description |
|-------|-------------|
| `solid` | Regular line (default) |
| `dashed` | Dashed line |
| `dotted` | Dotted line |
| `bold` | Thick line |
| `invis` | Invisible (for layout) |

### Arrow Heads

| Type | Description |
|------|-------------|
| `normal` | Standard arrow (default) |
| `open` | Open arrow tip |
| `none` | No arrow |
| `diamond` | Diamond end |
| `odiamond` | Open diamond |
| `dot` | Dot end |
| `box` | Box end |
| `crow` | Crow's foot (ER diagrams) |
| `vee` | V-shaped |

---

## Layout Control

### Layout Directions
```dot
digraph G {
    rankdir=TB;  // Top to Bottom (default)
    // rankdir=LR;  // Left to Right
    // rankdir=RL;  // Right to Left
    // rankdir=BT;  // Bottom to Top
}
```

### Node Ranking
```dot
digraph G {
    {rank=same; A; B; C;}    // Force same level
    {rank=min; StartNode;}   // Force to top
    {rank=max; EndNode;}     // Force to bottom
    {rank=source; Input;}    // Absolutely first
    {rank=sink; Output;}     // Absolutely last
}
```

### Spacing Control
```dot
digraph G {
    graph [
        nodesep=0.5,     // Horizontal spacing between nodes
        ranksep=1.0,     // Vertical spacing between ranks
        splines=ortho    // Edge routing: ortho|polyline|curved|line
    ];
}
```

### Edge Constraints
```dot
digraph G {
    A -> B [constraint=false];  // Don't affect ranking
    A -> C [minlen=2];          // Minimum edge length
}
```

---

## Subgraph (Clustering)

```dot
digraph G {
    subgraph cluster_backend {
        label="Backend Services";
        style=filled;
        fillcolor="#F0F0F0";
        color="#333333";
        
        API [label="API Gateway"];
        DB [label="Database", shape=cylinder];
        API -> DB;
    }
    
    subgraph cluster_frontend {
        label="Frontend";
        style=filled;
        fillcolor="#F5F5F5";
        
        Client [label="Web Client"];
    }
    
    Client -> API;
}
```

**Note:** Cluster names must start with `cluster_` to render as boxes.

---

## Global Defaults

```dot
digraph G {
    // Default for all nodes
    node [shape=box, style=filled, fillcolor="#3498DB", fontcolor=white];
    
    // Default for all edges
    edge [color="#666666", arrowhead=vee];
    
    // Graph attributes
    graph [rankdir=LR, bgcolor=white];
    
    A -> B -> C;
}
```

---

## Color Palette

| Color | Hex | Usage |
|-------|-----|-------|
| Green | `#2ECC71` | Success, completed |
| Red | `#E74C3C` | Error, critical |
| Orange | `#F39C12` | Warning, action |
| Blue | `#3498DB` | Info, process |
| Gray | `#95A5A6` | Neutral, disabled |
| Purple | `#9B59B6` | Concept, idea |
| Cyan | `#1ABC9C` | Secondary |
| Yellow | `#F1C40F` | Highlight |

---

## Node Shapes

### Common Shapes
| Shape | Description | Usage |
|-------|-------------|-------|
| `box` | Rectangle | Process, action |
| `ellipse` | Ellipse (default) | General node |
| `circle` | Circle | State, event |
| `diamond` | Diamond | Decision |
| `plaintext` | No border | Labels |
| `record` | Structured | Data tables |
| `cylinder` | Cylinder | Database |
| `folder` | Folder | Directory |
| `component` | UML component | Module |
| `house` | House | Root |
| `invhouse` | Inverted house | Leaf |

### HTML Labels
```dot
digraph G {
    node [shape=plaintext];
    A [label=<
        <TABLE BORDER="0" CELLBORDER="1" CELLSPACING="0">
            <TR><TD BGCOLOR="#3498DB"><FONT COLOR="white">Header</FONT></TD></TR>
            <TR><TD>Content</TD></TR>
        </TABLE>
    >];
}
```

---

## Undirected Graphs

```dot
graph G {
    rankdir=LR;
    A -- B -- C;
    B -- D;
}
```

Use `graph` instead of `digraph`, and `--` instead of `->`.

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Nodes not aligned | Use `rank=same` or invisible edges |
| Edges crossing | Try different `splines` or `rankdir` |
| Clusters not showing | Name must start with `cluster_` |
| Labels too long | Use `\n` for line breaks |
| Graph too wide | Switch to `rankdir=TB` |
| Overlapping nodes | Increase `nodesep` or `ranksep` |
