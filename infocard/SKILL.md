---
name: infocard
description: Create editorial-style information cards using HTML/CSS embedded directly in Markdown. Best for knowledge summaries, data highlights, topic overviews, event announcements, and content cards with magazine-quality typography and layout. NOT for architecture diagrams (use architecture), process diagrams (use uml), or data visualization (use vega).
metadata:
  author: Infocard Generator is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Infocard Generator

**Quick Start:** Analyze content (density × structure × mood) → Auto-sense tone for color palette → Pick a layout skeleton → Embed HTML directly in Markdown with `<style scoped>`.

## Critical Rules

### Rule 1: Direct HTML Embedding
**IMPORTANT**: Write info cards as direct HTML in Markdown. **NEVER** use code blocks (` ```html `). The HTML should be embedded directly in the document without any fencing.

### Rule 2: No Empty Lines in HTML Structure
**CRITICAL**: Do NOT add any empty lines within the HTML info card structure. Keep the entire HTML block continuous to prevent parsing errors.

### Rule 3: Content Analysis Before Layout
**REQUIRED**: Analyze content along three dimensions before designing:

**Density** (determines breathing rhythm):

| Density | Content Volume | Visual Treatment |
|---------|---------------|-----------------|
| Low | ≤ 50 words core | "Big-character" composition. One oversized element dominates. Generous whitespace. |
| Medium | 50–200 words | Hero + supporting panels. 2–3 main blocks with clear hierarchy. |
| High | 200+ words | Asymmetric multi-column grids. Primary/secondary/supporting blocks. Never equal-weight tiles. |

**Structure** (determines layout geometry):

| Structure | Signal | Layout Pattern |
|-----------|--------|---------------|
| Single point | One core concept | One anchor element dominates, rest recedes |
| Contrast | A vs B, old vs new | Split panel, two poles |
| Hierarchy | Layers build on each other | Stacked modules, pyramid |
| Flow | Sequential steps | Vertical cascade, numbered items |
| Radial | Core + derivatives | Hub with surrounding panels |
| Parallel | Multiple equal concepts | Asymmetric grid (never equal columns) |

**Mood** (determines color temperature):

| Mood | Visual Feel |
|------|------------|
| Reflective | More whitespace, serif-heavy, lower contrast |
| Sharp | Strong contrast, bold type, vivid accent |
| Warm | Earth tones, rounded feel, gentle rhythm |
| Technical | Monospace accents, grid-like density |

### Rule 4: Tone Sensing
**REQUIRED**: Auto-select color palette based on content topic. Scan content keywords and match the closest tone:

| Content Tone | Background | Accent | Trigger Keywords |
|---|---|---|---|
| Philosophical | `#FAF8F4` | `#7C6853` | cognition, thinking, meaning, philosophy, essence |
| Technical | `#F5F7FA` | `#3D5A80` | architecture, algorithm, system, API, code |
| Literary | `#FBF9F1` | `#6B4E3D` | story, narrative, writing, poetry, character |
| Scientific | `#F4F8F6` | `#2D6A4F` | experiment, data, research, paper, discovery |
| Business | `#F4F3F0` | `#2D6A4F` | market, strategy, growth, finance, investment |
| Creative | `#F6F3F2` | `#B8432F` | design, art, aesthetics, inspiration, creation |
| Default | `#FAFAF8` | `#4A4A4A` | When no clear match — prefer default over wrong match |

When a style template is explicitly chosen, its colors take precedence over tone sensing. Use tone sensing as the default when no style is specified.

### Rule 5: Title Protection
If the user provides a title explicitly, use it as-is for the main headline. Put editorial interpretation into subtitle, summary, or side modules. Do not silently rewrite the user's title.

### Rule 6: Typography Hierarchy
Maintain a clear type scale and use it consistently:
- Hero title: `32px–48px`, weight 700–900, tight letter-spacing (`-0.02em`)
- Subtitle / summary: `16px–20px`, weight 400–500
- Body text: `14px–16px`, weight 400, line-height `1.6–1.7`
- Meta / tags / captions: `11px–13px`, weight 500–700, uppercase with letter-spacing
- Body text color: never pure black — use `#1a1a1a`, `#333`, or `#4a4a4a`

### Rule 7: Visual Weight Distribution
At least one module should feel visually heavier than the others. Avoid making every panel use the exact same treatment. Differentiate through scale, background tone, typographic weight, or accent rules.

### Rule 8: Taste Rules (Anti-AI Checklist)
Before finalizing any card, check against these common AI-generated visual patterns:

**Layout:**
- **No centered hero** — Do not default-center titles. Prefer left-aligned or asymmetric
- **No equal-width tiles** — Three equal columns side by side is the #1 AI signature. Use `2fr 1fr`, asymmetric grids, or staggered layouts
- **No uniform panels** — At least one panel must differ in scale, weight, or treatment

**Typography:**
- **No pure black** `#000000` — Use off-black (`#1a1a1a`, `#2d2a26`) or warm/cool dark
- **No oversized-only hierarchy** — Build hierarchy with weight and color, not just font-size scaling

**Color:**
- **Max 1 accent color**, saturation < 80%
- **No neon gradients** — No purple-blue AI glow, no gradient-filled headlines
- **Consistent temperature** — Do not mix warm gray and cool gray in one card

**Content:**
- **No filler data** — Avoid `99.99%`, `50%`, `1234567`. Use organic numbers (`47.2%`, `3.8M`)
- **No AI phrasing** — Avoid "empower", "seamless", "unleash", "next-generation"

**Spacing:**
- Padding and margins must be mathematically precise, no awkward gaps
- Adjacent elements must be visually aligned

## Style Examples

Choose a visual style that matches the content's tone. Each example contains a complete, copy-ready HTML template.

| # | Style | File | Suitable For |
|---|---|---|---|
| 1 | **Editorial Warm** | [styles/editorial-warm.md](styles/editorial-warm.md) | Knowledge summaries, book notes, essays, analytical reports |
| 2 | **Clean Modern** | [styles/clean-modern.md](styles/clean-modern.md) | Product launches, tech announcements, startup pitches |
| 3 | **Bold Contrast** | [styles/bold-contrast.md](styles/bold-contrast.md) | Data highlights, KPI dashboards, event announcements |
| 4 | **Soft Neutral** | [styles/soft-neutral.md](styles/soft-neutral.md) | Lifestyle content, wellness, education, gentle branding |
| 5 | **Slate Chalk** | [styles/slate-chalk.md](styles/slate-chalk.md) | Teaching content, lessons, concept explanations, workshop notes |
| 6 | **Paper Minimal** | [styles/paper-minimal.md](styles/paper-minimal.md) | Product notes, task summaries, meeting notes, clean documentation |
| 7 | **Retro Vintage** | [styles/retro-vintage.md](styles/retro-vintage.md) | Brand stories, historical summaries, cultural content, heritage topics |
| 8 | **Tech Blueprint** | [styles/tech-blueprint.md](styles/tech-blueprint.md) | Technical specs, system design docs, architecture summaries, engineering plans |
| 9 | **Deep Night** | [styles/deep-night.md](styles/deep-night.md) | Entertainment, creative showcases, product reveals, gaming content |
| 10 | **Wash Pastel** | [styles/wash-pastel.md](styles/wash-pastel.md) | Lifestyle content, creative workshops, wellness topics, artistic portfolios |
| 11 | **Lab Journal** | [styles/lab-journal.md](styles/lab-journal.md) | Research summaries, scientific explanations, medical content, academic papers |
| 12 | **Navy Formal** | [styles/navy-formal.md](styles/navy-formal.md) | Investor decks, executive briefs, quarterly reports, corporate proposals |

## Layout Skeletons

Choose a layout that fits your content structure. Layouts are style-agnostic wireframes.

| # | Layout | File | Best For |
|---|---|---|---|
| 1 | **Hero Card** | [layouts/hero-card.md](layouts/hero-card.md) | Single topic with title + summary + one supporting panel |
| 2 | **Split Panel** | [layouts/split-panel.md](layouts/split-panel.md) | Two-column layouts: main content + sidebar or left-right comparison |
| 3 | **Stacked Modules** | [layouts/stacked-modules.md](layouts/stacked-modules.md) | Multi-section vertical flow with mixed-weight blocks |
| 4 | **Data Highlight** | [layouts/data-highlight.md](layouts/data-highlight.md) | Numbers-first cards with oversized metrics and supporting context |
| 5 | **Versus Split** | [layouts/versus-split.md](layouts/versus-split.md) | A vs B side-by-side comparison with central divider |
| 6 | **Timeline Flow** | [layouts/timeline-flow.md](layouts/timeline-flow.md) | Sequential steps, milestones, process stages with vertical timeline |
| 7 | **Bento Grid** | [layouts/bento-grid.md](layouts/bento-grid.md) | Multi-topic overviews, feature showcases, mixed-size grid cells |
| 8 | **Quote Card** | [layouts/quote-card.md](layouts/quote-card.md) | Pull-quotes, mission statements, keynote quotes with attribution |
| 9 | **Radial Hub** | [layouts/radial-hub.md](layouts/radial-hub.md) | Ecosystem overviews, core-plus-features, hub-and-spoke relationships |
| 10 | **Funnel Stack** | [layouts/funnel-stack.md](layouts/funnel-stack.md) | Sales funnels, conversion flows, recruitment pipelines, decision narrowing |
| 11 | **Badge Grid** | [layouts/badge-grid.md](layouts/badge-grid.md) | Feature lists, capability catalogs, skill inventories, benefit showcases |
| 12 | **Metric Board** | [layouts/metric-board.md](layouts/metric-board.md) | Performance dashboards, quarterly reviews, health checks, KPI summaries |

## Design Principles

### Space and Breathing Room
- Card padding: `32px–48px` from edges
- Module gaps: `16px–24px`
- Title area must have generous line-height (`1.1–1.3`) and clear separation from body
- Never crowd content against card edges

### Visual Accents
- Use `4px–6px` thick rules as section dividers or accent borders
- Use subtle tinted backgrounds (`rgba(0,0,0,0.03)` or style-specific tints) for secondary panels
- Accent colors should be restrained: one highlight color used for rules, tags, or key numbers
- Optional: `4%` noise overlay for paper texture (see style templates)

### Content Rhythm
- High-density cards: group into overview → core judgment → supporting modules → conclusion
- Ranking content: asymmetric hero + structured list (avoid equal tiles)
- Tutorial/analysis content: overview → core insight → detail blocks → boundary/caveats → summary

## Styling Reference

### Common Classes (shared across all styles)
- `.card-frame` — outer container with max-width and padding
- `.card` — main card surface with background, padding, and optional noise overlay
- `.card-meta` — meta line (category, date, version) in small uppercase
- `.card-title` — main headline
- `.card-subtitle` — secondary headline or summary
- `.card-bar` — thick accent rule divider
- `.card-body` — body text paragraph
- `.card-body.dropcap` — first paragraph with drop cap initial letter (editorial opening)
- `.card-highlight` — standalone short sentence (< 25 chars) with left accent border for key insights
- `.card-grid` — grid container; `.card-grid-2` for two columns
- `.card-panel` — content panel with border-top accent
- `.card-panel.heavy` — heavier panel with more padding
- `.card-panel.light` — lighter panel with thinner border
- `.card-panel-title` — panel heading in small uppercase
- `.card-panel-text` — panel body text
- `.card-item` — titled content block (label + description pair)
- `.card-item-label` — item title/label
- `.card-tag` — inline tag/badge
- `.card-stat` — oversized number/metric display
- `.card-stat-label` — label beneath a stat
- `.card-divider` — thin horizontal rule between sections
- `.card-footer` — bottom strip for source, attribution, or notes
- `.card-endmark` — end-of-content mark (∎) for editorial closure

### Rich Text Elements

**Drop cap** (first paragraph only — creates editorial opening ceremony):
```html
<p class="card-body dropcap">First paragraph text...</p>
```

**Highlight quote** (standalone insight, < 25 chars, with accent left border):
```html
<p class="card-highlight">Key insight phrase</p>
```

**Titled item** (label + description pairs, for structured lists):
```html
<div class="card-item">
  <p class="card-item-label">Item Title</p>
  <p class="card-panel-text">Item description text.</p>
</div>
```

**Section divider**:
```html
<div class="card-divider"></div>
```

**End mark** (editorial closure, placed at content end):
```html
<span class="card-endmark">∎</span>
```

## Best Practices

### Content Guidelines
1. **Direct embedding only** — Always embed HTML directly in Markdown, never use ` ```html ` code blocks
2. **No empty lines in structure** — Keep the entire HTML block continuous
3. **Judge density first** — Decide low/medium/high before picking layout
4. **Protect user titles** — Never silently rewrite a user-provided headline
5. **Balance visual weight** — At least one heavy block, one medium, one light
6. **Use type scale consistently** — Follow the size hierarchy defined above
7. **Accent with restraint** — One accent color, used sparingly for rules and highlights
8. **Fill space intentionally** — If a section looks empty, restructure hierarchy before adding filler content
