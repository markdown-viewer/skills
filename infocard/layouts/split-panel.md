# Split Panel Layout

**Layout**: Two-column asymmetric layout with main content and sidebar
**Best for**: Main content + sidebar, left-right comparison, analytical spread

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 16px; font-size: 34px; font-weight: 700; line-height: 1.15; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-split { display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 20px; }
    .card-main { }
    .card-aside { }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #333; }
    .card-panel { padding: 16px 18px; background: rgba(0,0,0,0.03); border-top: 6px solid #111; margin-bottom: 12px; }
    .card-panel:last-child { margin-bottom: 0; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #888; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #444; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Analysis · Report</p>
    <h1 class="card-title">Split Panel for<br>Complex Content</h1>
    <div class="card-bar"></div>
    <div class="card-split">
      <div class="card-main">
        <p class="card-body">The main column carries the primary narrative — the core argument, detailed analysis, or step-by-step explanation. It should feel heavier and more substantial than the sidebar.</p>
        <p class="card-body">Use multiple paragraphs, ordered lists, or sub-headings within the main column to build a clear reading path from top to bottom.</p>
      </div>
      <div class="card-aside">
        <div class="card-panel">
          <p class="card-panel-title">Key Insight</p>
          <p class="card-panel-text">The sidebar carries distilled takeaways, supporting data, or quick-reference points.</p>
        </div>
        <div class="card-panel">
          <p class="card-panel-title">Context</p>
          <p class="card-panel-text">Secondary context, caveats, or related references that support the main argument.</p>
        </div>
      </div>
    </div>
    <div class="card-footer">Source · Attribution</div>
  </div>
</div>
