# Bento Grid Layout

**Layout**: Asymmetric multi-size grid (inspired by Japanese bento box), mixed-weight cells
**Best for**: Multi-topic overviews, feature showcases, knowledge collections, content catalogs

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-bento { display: grid; grid-template-columns: 2fr 1fr; grid-template-rows: auto auto; gap: 12px; }
    .card-bento-cell { padding: 18px; background: rgba(0,0,0,0.03); border-top: 4px solid #111; }
    .card-bento-cell.span-col { grid-column: span 2; }
    .card-bento-cell.span-row { grid-row: span 2; }
    .card-bento-cell.accent { background: rgba(0,0,0,0.06); }
    .card-bento-title { margin: 0 0 6px; font-size: 14px; font-weight: 700; color: #111; }
    .card-bento-text { margin: 0; font-size: 13px; line-height: 1.5; color: #555; }
    .card-bento-stat { font-size: 36px; font-weight: 700; line-height: 1; color: #111; margin: 0 0 4px; }
    .card-bento-label { font-size: 11px; font-weight: 600; color: #888; text-transform: uppercase; letter-spacing: 0.1em; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Overview · Multi-Topic</p>
    <h1 class="card-title">Platform Feature Overview</h1>
    <div class="card-bar"></div>
    <div class="card-bento">
      <div class="card-bento-cell span-row accent">
        <p class="card-bento-title">Core Engine</p>
        <p class="card-bento-text">The platform's central processing layer handles real-time data ingestion, transformation, and routing across all connected services. Built on an event-driven architecture for sub-second response times.</p>
        <p class="card-bento-stat" style="margin-top: 12px;">47ms</p>
        <p class="card-bento-label">Avg Latency</p>
      </div>
      <div class="card-bento-cell">
        <p class="card-bento-title">API Gateway</p>
        <p class="card-bento-text">Rate limiting, auth, and routing in one layer. Supports REST, GraphQL, and gRPC.</p>
      </div>
      <div class="card-bento-cell">
        <p class="card-bento-title">Monitoring</p>
        <p class="card-bento-text">Real-time dashboards with anomaly detection and automated alert routing.</p>
      </div>
      <div class="card-bento-cell span-col">
        <p class="card-bento-title">Developer Experience</p>
        <p class="card-bento-text">CLI tools, SDK in 6 languages, interactive documentation with live examples, and a sandbox environment for testing integrations.</p>
      </div>
    </div>
    <div class="card-footer">Feature Overview · Q1 2026</div>
  </div>
</div>
