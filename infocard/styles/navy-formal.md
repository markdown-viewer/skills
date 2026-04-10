# Navy Formal Style

**Style**: Professional corporate palette, navy/gold accents, structured geometry, authoritative presence
**Best for**: Investor decks, executive briefs, quarterly reports, corporate proposals, board summaries

## Style Characteristics

| Property | Value |
|---|---|
| Background | Pure white `#ffffff` |
| Text | Navy `#1e3a5f` |
| Accent | Gold `#c9a227` |
| Secondary | Light navy `#3d5a80` |
| Muted | Corporate gray `#4a5568` |
| Tint | `rgba(201,162,39,0.06)` (gold-tinted panel backgrounds) |
| Title Font | `Inter`, sans-serif — weight 700 |
| Body Font | `Inter`, sans-serif |
| Texture | None — clean corporate surface |
| Rules | 5px solid gold for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #ffffff; padding: 40px; overflow: hidden; font-family: 'Inter', sans-serif; color: #1e3a5f; line-height: 1.6; border-bottom: 5px solid #c9a227; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #4a5568; }
    .card-title { margin: 0 0 16px; font-size: 34px; font-weight: 700; line-height: 1.2; letter-spacing: -0.01em; color: #1e3a5f; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #3d5a80; }
    .card-bar { width: 80px; height: 5px; margin: 0 0 20px; background: #c9a227; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.65; color: #334155; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(201,162,39,0.06); border-top: 5px solid #c9a227; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #1e3a5f; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.6; color: #4a5568; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: #1e3a5f; color: #ffffff; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; }
    .card-stat { font-size: 48px; font-weight: 700; line-height: 1; color: #c9a227; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #4a5568; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 68px/0.82 Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #1e3a5f; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #1e3a5f; padding: 10px 0 10px 18px; border-left: 4px solid #c9a227; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #1e3a5f; }
    .card-divider { height: 1px; background: rgba(30,58,95,0.1); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #c9a227; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(30,58,95,0.1); font-size: 11px; color: #4a5568; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Investor Update · Series B</p>
    <h1 class="card-title">FY2025 Performance<br>and Growth Trajectory</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">Annual recurring revenue reached $18.4M, up 142% year-over-year, driven by enterprise contract expansion and a net revenue retention rate of 128%. The company achieved cash-flow positive operations in Q3, three quarters ahead of the original plan presented at Series A close.</p>
    <p class="card-highlight">Path to profitability accelerated by 9 months</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Key Metrics</p>
        <p class="card-panel-text">ARR $18.4M · Gross margin 78% · CAC payback 11 months · LTV:CAC ratio 5.2x · Enterprise accounts 47 (+23 net new)</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">FY2026 Outlook</p>
        <p class="card-panel-text">Target $38M ARR · APAC market entry Q2 · Government vertical launch · SOC 2 Type II certification · Headcount 85 → 140</p>
      </div>
    </div>
    <span class="card-endmark">◆</span>
    <div class="card-footer">Confidential · Board Materials · March 2026</div>
  </div>
</div>
