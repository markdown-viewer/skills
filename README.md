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
| 📊 Charts | [vega](vega/SKILL.md) | Data-driven charts with Vega-Lite and Vega | Bar, line, scatter, heatmap, area charts, multi-series analytics |
| 📈 Infographic | [infographic](infographic/SKILL.md) | Beautiful infographics with pre-designed templates | KPI cards, timelines, roadmaps, SWOT, funnels, comparisons |
| 🔀 Diagrams | [mermaid](mermaid/SKILL.md) | Flowcharts, sequence diagrams, state machines, and more | Process flows, API interactions, system architecture |
| 🕸️ Graphs | [graphviz](graphviz/SKILL.md) | Complex directed/undirected graphs with DOT language | Dependency trees, org charts, network topologies |
| 🎨 Canvas | [canvas](canvas/SKILL.md) | Spatial node-based diagrams with free positioning | Mind maps, knowledge graphs, concept maps |
| 🏗️ Architecture | [drawio](drawio/SKILL.md) | Professional Draw.io diagrams with rich shape libraries | Architecture diagrams, network topologies, UML |

### Skill Selection Guide

| Use Case | Recommended Skill |
|----------|-------------------|
| Process flow / workflow | `mermaid` |
| API sequence diagram | `mermaid` |
| Data visualization (bar/line/scatter) | `vega` |
| Quick KPI dashboard | `infographic` |
| Timeline / roadmap | `infographic` |
| SWOT / comparison | `infographic` |
| Complex dependency graph | `graphviz` |
| Mind map / concept map | `canvas` |
| AWS/Azure architecture | `drawio` |
| Pixel-perfect layouts | `drawio` |

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
| Infographic | ` ```infographic ` |
| Graphviz | ` ```dot ` |
| Canvas | ` ```canvas ` |
| Draw.io | ` ```drawio ` |

---

## 🔗 Links

- [Markdown Viewer Extension](https://xicilion.gitbook.io/markdown-viewer-extension/) - The rendering engine behind these skills
- [Agent Skills Format](https://agentskills.io/) - Standard format for AI agent skills
- [Chrome Extension](https://chrome.google.com/webstore/detail/markdown-viewer) - Install for Chrome/Edge
- [Firefox Add-on](https://addons.mozilla.org/firefox/addon/markdown-viewer-extension/) - Install for Firefox
- [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=nicepkg.markdown-viewer) - Install for VS Code

---

## 📄 License

MIT
