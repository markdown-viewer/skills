# Clean Modern Style

**Style**: White background, blue accents, clean sans-serif, minimal borders, contemporary feel
**Best for**: Product launches, tech announcements, startup pitches

## Style Characteristics

| Property | Value |
|---|---|
| Background | White `#ffffff` |
| Surface | Light gray `#f8fafc` (card background) |
| Text | Dark slate `#0f172a` |
| Accent | Blue `#2563eb` (rules, tags, highlights) |
| Muted | Slate `#64748b` (meta, captions) |
| Tint | `rgba(37,99,235,0.06)` (panel backgrounds) |
| Title Font | `Inter`, sans-serif — weight 700 |
| Body Font | `Inter`, sans-serif |
| Rules | 4px solid accent blue |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #f8fafc; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #0f172a; line-height: 1.6; border: 1px solid #e2e8f0; border-radius: 8px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: #2563eb; }
    .card-title { margin: 0 0 14px; font-size: 34px; font-weight: 700; line-height: 1.2; letter-spacing: -0.02em; color: #0f172a; }
    .card-subtitle { margin: 0 0 16px; font-size: 16px; line-height: 1.6; color: #475569; }
    .card-bar { width: 64px; height: 4px; margin: 0 0 20px; background: #2563eb; border-radius: 2px; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #334155; }
    .card-grid { display: grid; gap: 14px; }.card-grid-2 { grid-template-columns: 1fr 1fr; }
    .card-panel { padding: 16px 18px; background: rgba(37,99,235,0.06); border-top: 4px solid #2563eb; border-radius: 0 0 6px 6px; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: #2563eb; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #475569; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 3px 10px; background: #2563eb; color: #fff; border-radius: 3px; margin-right: 6px; margin-bottom: 4px; }
    .card-stat { font-size: 44px; font-weight: 700; line-height: 1; color: #2563eb; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #64748b; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 64px/0.82 'Inter', sans-serif; float: left; margin: 4px 12px 0 -2px; color: #2563eb; }
    .card-highlight { font-size: 16px; font-weight: 500; line-height: 1.5; color: #0f172a; padding: 10px 0 10px 16px; border-left: 3px solid #2563eb; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #0f172a; }
    .card-divider { height: 1px; background: #e2e8f0; margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #2563eb; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid #e2e8f0; font-size: 11px; color: #94a3b8; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Product Launch</p>
    <h1 class="card-title">Next-Generation Platform<br>Built for Scale</h1>
    <div class="card-bar"></div>
    <p class="card-subtitle">A modern take on information architecture, combining clean design with powerful content hierarchy for high-impact communication.</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Key Feature</p>
        <p class="card-panel-text">Responsive grid layouts with semantic type scales. Every component is designed for clarity at any information density.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Built With</p>
        <p class="card-panel-text">Pure HTML/CSS with no external dependencies. Embeds directly in Markdown for immediate rendering.</p>
      </div>
    </div>
    <div class="card-footer">v1.0 · Clean Modern Template</div>
  </div>
</div>
