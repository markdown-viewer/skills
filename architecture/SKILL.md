---
name: architecture
description: Create layered architecture diagrams using HTML/CSS templates with color-coded layers and grid layouts. Best for visualizing system layers (User→Application→Data→Infrastructure), microservices architecture, and enterprise application design. NOT for pixel-perfect custom diagrams (use drawio), software modeling (use uml), or data visualization (use vega).
metadata:
  author: Architecture Diagram Generator is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Architecture Diagram Generator

**Quick Start:** Create HTML structure with flexible layout (single/double/triple column) → Define CSS styles for layers and grids → Add content with categorized panels → Use semantic colors for different layers.

## Critical Rules

### Rule 1: Direct HTML Embedding
**IMPORTANT**: Write architecture diagrams as direct HTML in Markdown. **NEVER** use code blocks (` ```html `). The HTML should be embedded directly in the document without any fencing.

### Rule 2: No Empty Lines in HTML Structure
**CRITICAL**: Do NOT add any empty lines within the HTML architecture diagram structure. Keep the entire HTML block continuous to prevent parsing errors.

### Rule 3: Incremental Creation Approach
**RECOMMENDED**: Create architecture diagrams in multiple steps:
1. **First**: Create the overall framework (wrapper, sidebars, main structure) and define all CSS styles
2. **Second**: Add layer containers with titles
3. **Third**: Fill in components layer by layer
4. **Fourth**: Add detailed content and refinements

### Rule 4: Flexible Layout Structure
Architecture diagrams can use flexible layouts based on complexity:
- **Single Column**: Main content only (for simple architectures)
- **Two Column**: Main content + one sidebar (left or right)
- **Three Column**: Full layout with both sidebars (for complex systems)
  - **Left Sidebar**: Supporting systems (monitoring, operations, analytics)
  - **Main Content**: Core architecture layers (user, application, data, infrastructure)
  - **Right Sidebar**: Cross-cutting concerns (security, compliance, governance)

### Rule 5: Layer-Based Organization
Each layer should have:
- Clear semantic meaning (User, Application, AI/Logic, Data, Infrastructure)
- Consistent color coding
- Grid-based layout for components
- Appropriate nesting for sub-components

### Rule 6: Color Semantics
Use consistent semantic meaning for layers — the exact color palette varies by style (see examples). The standard semantic mapping:
- **User Layer** — user-facing interfaces and clients
- **Application Layer** — business logic and API services
- **AI/Logic Layer** — intelligence, rules, processing engines
- **Data Layer** — databases, caches, storage
- **Infrastructure Layer** — containers, networking, DevOps
- **External Services** — third-party APIs, cloud services (typically dashed border)

## Style Examples

Choose a visual style that matches your project's tone and audience. Each example contains a complete, copy-ready HTML template.

| # | Style | File | Suitable For |
|---|---|---|---|
| 1 | **Steel Blue** | [styles/steel-blue.md](styles/steel-blue.md) | Consulting reports, banking/finance, government projects, RFP proposals |
| 2 | **Ember Warm** | [styles/ember-warm.md](styles/ember-warm.md) | Retail/e-commerce, education platforms, lifestyle brands, cultural institutions |
| 3 | **Neon Dark** | [styles/neon-dark.md](styles/neon-dark.md) | Tech talks, developer conferences, gaming platforms, cybersecurity dashboards |
| 4 | **Stark Block** | [styles/stark-block.md](styles/stark-block.md) | Creative studios, education platforms, indie developers, tech blogs |
| 5 | **Ocean Teal** | [styles/ocean-teal.md](styles/ocean-teal.md) | Travel platforms, logistics/shipping, green tech, weather/ocean projects |
| 6 | **Dusk Glow** | [styles/dusk-glow.md](styles/dusk-glow.md) | Social media, entertainment platforms, martech, content creation tools |
| 7 | **Rose Bloom** | [styles/rose-bloom.md](styles/rose-bloom.md) | Fashion/beauty, luxury brands, wedding platforms, premium memberships |
| 8 | **Sage Forest** | [styles/sage-forest.md](styles/sage-forest.md) | Healthcare, agritech, clean energy, sustainability, bioinformatics |
| 9 | **Frost Clean** | [styles/frost-clean.md](styles/frost-clean.md) | Design tools, developer docs, API references, minimalist SaaS |
| 10 | **Indigo Deep** | [styles/indigo-deep.md](styles/indigo-deep.md) | Brand-consistent systems, enterprise white papers, internal platforms |
| 11 | **Pastel Mix** | [styles/pastel-mix.md](styles/pastel-mix.md) | SaaS products, startups, general tech architecture, product docs |
| 12 | **Slate Dark** | [styles/slate-dark.md](styles/slate-dark.md) | Enterprise dark mode, internal tools, developer dashboards |

## Layout Examples

Choose a layout structure that fits your architecture's complexity. Layouts use wireframe style (no colors) to focus on structural patterns. Combine any layout with any style above.

| # | Layout | File | Best For |
|---|---|---|---|
| 1 | **Three-Column** | [layouts/three-column.md](layouts/three-column.md) | Complex systems with cross-cutting concerns and monitoring sidebars |
| 2 | **Single Stack** | [layouts/single-stack.md](layouts/single-stack.md) | Simple services, microservice detail views, focused documentation |
| 3 | **Left Sidebar** | [layouts/left-sidebar.md](layouts/left-sidebar.md) | Systems with operations/monitoring emphasis, DevOps-centric views |
| 4 | **Right Sidebar** | [layouts/right-sidebar.md](layouts/right-sidebar.md) | Systems with security/compliance emphasis, governance-focused views |
| 5 | **Pipeline** | [layouts/pipeline.md](layouts/pipeline.md) | Data pipelines, CI/CD flows, ETL processes, horizontal stage-based flows |
| 6 | **Two-Column Split** | [layouts/two-column-split.md](layouts/two-column-split.md) | Before/after comparisons, dual-system views, migration architecture |
| 7 | **Dashboard** | [layouts/dashboard.md](layouts/dashboard.md) | System overviews with KPIs, monitoring dashboards, executive summaries |
| 8 | **Grid Catalog** | [layouts/grid-catalog.md](layouts/grid-catalog.md) | Service catalogs, component libraries, equal-weight microservices |
| 9 | **Banner + Center** | [layouts/banner-center.md](layouts/banner-center.md) | Gateway-centric architectures, user-facing systems with shared infrastructure |
| 10 | **Nested Containers** | [layouts/nested-containers.md](layouts/nested-containers.md) | Cloud deployments, VPC/network topology, environment isolation |
| 11 | **Layer Layouts** | [layouts/layer-layouts.md](layouts/layer-layouts.md) | Per-layer layout patterns: grid, sub-group, product group, KPI, vertical stack, zones, inline pipeline, mixed width |
| 12 | **Connectors** | [layouts/connectors.md](layouts/connectors.md) | SVG overlay connectors between components: solid/dashed lines, arrows, labels, curved & orthogonal paths |

## Advanced Features

**NOTE**: These advanced components require additional CSS styles. Add these to your `<style scoped>` section:

```css
.arch-product-group { display: flex; gap: 10px; }
.arch-product { flex: 1; border-radius: 8px; padding: 10px; background: rgba(255, 255, 255, 0.6); border: 1px dashed #d97706; }
.arch-product-title { font-size: 12px; font-weight: bold; color: #92400e; margin-bottom: 8px; text-align: center; }
.arch-subgroup { display: flex; gap: 8px; margin-top: 8px; }
.arch-subgroup-box { flex: 1; border-radius: 6px; padding: 8px; background: rgba(255, 255, 255, 0.5); border: 1px solid rgba(0, 0, 0, 0.08); }
.arch-subgroup-title { font-size: 10px; font-weight: bold; color: #374151; text-align: center; margin-bottom: 6px; }
.arch-user-types { display: flex; gap: 4px; justify-content: center; margin-top: 6px; }
.arch-user-tag { font-size: 9px; padding: 2px 6px; border-radius: 10px; background: rgba(59, 130, 246, 0.15); color: #1d4ed8; }
/* SVG connector lines between components */
.arch-conn { stroke: #94a3b8; stroke-width: 1.5; fill: none; }
.arch-conn-dashed { stroke: #94a3b8; stroke-width: 1.5; fill: none; stroke-dasharray: 6 4; }
.arch-conn-label { font-size: 9px; fill: #64748b; font-family: sans-serif; }
```

### Custom Product Groups
For complex applications with multiple products/modules:

```html
<div class="arch-product-group">
  <div class="arch-product">
    <div class="arch-product-title">🎯 Product A</div>
    <div class="arch-grid arch-grid-2">
      <div class="arch-box">Feature 1<br><small>Description</small></div>
      <div class="arch-box highlight">Feature 2<br><small>Key Feature</small></div>
    </div>
  </div>
  <div class="arch-product">
    <div class="arch-product-title">📊 Product B</div>
    <div class="arch-grid arch-grid-2">
      <div class="arch-box">Feature 3<br><small>Description</small></div>
      <div class="arch-box">Feature 4<br><small>Description</small></div>
    </div>
  </div>
</div>
```

### Sub-grouped Components
For detailed breakdowns within layers:

```html
<div class="arch-subgroup">
  <div class="arch-subgroup-box">
    <div class="arch-subgroup-title">Component Group A</div>
    <div class="arch-grid arch-grid-3">
      <div class="arch-box tech">Service 1<br><small>Details</small></div>
      <div class="arch-box tech">Service 2<br><small>Details</small></div>
      <div class="arch-box tech">Service 3<br><small>Details</small></div>
    </div>
  </div>
  <div class="arch-subgroup-box">
    <div class="arch-subgroup-title">Component Group B</div>
    <div class="arch-grid arch-grid-2">
      <div class="arch-box tech">Service 4<br><small>Details</small></div>
      <div class="arch-box tech">Service 5<br><small>Details</small></div>
    </div>
  </div>
</div>
```

### User Types/Tags

```html
<div class="arch-user-types">
  <span class="arch-user-tag">Admin Users</span>
  <span class="arch-user-tag">End Users</span>
  <span class="arch-user-tag">API Clients</span>
  <span class="arch-user-tag">Partners</span>
</div>
```

### Metrics and KPIs

```html
<div class="arch-sidebar-item metric">99.9% Uptime</div>
<div class="arch-sidebar-item metric">&lt;200ms Response</div>
<div class="arch-sidebar-item metric">1M+ Users</div>
```

### SVG Connectors Between Components
Use an SVG overlay to draw orthogonal (right-angle) connectors between components. **Always use `<path>` with `M`/`L` commands for strictly horizontal and vertical segments. Do NOT use `<line>`, Bézier curves, or diagonal lines.** See [layouts/connectors.md](layouts/connectors.md) for full reference.

```html
<!-- Wrap diagram content in a relative container -->
<div style="position: relative;">
  <!-- ...layers and components here... -->
  <!-- SVG overlay as last child -->
  <svg style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; overflow: visible;">
    <defs>
      <marker id="arrowhead" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
        <path d="M0,0 L8,3 L0,6" fill="none" stroke="#94a3b8" stroke-width="1"/>
      </marker>
    </defs>
    <!-- Orthogonal solid arrow (vertical → horizontal → vertical) -->
    <path d="M 200,72 L 200,90 L 400,90 L 400,108" class="arch-conn" marker-end="url(#arrowhead)"/>
    <!-- Orthogonal dashed line -->
    <path d="M 600,72 L 600,90 L 600,90 L 600,108" class="arch-conn-dashed" marker-end="url(#arrowhead)"/>
    <!-- Label -->
    <text x="420" y="86" class="arch-conn-label">data flow</text>
  </svg>
</div>
```

## Styling Reference

### Common Classes (shared across all styles)
- `.arch-wrapper` — flex container for sidebar + main layout
- `.arch-sidebar` — fixed-width sidebar column
- `.arch-main` — flexible main content area
- `.arch-layer` — layer container (add semantic class: `.user`, `.application`, `.ai`, `.data`, `.infra`, `.external`)
- `.arch-box` — component box; `.arch-box.highlight` for key items; `.arch-box.tech` for smaller tech items
- `.arch-grid-2` to `.arch-grid-6` — grid column layouts
- `.arch-sidebar-panel` — sidebar panel container
- `.arch-sidebar-item` — sidebar item; `.arch-sidebar-item.metric` for highlighted metrics

## Best Practices

### HTML Usage Guidelines

1. **Direct embedding only** — Always embed HTML directly in Markdown, never use ` ```html ` code blocks
2. **No empty lines in structure** — Keep the entire HTML block continuous without any empty lines
3. **Incremental development** — Build diagrams step by step:
   - Start with basic framework and layout structure (single/two/three column as needed)
   - Add empty layer containers with proper CSS classes
   - Fill in content layer by layer from top to bottom
   - Refine content and add highlights last

### Architecture Design

1. **Keep layers logically separated** — Each layer should represent a clear architectural tier
2. **Use consistent naming** — Follow naming conventions for components and services
3. **Highlight key components** — Use `.highlight` class for critical components
4. **Add technical details** — Include technology stack info in `<small>` tags
5. **Balance information density** — Don't overcrowd components with text
6. **Use icons sparingly** — Add emojis to titles for visual hierarchy
7. **Maintain color semantics** — Stick to the established color meanings
8. **Consider responsive design** — Grids automatically adapt to content