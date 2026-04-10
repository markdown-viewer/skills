# Bold Contrast Style

**Style**: Dark background, high-contrast white text, vivid accent color, oversized numbers, impactful
**Best for**: Data highlights, KPI dashboards, event announcements

## Style Characteristics

| Property | Value |
|---|---|
| Background | Near-black `#0f172a` |
| Text | White `#f8fafc` |
| Accent | Amber `#f59e0b` (rules, stats, highlights) |
| Muted | Slate `#94a3b8` (meta, captions) |
| Tint | `rgba(248,250,252,0.05)` (panel backgrounds) |
| Title Font | `Inter`, sans-serif — weight 700 |
| Body Font | `Inter`, sans-serif |
| Rules | 4px solid accent amber |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #0f172a; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #f8fafc; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #f59e0b; }
    .card-title { margin: 0 0 14px; font-size: 36px; font-weight: 700; line-height: 1.15; letter-spacing: -0.02em; color: #f8fafc; }
    .card-subtitle { margin: 0 0 16px; font-size: 16px; line-height: 1.6; color: #cbd5e1; }
    .card-bar { width: 80px; height: 4px; margin: 0 0 20px; background: #f59e0b; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #e2e8f0; }
    .card-grid { display: grid; gap: 14px; }.card-grid-2 { grid-template-columns: 1fr 1fr; }.card-grid-3 { grid-template-columns: repeat(3, 1fr); }
    .card-panel { padding: 16px 18px; background: rgba(248,250,252,0.05); border-top: 4px solid #f59e0b; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #f59e0b; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #cbd5e1; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: #f59e0b; color: #0f172a; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; }
    .card-stat { font-size: 56px; font-weight: 700; line-height: 1; color: #f59e0b; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #94a3b8; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 64px/0.82 'Inter', sans-serif; float: left; margin: 4px 12px 0 -2px; color: #f59e0b; }
    .card-highlight { font-size: 16px; font-weight: 500; line-height: 1.5; color: #f8fafc; padding: 10px 0 10px 16px; border-left: 3px solid #f59e0b; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #f8fafc; }
    .card-divider { height: 1px; background: rgba(248,250,252,0.1); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #f59e0b; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(248,250,252,0.1); font-size: 11px; color: #64748b; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Annual Report · 2026</p>
    <h1 class="card-title">Performance Metrics<br>at a Glance</h1>
    <div class="card-bar"></div>
    <div class="card-grid card-grid-3">
      <div style="text-align: center; padding: 12px 0;">
        <p class="card-stat">99.9%</p>
        <p class="card-stat-label">Uptime</p>
      </div>
      <div style="text-align: center; padding: 12px 0;">
        <p class="card-stat">2.4M</p>
        <p class="card-stat-label">Active Users</p>
      </div>
      <div style="text-align: center; padding: 12px 0;">
        <p class="card-stat">&lt;50ms</p>
        <p class="card-stat-label">Avg Latency</p>
      </div>
    </div>
    <div class="card-grid card-grid-2" style="margin-top: 16px;">
      <div class="card-panel">
        <p class="card-panel-title">Growth</p>
        <p class="card-panel-text">Year-over-year user growth of 180%, driven by platform expansion across three new regions and API partner integrations.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Reliability</p>
        <p class="card-panel-text">Zero unplanned outages in Q4. Infrastructure migrated to multi-region active-active architecture with automated failover.</p>
      </div>
    </div>
    <div class="card-footer">Source: Q4 2026 Platform Report</div>
  </div>
</div>
