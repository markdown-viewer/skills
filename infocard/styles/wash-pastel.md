# Wash Pastel Style

**Style**: Soft watercolor-inspired palette, organic warmth, gentle pastel tints, hand-painted feel
**Best for**: Lifestyle content, creative workshops, wellness topics, personal stories, artistic portfolios

## Style Characteristics

| Property | Value |
|---|---|
| Background | Warm cream `#faf8f0` |
| Text | Warm charcoal `#3d3d3d` |
| Accent | Soft coral `#e07a5f` |
| Secondary | Sage green `#87a96b` |
| Muted | Dusty mauve `#9a8c8c` |
| Tint | `rgba(224,122,95,0.08)` (warm panel backgrounds) |
| Title Font | Georgia, `Noto Serif SC`, serif — weight 700 |
| Body Font | `Inter`, sans-serif |
| Texture | Subtle warm grain overlay |
| Rules | 4px solid coral for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #faf8f0; padding: 40px; overflow: hidden; font-family: 'Inter', sans-serif; color: #3d3d3d; line-height: 1.65; }
    .card::before { content: ''; position: absolute; inset: 0; pointer-events: none; opacity: 0.035; background-image: radial-gradient(circle at 25% 35%, rgba(160,100,60,0.7) 0.3px, transparent 0.6px), radial-gradient(circle at 65% 75%, rgba(160,100,60,0.5) 0.4px, transparent 0.7px); background-size: 9px 9px, 12px 12px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: #e07a5f; }
    .card-title { margin: 0 0 16px; font-family: Georgia, 'Noto Serif SC', serif; font-size: 34px; font-weight: 700; line-height: 1.2; color: #3d3d3d; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.6; color: #6b6b6b; }
    .card-bar { width: 60px; height: 4px; margin: 0 0 20px; background: #e07a5f; border-radius: 2px; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.65; color: #4a4a4a; }
    .card-grid { display: grid; gap: 14px; }.card-grid-2 { grid-template-columns: 1fr 1fr; }
    .card-panel { padding: 16px 18px; background: rgba(224,122,95,0.08); border-top: 4px solid #e07a5f; border-radius: 0 0 6px 6px; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: #87a96b; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.6; color: #6b6b6b; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 3px 10px; background: rgba(135,169,107,0.15); color: #6b8f55; border-radius: 12px; margin-right: 6px; margin-bottom: 4px; }
    .card-stat { font-size: 44px; font-weight: 700; line-height: 1; color: #e07a5f; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #9a8c8c; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 64px/0.82 Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #e07a5f; }
    .card-highlight { font-size: 16px; font-weight: 500; line-height: 1.5; color: #3d3d3d; padding: 10px 0 10px 16px; border-left: 3px solid #87a96b; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #e07a5f; }
    .card-divider { height: 1px; background: rgba(0,0,0,0.07); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #87a96b; opacity: 0.4; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.07); font-size: 11px; color: #9a8c8c; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Craft · Fermentation</p>
    <h1 class="card-title">The Slow Art of<br>Sourdough Bread</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">A living culture of wild yeast and lactobacilli, maintained through daily feeding, transforms flour and water into something no factory can replicate. The 72-hour fermentation breaks down gluten, develops complex organic acids, and produces a crumb structure that carries the signature of its maker.</p>
    <p class="card-highlight">Good bread needs only flour, water, salt, and patience</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">The Starter</p>
        <p class="card-panel-text">Equal parts flour and water, fed every 24 hours for 7 days. By day 5 it doubles in volume within 4 hours. The aroma shifts from sharp acetone to sweet yogurt.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">The Bake</p>
        <p class="card-panel-text">Bulk ferment at 24°C for 5 hours, shape, cold retard overnight. Bake in a preheated Dutch oven at 245°C — steam for the first 20 minutes, then dry heat for the crust.</p>
      </div>
    </div>
    <span class="card-endmark">❋</span>
    <div class="card-footer">Notes from the Kitchen · Artisan Baking Series</div>
  </div>
</div>
