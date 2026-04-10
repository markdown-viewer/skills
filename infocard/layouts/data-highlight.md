# Data Highlight Layout

**Layout**: Numbers-first card with oversized metrics, stat strip, and supporting context
**Best for**: KPI cards, data summaries, performance dashboards, metric-driven announcements

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin-bottom: 20px; }
    .card-stat-block { text-align: center; padding: 16px 8px; }
    .card-stat { font-size: 48px; font-weight: 700; line-height: 1; color: #111; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #888; text-transform: uppercase; letter-spacing: 0.1em; margin: 6px 0 0; }
    .card-body { margin: 0 0 20px; font-size: 15px; line-height: 1.6; color: #444; }
    .card-grid { display: grid; gap: 14px; }.card-grid-2 { grid-template-columns: 1fr 1fr; }
    .card-panel { padding: 16px 18px; background: rgba(0,0,0,0.03); border-top: 6px solid #111; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #888; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #444; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Quarterly Report · Q4 2026</p>
    <h1 class="card-title">Key Metrics Overview</h1>
    <div class="card-bar"></div>
    <div class="card-stats">
      <div class="card-stat-block">
        <p class="card-stat">127K</p>
        <p class="card-stat-label">New Users</p>
      </div>
      <div class="card-stat-block">
        <p class="card-stat">98.5%</p>
        <p class="card-stat-label">Satisfaction</p>
      </div>
      <div class="card-stat-block">
        <p class="card-stat">¥3.2M</p>
        <p class="card-stat-label">Revenue</p>
      </div>
    </div>
    <p class="card-body">Sustained growth across all verticals with particularly strong performance in enterprise adoption. The platform processed 4.7 billion API calls this quarter with zero unplanned downtime.</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Top Driver</p>
        <p class="card-panel-text">Enterprise self-serve onboarding reduced time-to-value by 60%, driving a 3x increase in paid conversions.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Next Focus</p>
        <p class="card-panel-text">Q1 priority is international expansion with localized pricing and regional compliance certifications.</p>
      </div>
    </div>
    <div class="card-footer">Data source: Internal Analytics Platform</div>
  </div>
</div>
