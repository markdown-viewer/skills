# Badge Grid Layout

**Layout**: Grid of labeled badges or icons with short descriptions
**Best for**: Feature lists, capability catalogs, skill inventories, benefit showcases, toolkits

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 12px; background: #111; }
    .card-body { margin: 0 0 20px; font-size: 15px; color: #333; }
    .card-badges { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }
    .card-badge { display: flex; flex-direction: column; align-items: center; text-align: center; padding: 18px 12px; background: rgba(0,0,0,0.03); }
    .card-badge-icon { font-size: 28px; margin-bottom: 8px; line-height: 1; }
    .card-badge-label { margin: 0 0 4px; font-size: 13px; font-weight: 700; color: #111; }
    .card-badge-text { margin: 0; font-size: 12px; line-height: 1.45; color: #666; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Capabilities · Platform</p>
    <h1 class="card-title">What Ships Out of the Box</h1>
    <div class="card-bar"></div>
    <p class="card-body">Every deployment includes these core capabilities, configured and ready to use from day one.</p>
    <div class="card-badges">
      <div class="card-badge">
        <span class="card-badge-icon">&#x1F512;</span>
        <p class="card-badge-label">Auth &amp; SSO</p>
        <p class="card-badge-text">SAML, OIDC, and MFA with configurable session policies</p>
      </div>
      <div class="card-badge">
        <span class="card-badge-icon">&#x1F4CA;</span>
        <p class="card-badge-label">Analytics</p>
        <p class="card-badge-text">Real-time dashboards with custom event tracking and funnels</p>
      </div>
      <div class="card-badge">
        <span class="card-badge-icon">&#x1F310;</span>
        <p class="card-badge-label">CDN</p>
        <p class="card-badge-text">Global edge caching across 42 PoPs with automatic purge</p>
      </div>
      <div class="card-badge">
        <span class="card-badge-icon">&#x1F514;</span>
        <p class="card-badge-label">Alerts</p>
        <p class="card-badge-text">Threshold and anomaly-based alerts via Slack, email, PagerDuty</p>
      </div>
      <div class="card-badge">
        <span class="card-badge-icon">&#x1F504;</span>
        <p class="card-badge-label">CI/CD</p>
        <p class="card-badge-text">Git-push deploys with preview environments and rollback</p>
      </div>
      <div class="card-badge">
        <span class="card-badge-icon">&#x1F4DD;</span>
        <p class="card-badge-label">Audit Log</p>
        <p class="card-badge-text">Immutable event log with 90-day retention and SIEM export</p>
      </div>
    </div>
    <div class="card-footer">Platform Capabilities · Standard Tier</div>
  </div>
</div>
