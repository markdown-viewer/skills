# Metric Board Layout

**Layout**: Dashboard-style multi-metric display with organized KPI grid
**Best for**: Performance dashboards, quarterly reviews, health checks, operational summaries

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 12px; background: #111; }
    .card-body { margin: 0 0 20px; font-size: 15px; color: #333; }
    .card-metrics { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin-bottom: 16px; }
    .card-metric { padding: 16px; background: rgba(0,0,0,0.03); border-top: 4px solid #111; }
    .card-metric-value { margin: 0; font-size: 32px; font-weight: 700; line-height: 1; color: #111; }
    .card-metric-label { margin: 6px 0 0; font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; color: #888; }
    .card-metric-delta { margin: 4px 0 0; font-size: 12px; font-weight: 600; }
    .card-metric-delta.up { color: #16a34a; }
    .card-metric-delta.down { color: #dc2626; }
    .card-metric-delta.flat { color: #888; }
    .card-detail { padding: 16px 18px; background: rgba(0,0,0,0.03); border-top: 4px solid #111; }
    .card-detail-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: #555; }
    .card-detail-text { margin: 0; font-size: 14px; line-height: 1.55; color: #444; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Dashboard · March 2026</p>
    <h1 class="card-title">Infrastructure Health Report</h1>
    <div class="card-bar"></div>
    <div class="card-metrics">
      <div class="card-metric">
        <p class="card-metric-value">99.97%</p>
        <p class="card-metric-label">Uptime</p>
        <p class="card-metric-delta up">+0.12% vs Feb</p>
      </div>
      <div class="card-metric">
        <p class="card-metric-value">14ms</p>
        <p class="card-metric-label">P95 Latency</p>
        <p class="card-metric-delta up">-3ms vs Feb</p>
      </div>
      <div class="card-metric">
        <p class="card-metric-value">2.1M</p>
        <p class="card-metric-label">Requests/Day</p>
        <p class="card-metric-delta up">+18% vs Feb</p>
      </div>
      <div class="card-metric">
        <p class="card-metric-value">0.03%</p>
        <p class="card-metric-label">Error Rate</p>
        <p class="card-metric-delta up">-0.01% vs Feb</p>
      </div>
      <div class="card-metric">
        <p class="card-metric-value">68%</p>
        <p class="card-metric-label">CPU Avg</p>
        <p class="card-metric-delta down">+7% vs Feb</p>
      </div>
      <div class="card-metric">
        <p class="card-metric-value">$4.2K</p>
        <p class="card-metric-label">Monthly Cost</p>
        <p class="card-metric-delta flat">+1% vs Feb</p>
      </div>
    </div>
    <div class="card-detail">
      <p class="card-detail-title">Notable Events</p>
      <p class="card-detail-text">March 12: 23-minute degradation in us-east-1 due to upstream DNS provider. March 21: Auto-scaling triggered at 89% CPU during product launch traffic spike (resolved in 4 minutes). Zero security incidents.</p>
    </div>
    <div class="card-footer">SRE Team · Monthly Infrastructure Report</div>
  </div>
</div>
