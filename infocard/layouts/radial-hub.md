# Radial Hub Layout

**Layout**: Central concept surrounded by radiating satellite items
**Best for**: Ecosystem overviews, core-plus-features, concept maps, hub-and-spoke relationships

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-hub { display: flex; flex-direction: column; align-items: center; gap: 16px; }
    .card-hub-core { text-align: center; padding: 24px 32px; background: #111; color: #fafafa; width: fit-content; }
    .card-hub-core-title { margin: 0 0 4px; font-size: 20px; font-weight: 700; }
    .card-hub-core-text { margin: 0; font-size: 13px; opacity: 0.8; }
    .card-spokes { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; width: 100%; }
    .card-spoke { padding: 14px 16px; background: rgba(0,0,0,0.03); border-top: 3px solid #111; }
    .card-spoke-title { margin: 0 0 4px; font-size: 13px; font-weight: 700; text-transform: uppercase; letter-spacing: 0.08em; color: #111; }
    .card-spoke-text { margin: 0; font-size: 13px; line-height: 1.5; color: #555; }
    .card-body { margin: 0 0 16px; font-size: 15px; color: #333; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Ecosystem · Overview</p>
    <h1 class="card-title">Developer Platform Architecture</h1>
    <div class="card-bar"></div>
    <div class="card-hub">
      <div class="card-hub-core">
        <p class="card-hub-core-title">Platform Core API</p>
        <p class="card-hub-core-text">Authentication · Rate Limiting · Versioning</p>
      </div>
      <div class="card-spokes">
        <div class="card-spoke">
          <p class="card-spoke-title">SDK Layer</p>
          <p class="card-spoke-text">Client libraries in 6 languages with auto-generated type definitions and request builders.</p>
        </div>
        <div class="card-spoke">
          <p class="card-spoke-title">Webhooks</p>
          <p class="card-spoke-text">Event-driven notifications with retry logic, signature verification, and delivery logs.</p>
        </div>
        <div class="card-spoke">
          <p class="card-spoke-title">Sandbox</p>
          <p class="card-spoke-text">Isolated test environment with seeded data, mock endpoints, and clock control for time-based flows.</p>
        </div>
        <div class="card-spoke">
          <p class="card-spoke-title">CLI Tools</p>
          <p class="card-spoke-text">Terminal interface for resource management, deployment triggers, and log tailing.</p>
        </div>
        <div class="card-spoke">
          <p class="card-spoke-title">Marketplace</p>
          <p class="card-spoke-text">Third-party integration catalog with one-click install, OAuth consent, and billing hooks.</p>
        </div>
        <div class="card-spoke">
          <p class="card-spoke-title">Docs Portal</p>
          <p class="card-spoke-text">Interactive API reference with executable examples, changelog, and migration guides.</p>
        </div>
      </div>
    </div>
    <div class="card-footer">Platform Engineering · Architecture Overview</div>
  </div>
</div>
