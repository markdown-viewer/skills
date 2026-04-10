# Connectors Layout

**Layout**: SVG overlay for drawing orthogonal (right-angle) lines/arrows between components
**Best for**: Showing data flow, dependencies, API calls, or any relationship between architecture components

## How It Works

Use an absolutely-positioned SVG element overlaid on the diagram container. Components get `id` attributes, and SVG `<path>` elements with orthogonal segments (horizontal + vertical only) connect them visually.

**Key principle**: The outer container must have `position: relative`, and the SVG overlay uses `position: absolute; top: 0; left: 0` with `pointer-events: none` so it doesn't block clicks.

> **IMPORTANT**: Always use orthogonal (right-angle) paths for connectors. Do NOT use diagonal lines (`<line>`), curved paths (Bézier `C`/`S`/`Q` commands), or any non-90° segments. All connectors must consist of strictly horizontal and vertical segments only, using the SVG `<path>` element with `M` and `L` commands.

## Connector Types

| Type | CSS Class | Use Case |
|---|---|---|
| Solid orthogonal line | `.arch-conn` | Direct dependency, data flow |
| Dashed orthogonal line | `.arch-conn-dashed` | Abstract relationship, optional dependency |
| Arrow (with marker) | Add `marker-end="url(#arrowhead)"` | Directional flow |
| Bidirectional | Add markers on both ends | Two-way communication |

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 4px; }
    .arch-layer-title { font-size: 13px; font-weight: 600; color: #475569; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; font-size: 11px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #334155; background: #ffffff; border: 1px solid #e2e8f0; }.arch-box.highlight { background: #fefce8; border: 1px solid #d4d726; font-weight: 600; }
    .arch-layer.user { background: #f0f9ff; border: 1px solid #bae6fd; }
    .arch-layer.application { background: #fffbeb; border: 1px solid #fde68a; }
    .arch-layer.data { background: #fdf2f8; border: 1px solid #fbcfe8; }
    .arch-conn { stroke: #94a3b8; stroke-width: 1.5; fill: none; }
    .arch-conn-dashed { stroke: #94a3b8; stroke-width: 1.5; fill: none; stroke-dasharray: 6 4; }
    .arch-conn-label { font-size: 9px; fill: #64748b; font-family: sans-serif; }
  </style>
  <div class="arch-title">System Architecture with Connectors</div>
  <div style="position: relative;">
    <div class="arch-layer user">
      <div class="arch-layer-title">User Interface Layer</div>
      <div class="arch-grid arch-grid-3">
        <div class="arch-box" id="web-app">Web App<br><small>React</small></div>
        <div class="arch-box" id="mobile-app">Mobile App<br><small>React Native</small></div>
        <div class="arch-box" id="api-client">API Client<br><small>REST</small></div>
      </div>
    </div>
    <div class="arch-layer application">
      <div class="arch-layer-title">Application Layer</div>
      <div class="arch-grid arch-grid-3">
        <div class="arch-box" id="auth-svc">Auth Service<br><small>OAuth 2.0</small></div>
        <div class="arch-box highlight" id="api-gw">API Gateway<br><small>Routing</small></div>
        <div class="arch-box" id="biz-logic">Business Logic<br><small>Core</small></div>
      </div>
    </div>
    <div class="arch-layer data">
      <div class="arch-layer-title">Data Layer</div>
      <div class="arch-grid arch-grid-4">
        <div class="arch-box" id="pg-db">Primary DB<br><small>PostgreSQL</small></div>
        <div class="arch-box" id="redis">Cache<br><small>Redis</small></div>
        <div class="arch-box" id="es">Search<br><small>Elasticsearch</small></div>
        <div class="arch-box" id="s3">Storage<br><small>S3</small></div>
      </div>
    </div>
    <!-- SVG Connector Overlay -->
    <svg style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; overflow: visible;">
      <defs>
        <marker id="arrowhead" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
          <path d="M0,0 L8,3 L0,6" fill="none" stroke="#94a3b8" stroke-width="1"/>
        </marker>
        <marker id="arrowhead-fill" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
          <path d="M0,0 L8,3 L0,6 Z" fill="#94a3b8"/>
        </marker>
      </defs>
      <!-- Orthogonal connectors: User → Application -->
      <path d="M 200,72 L 200,90 L 200,90 L 200,108" class="arch-conn" marker-end="url(#arrowhead)"/>
      <path d="M 600,72 L 600,90 L 600,90 L 600,108" class="arch-conn" marker-end="url(#arrowhead)"/>
      <path d="M 1000,72 L 1000,90 L 600,90 L 600,108" class="arch-conn-dashed" marker-end="url(#arrowhead)"/>
      <!-- Orthogonal connectors: Application → Data -->
      <path d="M 200,182 L 200,200 L 150,200 L 150,218" class="arch-conn" marker-end="url(#arrowhead)"/>
      <path d="M 600,182 L 600,200 L 450,200 L 450,218" class="arch-conn" marker-end="url(#arrowhead)"/>
      <path d="M 600,182 L 600,200 L 750,200 L 750,218" class="arch-conn-dashed" marker-end="url(#arrowhead)"/>
      <!-- Connector label -->
      <text x="620" y="196" class="arch-conn-label">queries</text>
    </svg>
  </div>
</div>

## Usage Guidelines

1. **Container setup** — Wrap the diagram content in a `<div style="position: relative;">`, then place the `<svg>` overlay as the last child
2. **Coordinate system** — SVG coordinates are relative to the container's top-left corner. Estimate positions based on grid layout and component sizes
3. **Arrow markers** — Define `<marker>` elements in `<defs>` once, reference via `marker-end="url(#arrowhead)"`
4. **Line types** — Use `class="arch-conn"` for solid lines, `class="arch-conn-dashed"` for dashed/abstract relationships
5. **Labels** — Use `<text class="arch-conn-label">` to annotate connectors
6. **Orthogonal paths** — Always use right-angle connections: `<path d="M x1,y1 L x1,yMid L x2,yMid L x2,y2">` (vertical → horizontal → vertical)

## CSS Reference

Add these classes to your `<style scoped>` section:

```css
/* Solid connector line */
.arch-conn { stroke: #94a3b8; stroke-width: 1.5; fill: none; }
/* Dashed connector line */
.arch-conn-dashed { stroke: #94a3b8; stroke-width: 1.5; fill: none; stroke-dasharray: 6 4; }
/* Connector label text */
.arch-conn-label { font-size: 9px; fill: #64748b; font-family: sans-serif; }
```

## Arrow Marker Definitions

Include these in the SVG `<defs>` block:

```html
<defs>
  <!-- Open arrowhead (stroke only) -->
  <marker id="arrowhead" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
    <path d="M0,0 L8,3 L0,6" fill="none" stroke="#94a3b8" stroke-width="1"/>
  </marker>
  <!-- Filled arrowhead -->
  <marker id="arrowhead-fill" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
    <path d="M0,0 L8,3 L0,6 Z" fill="#94a3b8"/>
  </marker>
  <!-- Bidirectional marker (for marker-start) -->
  <marker id="arrowhead-reverse" markerWidth="8" markerHeight="6" refX="0" refY="3" orient="auto">
    <path d="M8,0 L0,3 L8,6" fill="none" stroke="#94a3b8" stroke-width="1"/>
  </marker>
</defs>
```

## Orthogonal Path Patterns

```html
<!-- Vertical → Horizontal → Vertical (standard cross-layer connection) -->
<path d="M 100,50 L 100,100 L 300,100 L 300,150" class="arch-conn" marker-end="url(#arrowhead)"/>

<!-- Straight vertical drop (same column) -->
<path d="M 200,50 L 200,150" class="arch-conn" marker-end="url(#arrowhead)"/>

<!-- Labeled orthogonal connector -->
<path d="M 100,50 L 100,100 L 300,100 L 300,150" class="arch-conn-dashed" marker-end="url(#arrowhead)"/>
<text x="200" y="96" class="arch-conn-label">async event</text>
```
