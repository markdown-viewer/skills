---
name: engineering
description: Create professional engineering diagrams using drawio XML format with industry-standard symbols. Best for electrical schematics, P&ID (Piping & Instrumentation), rack diagrams, fault tree analysis, PLC ladder logic, and logic gate diagrams. Built on drawio with engineering-specific stencils. NOT for simple flowcharts (use mermaid) or network topology (use network skill).
author: Engineering diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Engineering Diagram Generator

**Quick Start:** Choose diagram type → Add symbols from stencil library → Connect with appropriate lines → Add labels/annotations → Wrap in ` ```drawio ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```drawio ` code fence. NEVER use ` ```xml ` — it will NOT render as a diagram.

## Critical Rules

> 🔗 **This is a drawio-derived skill.** All structure, layout, and edge routing rules inherit from [drawio SKILL.md](../drawio/SKILL.md). Read the base rules first.

**Engineering-specific additions:**
- Check [stencils/README.md](../drawio/stencils/README.md) for exact symbol names (e.g., `mxgraph.electrical.resistors.resistor_1`)
- Symbol colors: Black(`#000000`) for schematic, Blue(`#0000FF`) for pneumatic, Green(`#00FF00`) for hydraulic

## Engineering Diagram Types

| Type | Purpose | Stencil Library | Example |
|------|---------|-----------------|---------|
| Electrical Schematic | Circuit diagrams, wiring diagrams | `mxgraph.electrical.*` (527 symbols) | [electrical-circuit.md](examples/electrical-circuit.md) |
| P&ID | Process flow, piping & instrumentation | `mxgraph.pid.*` (478 symbols) | [pid-process.md](examples/pid-process.md) |
| Rack Diagram | Data center, server rack layout | `mxgraph.rack.*` (487 symbols) | [rack-datacenter.md](examples/rack-datacenter.md) |
| Logic Gates | Digital logic circuits | `mxgraph.electrical.logic_gates.*` | [logic-gates.md](examples/logic-gates.md) |
| Fault Tree | Fault tree analysis (FTA) | `mxgraph.electrical.logic_gates.*` | [fault-tree.md](examples/fault-tree.md) |
| PLC Ladder | PLC ladder logic diagrams | `mxgraph.electrical.plc_ladder.*` | [plc-ladder.md](examples/plc-ladder.md) |
