# Stacked Modules Layout

**Layout**: Vertical stack of mixed-weight modules with clear hierarchy
**Best for**: Multi-section content, high-density topics, structured summaries

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 32px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 16px; background: #111; }
    .card-subtitle { margin: 0 0 20px; font-size: 16px; line-height: 1.55; color: #444; }
    .card-modules { display: flex; flex-direction: column; gap: 14px; }
    .card-panel { padding: 16px 18px; background: rgba(0,0,0,0.03); border-top: 6px solid #111; }
    .card-panel.heavy { padding: 20px 22px; }
    .card-panel.light { border-top-width: 3px; border-top-color: #ccc; background: transparent; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #888; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #444; }
    .card-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Deep Dive · High Density</p>
    <h1 class="card-title">Stacked Modules for<br>Rich Structured Content</h1>
    <div class="card-bar"></div>
    <p class="card-subtitle">A core summary statement that frames everything below. This line establishes the main thesis before the modules elaborate.</p>
    <div class="card-modules">
      <div class="card-panel heavy">
        <p class="card-panel-title">Primary Module</p>
        <p class="card-panel-text">The heaviest block carries the core framework, main argument, or central process. Give it more space, richer copy, and stronger visual weight than other modules.</p>
      </div>
      <div class="card-row">
        <div class="card-panel">
          <p class="card-panel-title">Supporting Point A</p>
          <p class="card-panel-text">Medium-weight block for secondary evidence or a key sub-topic.</p>
        </div>
        <div class="card-panel">
          <p class="card-panel-title">Supporting Point B</p>
          <p class="card-panel-text">Another medium block. Together these form a balanced pair beneath the primary module.</p>
        </div>
      </div>
      <div class="card-panel light">
        <p class="card-panel-title">Boundary / Caveats</p>
        <p class="card-panel-text">Lighter treatment for limitations, edge cases, or additional context that qualifies the main argument.</p>
      </div>
    </div>
    <div class="card-footer">Source · Attribution</div>
  </div>
</div>
