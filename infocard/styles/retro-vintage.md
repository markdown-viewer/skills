# Retro Vintage Style

**Style**: Sepia-warm palette, aged paper feel, poster-print influence, nostalgic warmth
**Best for**: Brand stories, historical summaries, cultural content, retro reviews, heritage topics

## Style Characteristics

| Property | Value |
|---|---|
| Background | Aged parchment `#f2ece0` |
| Text | Dark sepia `#2c221a` |
| Accent | Burnt sienna `#b5543a` |
| Muted | Faded brown `#8a7d6b` |
| Tint | `rgba(181,84,58,0.06)` (warm panel backgrounds) |
| Title Font | `Noto Serif SC`, Georgia, serif — weight 700/900 |
| Body Font | `Inter`, `Noto Sans SC`, sans-serif |
| Noise | 5% multi-layer grain for aged paper texture |
| Rules | 5px solid burnt sienna for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #f2ece0; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #2c221a; line-height: 1.6; }
    .card::before { content: ''; position: absolute; inset: 0; pointer-events: none; opacity: 0.05; background-image: radial-gradient(circle at 30% 25%, rgba(80,50,20,0.8) 0.4px, transparent 0.7px), radial-gradient(circle at 70% 70%, rgba(80,50,20,0.6) 0.3px, transparent 0.6px); background-size: 7px 7px, 10px 10px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #8a7d6b; }
    .card-title { margin: 0 0 16px; font-family: 'Noto Serif SC', Georgia, serif; font-size: 36px; font-weight: 900; line-height: 1.15; letter-spacing: -0.01em; color: #2c221a; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #4a3c2e; }
    .card-bar { width: 80px; height: 5px; margin: 0 0 20px; background: #b5543a; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #2c221a; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(181,84,58,0.06); border-top: 5px solid #b5543a; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #b5543a; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #4a3c2e; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: #b5543a; color: #f2ece0; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; }
    .card-stat { font-family: 'Oswald', sans-serif; font-size: 48px; font-weight: 700; line-height: 1; color: #b5543a; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #8a7d6b; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 900 72px/0.82 'Noto Serif SC', Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #b5543a; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #2c221a; padding: 10px 0 10px 18px; border-left: 3px solid #b5543a; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #b5543a; }
    .card-divider { height: 1px; background: rgba(44,34,26,0.12); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #b5543a; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(44,34,26,0.1); font-size: 11px; color: #8a7d6b; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Cultural Heritage · Retrospective</p>
    <h1 class="card-title">The Golden Age of<br>Radio Broadcasting</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">Between 1920 and 1950, radio transformed from a maritime signaling tool into the living room hearth of modern civilization. Families gathered around wooden cabinets each evening, listening to dramas, comedies, and live news that shaped public opinion across continents.</p>
    <p class="card-highlight">By 1940, 83% of American households owned a radio receiver</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Cultural Impact</p>
        <p class="card-panel-text">Orson Welles' 1938 "War of the Worlds" broadcast proved radio's power to blur fiction and reality. FDR's Fireside Chats pioneered direct political communication with citizens.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Technical Legacy</p>
        <p class="card-panel-text">AM broadcasting, the superheterodyne receiver, and early advertising models laid the groundwork for television, podcasting, and streaming media that followed.</p>
      </div>
    </div>
    <span class="card-endmark">❧</span>
    <div class="card-footer">Source: A History of Broadcasting · Media Archives</div>
  </div>
</div>
