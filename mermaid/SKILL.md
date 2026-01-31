---
name: mermaid
description: Create flowcharts, sequence diagrams, state machines, class diagrams, Gantt charts, mindmaps, and more. Best for process flows, API interactions, system architecture, and technical documentation. NOT for data-driven charts (use vega) or quick KPI visuals (use infographic).
auth: Mermaid is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Mermaid Diagram Visualizer

**Quick Start:** Identify diagram type (flowchart/sequence/state/class/ER/gantt/mindmap) → Define nodes with shapes → Connect with arrows → Wrap in ` ```mermaid ` fence. Default: top-to-bottom (`TD`), use `flowchart` over `graph`, Unicode supported.

---

## Critical Syntax Rules

### Rule 1: List Syntax Conflicts
```
❌ [1. Item]     → "Unsupported markdown: list"
✅ [1.Item]      → Remove space after period
✅ [① Item]      → Use circled numbers ①②③④⑤⑥⑦⑧⑨⑩
✅ [(1) Item]    → Use parentheses
```

### Rule 2: Subgraph Naming
```
❌ subgraph AI Agent Core    → Space without quotes
✅ subgraph agent["AI Agent Core"]  → ID with display name
✅ subgraph agent            → Simple ID only
```

### Rule 3: Node References in Subgraphs
```
❌ Title --> AI Agent Core   → Reference display name
✅ Title --> agent           → Reference subgraph ID
```

### Rule 4: Special Characters in Node Text
```
✅ ["Text with spaces"]       → Quotes for spaces
✅ Use 『』 instead of ""     → Avoid quotation marks
✅ Use 「」 instead of ()     → Avoid parentheses
```

### Rule 5: Use flowchart over graph
```
❌ graph TD      → Outdated
✅ flowchart TD  → Supports subgraph directions, more features
```

---

## Common Pitfalls

| Issue | Solution |
|-------|----------|
| Diagram won't render | Check unmatched brackets, quotes |
| List syntax error | `[1.Item]` not `[1. Item]` |
| Subgraph reference fails | Use ID not display name |
| Too crowded | Split into multiple diagrams |
| Crossing connections | Use different layout direction or invisible edges `~~~` |

---

## Output Format

````markdown
```mermaid
[diagram code]
```
````

---

## Related Files

> For diagram-specific syntax and advanced features, refer to references below:

- [syntax.md](references/syntax.md) — Detailed syntax for all 14+ diagram types: flowchart shapes, sequence actors, class relationships, state transitions, ER cardinality, Gantt tasks, and more
