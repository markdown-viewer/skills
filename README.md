# Markdown Viewer Agent Skills

Opinionated skills for AI coding agents to create stunning diagrams and visualizations directly in Markdown. These skills extend agent capabilities across diagram generation, data visualization, and technical documentation.

Skills follow the [Agent Skills](https://agentskills.io/) format.

---

## 🧭 Quick Navigation

**[🚀 Installation](#-installation)** • **[📚 Available Skills](#-available-skills)** • **[📖 Skill Structure](#-skill-structure)** • **[🔗 Links](#-links)**

---

## 🚀 Installation

### Quick Install (Recommended)

```bash
npx skills add markdown-viewer/skills
```

This method works with multiple AI coding agents (Claude Code, Codex, Cursor, etc.)

### Manual Installation

**For Claude Code (Manual)**
```bash
cp -r skills/<skill-name> ~/.claude/skills/
```

**For claude.ai**

Add skills to project knowledge or paste SKILL.md contents into the conversation.

**For GitHub Copilot / VS Code**

Skills are automatically detected when placed in `.github/skills/` directory.

---

## 📚 Available Skills

| Category | Skill | Description | Best For |
|----------|-------|-------------|----------|
| 🔀 Flowcharts | [mermaid](mermaid/SKILL.md) | Flowcharts, sequence diagrams, state machines, Gantt charts | Process flows, API interactions, simple architecture |
| 📊 Data Charts | [vega](vega/SKILL.md) | Data-driven charts with Vega-Lite and Vega | Bar, line, scatter, heatmap, area charts, analytics |
| 📈 Infographic | [infographic](infographic/SKILL.md) | Pre-designed templates for quick visual impact | KPI cards, timelines, roadmaps, SWOT, funnels |
| 🎨 Mind Map | [canvas](canvas/SKILL.md) | Spatial node-based diagrams with free positioning | Mind maps, knowledge graphs, concept maps |
| 🕸️ Dependency Graph | [graphviz](graphviz/SKILL.md) | Complex directed/undirected graphs with DOT language | Dependency trees, module relationships, org charts |
| 🏛️ Layered Architecture | [architecture](architecture/SKILL.md) | HTML/CSS layered architecture with color-coded layers | System architecture, microservices, enterprise apps |
| 🏗️ drawio (General) | [drawio](drawio/SKILL.md) | General-purpose drawio with 8900+ stencils | Custom diagrams, pixel-perfect layouts |
| 🌐 Network Topology | [network](network/SKILL.md) | Network diagrams with Cisco/vendor icons (drawio based) | LAN/WAN, enterprise networks, cloud infrastructure |
| 📐 UML Diagrams | [uml](uml/SKILL.md) | UML diagrams for software modeling (drawio based) | Class, sequence, activity, component diagrams |

### Skill Selection Guide

| Use Case | Recommended Skill | Reason |
|----------|-------------------|--------|
| Process flow / workflow | `mermaid` | Simple text-based syntax |
| API sequence diagram | `mermaid` | Built-in sequence diagram support |
| State machine | `mermaid` | Native state diagram syntax |
| Bar / line / scatter chart | `vega` | Data-driven visualization |
| Heatmap / multi-series | `vega` | Statistical analysis |
| KPI dashboard / metrics | `infographic` | Pre-designed card templates |
| Timeline / roadmap | `infographic` | Built-in timeline templates |
| SWOT / comparison | `infographic` | Structured comparison templates |
| Mind map / brainstorm | `canvas` | Free spatial positioning |
| Knowledge graph | `canvas` | Node-edge with coordinates |
| Module dependencies | `graphviz` | Complex edge routing |
| Package relationships | `graphviz` | Hierarchical layouts |
| System layers (User→App→Data→Infra) | `architecture` | Color-coded layer templates |
| Microservices architecture | `architecture` | Grid-based component layout |
| Custom diagram with icons | `drawio` | 8900+ stencils available |
| Pixel-perfect positioning | `drawio` | Precise x/y coordinates |
| Network topology (LAN/WAN) | `network` | Cisco/vendor device icons |
| Cloud infrastructure | `network` | AWS/Azure/GCP shapes |
| UML class diagram | `uml` | Standard UML notation |
| UML sequence / activity | `uml` | UML lifeline and flow shapes |

---

## 📖 Skill Structure

Each skill contains:

```
skills/
├── <skill-name>/
│   └── SKILL.md      # Detailed instructions for the agent (with YAML frontmatter)
└── README.md         # This file
```

### SKILL.md Format

Each `SKILL.md` includes:
- **YAML frontmatter** with `name`, `description`, and `auth` fields
- **Quick Start** guide for immediate usage
- **Critical Syntax Rules** to avoid common errors
- **Examples** and templates for reference

---

## 🎯 Usage Tips

### For AI Agents

When the agent receives a request involving diagrams or visualizations:

1. **Identify the diagram type** from user requirements
2. **Read the appropriate SKILL.md** for detailed instructions
3. **Follow the syntax rules** carefully to avoid render failures
4. **Use the code fence** specified in each skill (e.g., ` ```mermaid `, ` ```vega-lite `, ` ```dot `)

### Code Fence Reference

| Skill | Code Fence |
|-------|------------|
| Mermaid | ` ```mermaid ` |
| Vega-Lite | ` ```vega-lite ` |
| Vega | ` ```vega ` |
| drawio | ` ```drawio ` |
| Architecture | (no fence, use raw HTML) |
| Canvas | ` ```canvas ` |
| Infographic | ` ```infographic ` |
| Graphviz | ` ```dot ` |
| Network | ` ```drawio ` |
| UML | ` ```drawio ` |

---

## 🔗 Links

- [Markdown Viewer Extension](https://xicilion.gitbook.io/markdown-viewer-extension/) - The rendering engine behind these skills
- [Agent Skills Format](https://agentskills.io/) - Standard format for AI agent skills
- [Chrome Extension](https://chromewebstore.google.com/detail/markdown-viewer/jekhhoflgcfoikceikgeenibinpojaoi) - Install for Chrome/Edge
- [Firefox Add-on](https://addons.mozilla.org/firefox/addon/markdown-viewer-extension/) - Install for Firefox
- [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=xicilion.markdown-viewer-extension) - Install for VS Code

---

## 📄 License

MIT
