# Layer Layouts

**Layout**: Catalog of per-layer layout patterns
**Best for**: Choosing how to arrange components within each layer of any architecture diagram

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-main { width: 100%; }
    .arch-layer { margin: 10px 0; padding: 14px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }
    .arch-subgroup { display: flex; gap: 8px; }.arch-subgroup-box { flex: 1; border-radius: 4px; padding: 10px; background: #fff; border: 1px solid #ddd; }.arch-subgroup-title { font-size: 10px; font-weight: 600; color: #555; text-align: center; margin-bottom: 6px; }
    .arch-product-group { display: flex; gap: 10px; }.arch-product { flex: 1; border-radius: 4px; padding: 10px; background: #fff; border: 1px dashed #bbb; }.arch-product-title { font-size: 11px; font-weight: 600; color: #555; margin-bottom: 8px; text-align: center; }
    .arch-kpi-row { display: flex; gap: 8px; }.arch-kpi { flex: 1; border: 1px solid #ccc; border-radius: 4px; padding: 10px; text-align: center; background: #fff; }.arch-kpi-value { font-size: 20px; font-weight: 700; color: #333; }.arch-kpi-label { font-size: 10px; color: #777; text-transform: uppercase; letter-spacing: 0.5px; margin-top: 4px; }
    .arch-vstack { display: flex; flex-direction: column; gap: 6px; }.arch-vstack-item { border-radius: 3px; padding: 8px; font-size: 11px; font-weight: 500; color: #333; background: #fff; border: 1px solid #ddd; display: flex; align-items: center; gap: 8px; }.arch-vstack-num { width: 20px; height: 20px; border-radius: 50%; background: #eee; border: 1px solid #ccc; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 600; color: #555; flex-shrink: 0; }
    .arch-zone-row { display: flex; gap: 8px; }.arch-zone { flex: 1; padding: 10px; border: 1px dashed #bbb; border-radius: 4px; background: #fff; }.arch-zone-title { font-size: 10px; font-weight: 600; color: #666; text-align: center; margin-bottom: 6px; text-transform: uppercase; letter-spacing: 0.3px; }
    .arch-inline-pipeline { display: flex; gap: 0; align-items: stretch; }.arch-inline-stage { flex: 1; padding: 8px; border: 1px solid #ddd; border-radius: 3px; background: #fff; text-align: center; font-size: 11px; font-weight: 500; color: #333; }.arch-inline-arrow { display: flex; align-items: center; justify-content: center; width: 28px; flex-shrink: 0; font-size: 16px; color: #999; }
    .arch-mixed-row { display: flex; gap: 8px; }.arch-mixed-wide { flex: 2; border-radius: 3px; padding: 10px; background: #fff; border: 1px solid #ddd; text-align: center; font-size: 11px; font-weight: 500; color: #333; }.arch-mixed-narrow { flex: 1; border-radius: 3px; padding: 10px; background: #fff; border: 1px solid #ddd; text-align: center; font-size: 11px; font-weight: 500; color: #333; }
  </style>
  <div class="arch-title">Layer Layout Patterns</div>
  <div class="arch-main">
    <div class="arch-layer">
      <div class="arch-layer-title">1 · Simple Grid — equal-width columns (2 / 3 / 4 / 5 / 6)</div>
      <div class="arch-grid arch-grid-6"><div class="arch-box">Web App</div><div class="arch-box">Mobile App</div><div class="arch-box">Desktop App</div><div class="arch-box">API Portal</div><div class="arch-box">CLI Tool</div><div class="arch-box">SDK</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">2 · Sub-grouped — split into titled groups with independent grids</div>
      <div class="arch-subgroup">
        <div class="arch-subgroup-box">
          <div class="arch-subgroup-title">Synchronous</div>
          <div class="arch-grid arch-grid-3"><div class="arch-box">REST API</div><div class="arch-box">GraphQL</div><div class="arch-box">gRPC</div></div>
        </div>
        <div class="arch-subgroup-box">
          <div class="arch-subgroup-title">Asynchronous</div>
          <div class="arch-grid arch-grid-3"><div class="arch-box">Kafka</div><div class="arch-box">RabbitMQ</div><div class="arch-box">SQS</div></div>
        </div>
      </div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">3 · Product Groups — dashed-border modules for multi-product layers</div>
      <div class="arch-product-group">
        <div class="arch-product">
          <div class="arch-product-title">Product A</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">User Mgmt</div><div class="arch-box">Auth</div><div class="arch-box">Profile</div><div class="arch-box">Settings</div></div>
        </div>
        <div class="arch-product">
          <div class="arch-product-title">Product B</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">Orders</div><div class="arch-box">Payments</div><div class="arch-box">Invoicing</div><div class="arch-box">Refunds</div></div>
        </div>
        <div class="arch-product">
          <div class="arch-product-title">Product C</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">Analytics</div><div class="arch-box">Reports</div><div class="arch-box">Dashboards</div><div class="arch-box">Exports</div></div>
        </div>
      </div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">4 · KPI / Metrics Row — large values with labels</div>
      <div class="arch-kpi-row">
        <div class="arch-kpi"><div class="arch-kpi-value">99.9%</div><div class="arch-kpi-label">Uptime</div></div>
        <div class="arch-kpi"><div class="arch-kpi-value">142ms</div><div class="arch-kpi-label">P95 Latency</div></div>
        <div class="arch-kpi"><div class="arch-kpi-value">2.4M</div><div class="arch-kpi-label">Daily Requests</div></div>
        <div class="arch-kpi"><div class="arch-kpi-value">12</div><div class="arch-kpi-label">Microservices</div></div>
        <div class="arch-kpi"><div class="arch-kpi-value">3</div><div class="arch-kpi-label">Regions</div></div>
      </div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">5 · Vertical Stack — ordered steps or sequential items</div>
      <div class="arch-vstack">
        <div class="arch-vstack-item"><div class="arch-vstack-num">1</div>Client sends request to API Gateway</div>
        <div class="arch-vstack-item"><div class="arch-vstack-num">2</div>Gateway validates token and applies rate limiting</div>
        <div class="arch-vstack-item"><div class="arch-vstack-num">3</div>Request routed to appropriate microservice</div>
        <div class="arch-vstack-item"><div class="arch-vstack-num">4</div>Service processes business logic and queries database</div>
        <div class="arch-vstack-item"><div class="arch-vstack-num">5</div>Response returned through gateway to client</div>
      </div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">6 · Nested Zones — dashed containers for isolation boundaries</div>
      <div class="arch-zone-row">
        <div class="arch-zone">
          <div class="arch-zone-title">Public Subnet</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">ALB</div><div class="arch-box">NAT GW</div><div class="arch-box">Bastion</div><div class="arch-box">WAF</div></div>
        </div>
        <div class="arch-zone">
          <div class="arch-zone-title">Private Subnet A</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">App Server 1</div><div class="arch-box">App Server 2</div><div class="arch-box">Worker 1</div><div class="arch-box">Worker 2</div></div>
        </div>
        <div class="arch-zone">
          <div class="arch-zone-title">Private Subnet B</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">RDS Primary</div><div class="arch-box">RDS Standby</div><div class="arch-box">ElastiCache</div><div class="arch-box">S3 Endpoint</div></div>
        </div>
      </div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">7 · Inline Pipeline — horizontal flow with arrow connectors</div>
      <div class="arch-inline-pipeline">
        <div class="arch-inline-stage">Source Code</div>
        <div class="arch-inline-arrow">→</div>
        <div class="arch-inline-stage highlight">Build</div>
        <div class="arch-inline-arrow">→</div>
        <div class="arch-inline-stage">Unit Test</div>
        <div class="arch-inline-arrow">→</div>
        <div class="arch-inline-stage">Integration Test</div>
        <div class="arch-inline-arrow">→</div>
        <div class="arch-inline-stage">Staging Deploy</div>
        <div class="arch-inline-arrow">→</div>
        <div class="arch-inline-stage">Production</div>
      </div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">8 · Mixed Width — unequal columns for primary + secondary elements</div>
      <div class="arch-mixed-row">
        <div class="arch-mixed-wide"><strong>Core Database</strong><br><small>PostgreSQL · Primary read/write store</small></div>
        <div class="arch-mixed-narrow">Redis Cache<br><small>Hot data</small></div>
        <div class="arch-mixed-narrow">Search Index<br><small>Elasticsearch</small></div>
      </div>
      <div class="arch-mixed-row" style="margin-top: 6px;">
        <div class="arch-mixed-narrow">Event Store<br><small>Kafka</small></div>
        <div class="arch-mixed-wide"><strong>Data Lake</strong><br><small>S3 + Glue · Long-term analytics storage</small></div>
        <div class="arch-mixed-narrow">Blob Store<br><small>Files/Media</small></div>
      </div>
    </div>
  </div>
</div>
