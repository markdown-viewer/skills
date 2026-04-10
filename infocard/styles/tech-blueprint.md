# Tech Blueprint Style

**Style**: Blueprint grid background, monospace accents, engineering schematic feel, technical precision
**Best for**: Technical specs, system design docs, architecture summaries, engineering plans, API overviews

## Style Characteristics

| Property | Value |
|---|---|
| Background | Blueprint blue `#0a1628` |
| Text | Light blueprint `#c8d8ea` |
| Accent | Bright cyan `#00d4ff` |
| Muted | Steel `#5a7a96` |
| Tint | `rgba(0,212,255,0.06)` (panel backgrounds) |
| Title Font | `Inter`, `Noto Sans SC`, sans-serif — weight 700 |
| Body Font | `Inter`, `Noto Sans SC`, sans-serif |
| Grid | 1px cyan grid lines at 8% opacity |
| Rules | 3px solid cyan for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #0a1628; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #c8d8ea; line-height: 1.6; }
    .card::before { content: ''; position: absolute; inset: 0; pointer-events: none; opacity: 0.08; background-image: linear-gradient(rgba(0,212,255,0.5) 1px, transparent 1px), linear-gradient(90deg, rgba(0,212,255,0.5) 1px, transparent 1px); background-size: 24px 24px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.18em; text-transform: uppercase; color: #5a7a96; font-family: 'SF Mono', 'Fira Code', monospace; }
    .card-title { margin: 0 0 16px; font-size: 34px; font-weight: 700; line-height: 1.2; letter-spacing: -0.01em; color: #00d4ff; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #8ab0cc; }
    .card-bar { width: 80px; height: 3px; margin: 0 0 20px; background: #00d4ff; box-shadow: 0 0 8px rgba(0,212,255,0.3); }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #c8d8ea; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(0,212,255,0.06); border-top: 3px solid #00d4ff; border-left: 1px solid rgba(0,212,255,0.15); }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #00d4ff; font-family: 'SF Mono', 'Fira Code', monospace; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #8ab0cc; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: rgba(0,212,255,0.15); color: #00d4ff; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; border: 1px solid rgba(0,212,255,0.25); font-family: 'SF Mono', 'Fira Code', monospace; }
    .card-stat { font-family: 'SF Mono', 'Fira Code', monospace; font-size: 44px; font-weight: 700; line-height: 1; color: #00d4ff; margin: 0; text-shadow: 0 0 12px rgba(0,212,255,0.25); }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #5a7a96; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; font-family: 'SF Mono', 'Fira Code', monospace; }
    .card-body.dropcap::first-letter { font: 700 64px/0.82 'Inter', sans-serif; float: left; margin: 4px 12px 0 -2px; color: #00d4ff; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #c8d8ea; padding: 10px 0 10px 18px; border-left: 3px solid #00d4ff; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #00d4ff; }
    .card-divider { height: 1px; background: rgba(0,212,255,0.15); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #00d4ff; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,212,255,0.15); font-size: 11px; color: #5a7a96; letter-spacing: 0.05em; font-family: 'SF Mono', 'Fira Code', monospace; }
  </style>
  <div class="card">
    <p class="card-meta">SPEC // Infrastructure</p>
    <h1 class="card-title">Event Stream Processing<br>Pipeline Specification</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">The event bus serves as the central nervous system of the platform, ingesting structured events from 14 upstream producers, applying schema validation and enrichment transforms, then routing to downstream consumers via topic-based subscriptions with exactly-once delivery guarantees.</p>
    <p class="card-highlight">Peak throughput: 240K events/sec, P99 latency &lt; 12ms</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">CORE STACK</p>
        <p class="card-panel-text">Apache Kafka 3.7 · Schema Registry (Avro) · Kafka Streams DSL · Dead Letter Queue · mTLS inter-broker · RBAC per-topic ACLs</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">OBSERVABILITY</p>
        <p class="card-panel-text">Consumer lag monitors · Partition skew alerts · End-to-end trace IDs · Retention policy: 72h hot, 30d tiered (S3) · Quarterly capacity review</p>
      </div>
    </div>
    <span class="card-endmark">⬡</span>
    <div class="card-footer">REV 3.1 // Event Bus Architecture // Platform Team 2026</div>
  </div>
</div>
