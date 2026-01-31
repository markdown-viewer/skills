---
name: graphviz
description: Create complex directed/undirected graphs with precise layout control. Best for dependency trees, org charts, network topologies, and module relationships. Use when you need fine-grained edge routing or hierarchical layouts with many levels. NOT for simple flowcharts (use mermaid) or data charts (use vega).
auth: Graphviz is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Graphviz DOT Diagram Generator

> **Important:** Use ` ```dot ` as the code fence identifier, NOT ` ```graphviz `.

**Quick Start:** Choose `digraph` (directed) or `graph` (undirected) → Define nodes with attributes (shape, color, label) → Connect with `->` or `--` → Set layout (rankdir, spacing) → Wrap in ` ```dot ` fence. Default: top-to-bottom (`rankdir=TB`), cluster names must start with `cluster_`, use semicolons.

---

## Critical Syntax Rules

### Rule 1: Cluster Naming
```
❌ subgraph backend { }      → Won't render as box
✅ subgraph cluster_backend { }  → Must start with cluster_
```

### Rule 2: Node IDs with Spaces
```
❌ API Gateway [label="API"];    → Invalid ID
✅ "API Gateway" [label="API"];  → Quote the ID
✅ api_gateway [label="API Gateway"];  → Use underscore ID
```

### Rule 3: Edge Syntax Difference
```
digraph: A -> B;   → Directed arrow
graph:   A -- B;   → Undirected line
```

### Rule 4: Attribute Syntax
```
❌ node [shape=box color=red]    → Missing comma
✅ node [shape=box, color=red];  → Comma separated
```

### Rule 5: HTML Labels
```
✅ shape=plaintext for HTML labels
✅ Use < > not " " for HTML content
```

---

## Common Pitfalls

| Issue | Solution |
|-------|----------|
| Nodes overlapping | Increase `nodesep` and `ranksep` |
| Poor layout | Change `rankdir` or add `{rank=same}` |
| Edges crossing | Use `splines=ortho` or adjust node order |
| Cluster not showing | Name must start with `cluster_` |
| Label not displaying | Check quote escaping |

---

## Output Format

````markdown
```dot
digraph G {
    [diagram code]
}
```
````

---

## Related Files

> For advanced layout control and complex styling, refer to references below:

- [syntax.md](references/syntax.md) — Layout control (rankdir, splines, rank), HTML labels, edge styles, cluster subgraphs, and record-based nodes
