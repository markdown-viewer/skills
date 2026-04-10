# Paper Minimal Style

**Style**: Ultra-clean white canvas, black line art, minimal decoration, digital notebook feel
**Best for**: Product notes, task summaries, meeting notes, project briefs, clean documentation

## Style Characteristics

| Property | Value |
|---|---|
| Background | Pure white `#ffffff` |
| Text | Neutral black `#1a1a1a` |
| Accent | Muted blue `#4a7cbe` |
| Muted | `#9ca3af` |
| Tint | `rgba(0,0,0,0.02)` (panel backgrounds) |
| Title Font | `Inter`, `Noto Sans SC`, sans-serif — weight 700 |
| Body Font | `Inter`, `Noto Sans SC`, sans-serif |
| Noise | None — clean digital surface |
| Rules | 2px solid accent for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #ffffff; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #1a1a1a; line-height: 1.6; border: 1px solid #e5e7eb; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; color: #9ca3af; }
    .card-title { margin: 0 0 16px; font-size: 32px; font-weight: 700; line-height: 1.2; letter-spacing: -0.02em; color: #1a1a1a; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #4b5563; }
    .card-bar { width: 60px; height: 2px; margin: 0 0 20px; background: #4a7cbe; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.7; color: #374151; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1fr 1fr; }
    .card-panel { padding: 16px 18px; background: #f9fafb; border-top: 2px solid #4a7cbe; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: #4a7cbe; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.6; color: #4b5563; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: #f3f4f6; color: #4a7cbe; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; border: 1px solid #e5e7eb; border-radius: 3px; }
    .card-stat { font-size: 44px; font-weight: 700; line-height: 1; color: #4a7cbe; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #9ca3af; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 64px/0.82 'Inter', sans-serif; float: left; margin: 4px 12px 0 -2px; color: #4a7cbe; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #1a1a1a; padding: 10px 0 10px 18px; border-left: 2px solid #4a7cbe; margin: 16px 0; background: #f9fafb; padding: 12px 18px; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #1a1a1a; }
    .card-divider { height: 1px; background: #e5e7eb; margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #4a7cbe; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid #e5e7eb; font-size: 11px; color: #9ca3af; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Project Brief · Migration Plan</p>
    <h1 class="card-title">Design System v3<br>Migration Checklist</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">The legacy component library will be fully deprecated by end of Q3. All product teams must migrate to Design System v3, which introduces tokenized styling, composable primitives, and accessibility-first defaults across web and mobile surfaces.</p>
    <p class="card-highlight">Target: 100% adoption by September 30</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Completed</p>
        <p class="card-panel-text">Token migration for color, spacing, and typography. Button and input components converted. Storybook documentation updated. CI lint rules enforced.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Remaining</p>
        <p class="card-panel-text">Modal and dialog components. Data table refactor. Dark mode token mapping. Mobile gesture components. Visual regression test baseline.</p>
      </div>
    </div>
    <span class="card-endmark">◇</span>
    <div class="card-footer">Design Engineering · Migration Tracker · 2026</div>
  </div>
</div>
