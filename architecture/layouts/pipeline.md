# Pipeline Layout

**Layout**: Horizontal left-to-right flow with sequential stages
**Best for**: Data pipelines, CI/CD flows, ETL processes, horizontal stage-based flows

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-pipeline { display: flex; gap: 0; align-items: stretch; }
    .arch-stage { flex: 1; padding: 14px; border: 1px solid #ccc; border-radius: 4px; background: #fafafa; display: flex; flex-direction: column; }
    .arch-stage-title { font-size: 12px; font-weight: 600; color: #555; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 10px; }
    .arch-arrow { display: flex; align-items: center; justify-content: center; width: 36px; flex-shrink: 0; font-size: 20px; color: #999; }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; margin: 3px 0; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }.arch-box.tech { font-size: 10px; color: #666; }
  </style>
  <div class="arch-title">Data Pipeline Architecture</div>
  <div class="arch-pipeline">
    <div class="arch-stage">
      <div class="arch-stage-title">Ingest</div>
      <div class="arch-box">API Collectors</div>
      <div class="arch-box">Event Stream</div>
      <div class="arch-box">File Upload</div>
      <div class="arch-box">CDC Capture</div>
    </div>
    <div class="arch-arrow">→</div>
    <div class="arch-stage">
      <div class="arch-stage-title">Process</div>
      <div class="arch-box highlight">Stream Engine</div>
      <div class="arch-box">Validation</div>
      <div class="arch-box">Enrichment</div>
      <div class="arch-box">Deduplication</div>
    </div>
    <div class="arch-arrow">→</div>
    <div class="arch-stage">
      <div class="arch-stage-title">Transform</div>
      <div class="arch-box">Schema Mapping</div>
      <div class="arch-box">Aggregation</div>
      <div class="arch-box">Normalization</div>
      <div class="arch-box">Feature Eng.</div>
    </div>
    <div class="arch-arrow">→</div>
    <div class="arch-stage">
      <div class="arch-stage-title">Store</div>
      <div class="arch-box">Data Lake</div>
      <div class="arch-box">Data Warehouse</div>
      <div class="arch-box">Search Index</div>
      <div class="arch-box">Cache</div>
    </div>
    <div class="arch-arrow">→</div>
    <div class="arch-stage">
      <div class="arch-stage-title">Serve</div>
      <div class="arch-box">REST API</div>
      <div class="arch-box">BI Dashboard</div>
      <div class="arch-box">ML Models</div>
      <div class="arch-box">Reports</div>
    </div>
  </div>
</div>
