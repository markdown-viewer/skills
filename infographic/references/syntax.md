# Infographic Syntax Specification

Complete syntax reference for AntV Infographic DSL.

## Table of Contents
- [Syntax Structure](#syntax-structure)
- [Data Fields](#data-fields)
- [Theme Configuration](#theme-configuration)
- [Icon & Illustration Resources](#icon--illustration-resources)
- [Strict Rules](#strict-rules)
- [Common Errors](#common-errors)

---

## Syntax Structure

### Basic Format

```plain
infographic <template-name>
data
  title Title Text
  desc Description Text
  items
    - label Item Label
      value 12.5
      desc Item description
      icon mdi/rocket-launch
theme
  palette #3b82f6 #8b5cf6 #f97316
```

### Syntax Rules

| Rule | Description | Example |
|------|-------------|---------|
| Entry line | Must start with `infographic <template-name>` | `infographic list-grid-badge-card` |
| Indentation | Two spaces per level | `  items` / `    - label` |
| Key-value | Format: `key value` (space separated) | `label Product Name` |
| Arrays | Use `-` prefix for items | `- label Item1` |
| Blocks | `data` and `theme` are top-level blocks | See example above |

### Nesting Hierarchy

```plain
infographic template-name     # Entry (required)
data                          # Data block (required)
  title xxx                   # Level 1 (2 spaces)
  desc xxx                    # Level 1
  items                       # Level 1
    - label xxx               # Level 2 (4 spaces)
      value 100               # Level 3 (6 spaces)
      desc xxx                # Level 3
      children                # Level 3 (for hierarchy)
        - label xxx           # Level 4 (8 spaces)
theme                         # Theme block (optional)
  palette #fff #000           # Level 1
```

---

## Data Fields

### Root Level Fields (under `data`)

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `title` | string | No | Infographic title |
| `desc` | string | No | Infographic description/subtitle |
| `items` | array | **Yes** | Array of data items |

### Item Fields (under `items`)

| Field | Type | Description | Applicable Templates |
|-------|------|-------------|---------------------|
| `label` | string | Item label/name (required for most templates) | All templates |
| `desc` | string | Description text, supports `\|` separator | All templates |
| `value` | number | **Numeric type**, used for chart calculations | `chart-*`, `sequence-filter-*`, `sequence-funnel-*` |
| `icon` | string | Icon name, format `collection/name` | Templates with icon support |
| `illus` | string | Illustration name (from unDraw) | `*-illus` templates |
| `time` | string | Time label | `sequence-timeline-*` |
| `done` | boolean | Completion status (`true`/`false`) | `list-column-done-list` |
| `children` | array | Child items array, for hierarchy/compare | `compare-*`, `hierarchy-*` |

### TypeScript Definition

```typescript
interface Data {
  title?: string;
  desc?: string;
  items: ItemDatum[];
  illus?: Record<string, string | ResourceConfig>;
  [key: string]: any;
}

interface ItemDatum {
  icon?: string | ResourceConfig;
  label?: string;
  desc?: string;
  value?: number;
  illus?: string | ResourceConfig;
  time?: string;
  done?: boolean;
  children?: ItemDatum[];
  [key: string]: any;
}
```

---

## Theme Configuration

### Preset Themes

```plain
# Use preset theme
theme dark

# Or
theme hand-drawn
```

Available theme names:
- `dark` — Dark theme
- `hand-drawn` — Hand-drawn style

### Custom Palette

```plain
# Method 1: Inline
theme
  palette #3b82f6 #8b5cf6 #f97316

# Method 2: Array format
theme
  palette
    - #3b82f6
    - #8b5cf6
    - #f97316
```

### Stylization (stylize)

```plain
# Hand-drawn style (rough)
theme
  stylize rough
  base
    text
      font-family 851tegakizatsu

# Pattern fill
theme
  stylize pattern

# Gradient fill
theme
  stylize linear-gradient
# Or
theme
  stylize radial-gradient
```

### Complete Theme Example

```plain
infographic list-row-horizontal-icon-arrow
theme dark
  palette
    - #61DDAA
    - #F6BD16
    - #F08BB4
  stylize rough
  base
    text
      font-family 851tegakizatsu
data
  items
    - label Step 1
      desc Start
    - label Step 2
      desc In Progress
    - label Step 3
      desc Complete
```

---

## Icon & Illustration Resources

### Icons

**Source**: [Iconify](https://icon-sets.iconify.design/)

**Format**: `<collection>/<icon-name>`

**Popular Collections**:
| Collection | Prefix | Description |
|------------|--------|-------------|
| Material Design Icons | `mdi/*` | Most commonly used, largest library |
| Font Awesome | `fa/*` | Classic icon library |
| Bootstrap Icons | `bi/*` | Bootstrap style |
| Heroicons | `heroicons/*` | Tailwind style |

**Common Icon Examples**:

| Category | Icons |
|----------|-------|
| Tech | `mdi/code-tags`, `mdi/database`, `mdi/api`, `mdi/cloud`, `mdi/server` |
| Business | `mdi/chart-line`, `mdi/briefcase`, `mdi/currency-usd`, `mdi/bank` |
| Process | `mdi/check-circle`, `mdi/arrow-right`, `mdi/cog`, `mdi/play` |
| People | `mdi/account`, `mdi/account-group`, `mdi/shield-account` |
| Status | `mdi/star`, `mdi/heart`, `mdi/alert`, `mdi/information` |

### Illustrations

**Source**: [unDraw](https://undraw.co/illustrations)

**Format**: Illustration filename (without .svg)

**Usage**: For templates with `*-illus` suffix

**Common Illustrations**:
| Category | Illustration Names |
|----------|-------------------|
| Tech | `coding`, `programmer`, `server`, `cloud-sync` |
| Business | `business-plan`, `team-work`, `analytics` |
| Abstract | `abstract`, `building-blocks`, `connection` |

---

## Strict Rules

### Rule 1: Compare Templates Must Have Exactly 2 Root Nodes

```plain
# ❌ Wrong: 3 or more root nodes
infographic compare-binary-horizontal-underline-text-vs
data
  items
    - label A
    - label B
    - label C    # Error!

# ✅ Correct: Exactly 2 root nodes with children
infographic compare-binary-horizontal-underline-text-vs
data
  items
    - label Option A
      children
        - label Feature 1
        - label Feature 2
    - label Option B
      children
        - label Feature 1
        - label Feature 2
```

### Rule 2: SWOT Template Must Have 4 English Labels

```plain
# ❌ Wrong: Non-English labels
infographic compare-swot
data
  items
    - label 优势
    - label 劣势

# ✅ Correct: English labels (Strengths, Weaknesses, Opportunities, Threats)
infographic compare-swot
data
  items
    - label Strengths
      children
        - label Technical leadership
        - label Brand awareness
    - label Weaknesses
      children
        - label High costs
        - label Limited coverage
    - label Opportunities
      children
        - label Market expansion
        - label Digital transformation
    - label Threats
      children
        - label Intense competition
        - label Policy risks
```

### Rule 3: hierarchy-structure Supports Max 3 Levels

```plain
# ✅ Correct: 3-level structure
infographic hierarchy-structure
data
  items
    - label Level 1 (Root)          # Level 1
      children
        - label Level 2 (Group)     # Level 2
          children
            - label Level 3 (Item)  # Level 3 (deepest)
```

### Rule 4: Value Field Must Be Numeric

```plain
# ❌ Wrong
- label Revenue
  value "40%"      # String
  value 40%        # With unit

# ✅ Correct
- label Revenue
  value 40         # Pure number
  desc 40% | +5%   # Put units in desc
```

### Rule 5: Icon Format Must Be collection/name

```plain
# ❌ Wrong
icon star
icon mdi-star
icon mdi:star

# ✅ Correct
icon mdi/star
icon fa/check
icon bi/arrow-right
```

---

## Common Errors

### Indentation Errors

```plain
# ❌ Wrong: Using Tab or inconsistent spaces
data
	title xxx          # Tab
   items              # 3 spaces

# ✅ Correct: Use 2 spaces consistently
data
  title xxx
  items
```

### Array Item Format Errors

```plain
# ❌ Wrong
items
  label Item1        # Missing `-`
  -label Item2       # No space after `-`

# ✅ Correct
items
  - label Item1
  - label Item2
```

### Field Level Errors

```plain
# ❌ Wrong: value not at same level as label
items
  - label Item
value 100            # Wrong level

# ✅ Correct
items
  - label Item
    value 100        # Same level as label (as item property)
```

### Template Name Errors

```plain
# ❌ Wrong
infographic list_grid_badge_card    # Underscore
infographic ListGridBadgeCard       # CamelCase
infographic list-grid-badge         # Incomplete

# ✅ Correct
infographic list-grid-badge-card    # Complete kebab-case
```

---

## Generation Workflow

1. **Analyze Content** — Extract title, description, items and hierarchy
2. **Select Template** — Match appropriate template based on information type
3. **Organize Data** — Provide necessary fields for each item
4. **Add Theme** — If user specifies style or colors
5. **Validate Syntax** — Check indentation, field types, template rules

## Output Requirements

- Output only `infographic` code block
- No explanatory text
- Preserve user's input language (Chinese content → Chinese output)
