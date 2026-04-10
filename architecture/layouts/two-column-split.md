# Two-Column Split Layout

**Layout**: Two parallel columns for side-by-side comparison
**Best for**: Before/after comparisons, dual-system views, migration architecture

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-split { display: flex; gap: 16px; }
    .arch-column { flex: 1; border: 1px solid #bbb; border-radius: 4px; padding: 14px; background: #fdfdfd; }
    .arch-column-title { font-size: 14px; font-weight: 600; color: #444; text-align: center; margin-bottom: 12px; padding-bottom: 8px; border-bottom: 1px solid #ddd; }
    .arch-layer { margin: 8px 0; padding: 12px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 8px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }.arch-box.tech { font-size: 10px; color: #666; }
  </style>
  <div class="arch-title">Migration Architecture: Legacy → Modern</div>
  <div class="arch-split">
    <div class="arch-column">
      <div class="arch-column-title">Legacy System</div>
      <div class="arch-layer">
        <div class="arch-layer-title">Frontend</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">jQuery App</div><div class="arch-box">Server Pages</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Backend</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Monolith</div><div class="arch-box">SOAP API</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Data</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Oracle DB</div><div class="arch-box">File System</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Infrastructure</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Bare Metal</div><div class="arch-box">Manual Deploy</div></div>
      </div>
    </div>
    <div class="arch-column">
      <div class="arch-column-title">Modern System</div>
      <div class="arch-layer">
        <div class="arch-layer-title">Frontend</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box highlight">React SPA</div><div class="arch-box">Mobile App</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Backend</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box">Microservices</div><div class="arch-box highlight">REST/gRPC</div><div class="arch-box">Event Bus</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Data</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box">PostgreSQL</div><div class="arch-box">Redis</div><div class="arch-box">S3</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Infrastructure</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box">Kubernetes</div><div class="arch-box">Terraform</div><div class="arch-box">CI/CD</div></div>
      </div>
    </div>
  </div>
</div>
