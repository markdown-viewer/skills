# Versus Split Layout

**Layout**: Side-by-side contrast with clear visual division
**Best for**: A vs B, before/after, pros/cons, product comparison, two-perspective analysis

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-vs { display: grid; grid-template-columns: 1fr auto 1fr; gap: 0; margin-bottom: 16px; }
    .card-vs-side { padding: 20px; }
    .card-vs-side.left { background: rgba(0,0,0,0.03); border-top: 4px solid #111; }
    .card-vs-side.right { background: rgba(0,0,0,0.06); border-top: 4px solid #666; }
    .card-vs-divider { display: flex; align-items: center; justify-content: center; width: 40px; font-size: 14px; font-weight: 700; color: #999; letter-spacing: 0.1em; }
    .card-vs-label { margin: 0 0 10px; font-size: 13px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: #666; }
    .card-vs-title { margin: 0 0 10px; font-size: 18px; font-weight: 700; color: #111; }
    .card-vs-text { margin: 0; font-size: 14px; line-height: 1.55; color: #444; }
    .card-vs-list { list-style: none; padding: 0; margin: 8px 0 0; }
    .card-vs-list li { font-size: 13px; line-height: 1.5; color: #444; padding: 4px 0 4px 16px; position: relative; }
    .card-vs-list li::before { content: '·'; position: absolute; left: 0; color: #999; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #444; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Comparison · Analysis</p>
    <h1 class="card-title">Option A vs Option B</h1>
    <div class="card-bar"></div>
    <div class="card-vs">
      <div class="card-vs-side left">
        <p class="card-vs-label">Option A</p>
        <p class="card-vs-title">Traditional Approach</p>
        <p class="card-vs-text">Established workflow with predictable outcomes and lower learning curve.</p>
        <ul class="card-vs-list">
          <li>Proven reliability</li>
          <li>Lower upfront cost</li>
          <li>Larger talent pool</li>
        </ul>
      </div>
      <div class="card-vs-divider">VS</div>
      <div class="card-vs-side right">
        <p class="card-vs-label">Option B</p>
        <p class="card-vs-title">Modern Approach</p>
        <p class="card-vs-text">Cutting-edge tooling with higher ceiling and better long-term scalability.</p>
        <ul class="card-vs-list">
          <li>Higher performance</li>
          <li>Better DX</li>
          <li>Future-proof</li>
        </ul>
      </div>
    </div>
    <p class="card-body">Both approaches have valid trade-offs. The right choice depends on team size, timeline, and long-term maintenance strategy.</p>
    <div class="card-footer">Source · Analysis Report</div>
  </div>
</div>
