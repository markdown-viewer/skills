# Chalkboard Style

**Style**: Dark blackboard background, chalk-colored text, hand-drawn feel, educational warmth
**Best for**: Teaching content, lessons, concept explanations, workshop notes, classroom summaries

## Style Characteristics

| Property | Value |
|---|---|
| Background | Dark slate `#1e2226` with subtle noise |
| Text | Chalk white `#e8e4dc` |
| Accent | Warm yellow chalk `#f5d764` |
| Muted | Dusty `#8b9098` |
| Tint | `rgba(255,255,255,0.05)` (panel backgrounds) |
| Title Font | `Noto Serif SC`, serif — weight 700/900 |
| Body Font | `Inter`, `Noto Sans SC`, sans-serif |
| Noise | 6% multi-layer grain for board texture |
| Rules | 4px solid chalk-yellow for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #1e2226; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #e8e4dc; line-height: 1.6; }
    .card::before { content: ''; position: absolute; inset: 0; pointer-events: none; opacity: 0.06; background-image: radial-gradient(circle at 15% 30%, rgba(255,255,255,0.7) 0.3px, transparent 0.6px), radial-gradient(circle at 75% 60%, rgba(255,255,255,0.5) 0.4px, transparent 0.7px); background-size: 6px 6px, 9px 9px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #8b9098; }
    .card-title { margin: 0 0 16px; font-family: 'Noto Serif SC', serif; font-size: 36px; font-weight: 900; line-height: 1.15; letter-spacing: -0.02em; color: #f5d764; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #c8c4bc; }
    .card-bar { width: 80px; height: 4px; margin: 0 0 20px; background: #f5d764; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #e8e4dc; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(255,255,255,0.05); border-top: 4px solid #f5d764; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #f5d764; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #c8c4bc; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: #f5d764; color: #1e2226; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; }
    .card-stat { font-family: 'Oswald', sans-serif; font-size: 48px; font-weight: 700; line-height: 1; color: #f5d764; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #8b9098; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 900 72px/0.82 'Noto Serif SC', Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #f5d764; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #e8e4dc; padding: 10px 0 10px 18px; border-left: 3px solid #f5d764; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #f5d764; }
    .card-divider { height: 1px; background: rgba(255,255,255,0.1); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #f5d764; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(255,255,255,0.1); font-size: 11px; color: #8b9098; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Lesson · Concept Explanation</p>
    <h1 class="card-title">The CAP Theorem in<br>Distributed Systems</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">In the field of distributed computing, the CAP theorem states that a distributed system cannot simultaneously guarantee consistency, availability, and partition tolerance. System designers must choose trade-offs among these three properties.</p>
    <p class="card-highlight">Any networked shared-data system can satisfy at most two of the three guarantees</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Three Guarantees</p>
        <p class="card-panel-text">Consistency (C): All nodes see the same data. Availability (A): Every request receives a response. Partition Tolerance (P): System continues operating during network partitions.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Practical Choices</p>
        <p class="card-panel-text">CP systems: HBase, MongoDB. AP systems: Cassandra, DynamoDB. CA systems do not exist in real networks.</p>
      </div>
    </div>
    <span class="card-endmark">✦</span>
    <div class="card-footer">Source: Distributed Systems · Lecture Notes</div>
  </div>
</div>
