# Editorial Warm Style

**Style**: Warm paper background, serif titles, noise texture, thick accent rules, magazine-quality typography
**Best for**: Knowledge summaries, book notes, essays, analytical reports

## Style Characteristics

| Property | Value |
|---|---|
| Background | Warm paper `#f5f3ed` |
| Text | High-contrast ink `#111111` |
| Accent | Black `#111111` (rules, tags) |
| Muted | `#575757` (meta, captions) |
| Tint | `rgba(0,0,0,0.03)` (panel backgrounds) |
| Title Font | `Noto Serif SC`, serif — weight 700/900 |
| Body Font | `Inter`, `Noto Sans SC`, sans-serif |
| Noise | 4% radial-gradient overlay for paper texture |
| Rules | 6px solid accent for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #f5f3ed; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #111; line-height: 1.6; }
    .card::before { content: ''; position: absolute; inset: 0; pointer-events: none; opacity: 0.04; background-image: radial-gradient(circle at 20% 20%, rgba(0,0,0,0.8) 0.5px, transparent 0.8px), radial-gradient(circle at 80% 40%, rgba(0,0,0,0.7) 0.4px, transparent 0.7px); background-size: 8px 8px, 11px 11px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #575757; }
    .card-title { margin: 0 0 16px; font-family: 'Noto Serif SC', serif; font-size: 36px; font-weight: 900; line-height: 1.15; letter-spacing: -0.02em; color: #111; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #333; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #111; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(0,0,0,0.03); border-top: 6px solid #111; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #575757; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #333; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: #111; color: #f5f3ed; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; }
    .card-stat { font-family: 'Oswald', sans-serif; font-size: 48px; font-weight: 700; line-height: 1; color: #111; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #575757; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 900 72px/0.82 'Noto Serif SC', Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #111; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #111; padding: 10px 0 10px 18px; border-left: 3px solid #111; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #111; }
    .card-divider { height: 1px; background: rgba(0,0,0,0.1); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #111; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #575757; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Essay · Behavioral Psychology</p>
    <h1 class="card-title">The Paradox of Choice:<br>Why More Is Less</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">Modern consumers face an unprecedented abundance of options. From 175 salad dressings to 285 cookie varieties on a single supermarket shelf, the illusion of freedom through choice masks a deeper psychological burden that erodes satisfaction and fuels regret.</p>
    <p class="card-highlight">Satisfaction peaks at 6 options, then declines</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">The Jam Study</p>
        <p class="card-panel-text">Shoppers offered 24 jam varieties were 10x less likely to purchase than those shown only 6. Excess choice triggers decision paralysis and post-decision doubt.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Key Takeaway</p>
        <p class="card-panel-text">Curate deliberately. Reduce options to meaningful differences. Satisficers — those who accept "good enough" — report higher well-being than maximizers who chase the best.</p>
      </div>
    </div>
    <span class="card-endmark">∎</span>
    <div class="card-footer">Source: Barry Schwartz · The Paradox of Choice · 2004</div>
  </div>
</div>
