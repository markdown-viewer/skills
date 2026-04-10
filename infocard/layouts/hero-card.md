# Hero Card Layout

**Layout**: Title-dominant card with hero area, summary, and one supporting panel
**Best for**: Single topic with title + summary + one supporting panel, low to medium density

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 16px; font-size: 36px; font-weight: 700; line-height: 1.15; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-subtitle { margin: 0 0 20px; font-size: 17px; line-height: 1.55; color: #444; }
    .card-panel { padding: 16px 18px; background: rgba(0,0,0,0.03); border-top: 6px solid #111; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #888; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #444; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Category · Date</p>
    <h1 class="card-title">Hero Headline That<br>Anchors the Entire Card</h1>
    <div class="card-bar"></div>
    <p class="card-subtitle">A clear summary paragraph that expands on the headline. This should give readers the core message in 2–3 sentences without requiring them to read further.</p>
    <div class="card-panel">
      <p class="card-panel-title">Key Takeaway</p>
      <p class="card-panel-text">Supporting context that adds depth to the hero message. This panel carries secondary information — evidence, methodology, or a call to action.</p>
    </div>
    <div class="card-footer">Source · Attribution</div>
  </div>
</div>
