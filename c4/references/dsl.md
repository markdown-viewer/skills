# Structurizr DSL Reference

Syntax reference for authoring C4 models as code. Load this when you need precise element, relationship, view, or style syntax.

---

## Workspace & Model

```dsl
workspace "Name" "Description" {
    model {
        # elements and relationships
    }
    views {
        # one view per C4 level
    }
}
```

The `workspace` is the top-level container; `model` holds the elements and relationships (the single source of truth); `views` defines which diagrams to render.

---

## Elements

| Type | Syntax | Purpose |
|---|---|---|
| Person | `p = person "Name" "Description" "Tag"` | A human user (internal or external) |
| Software system | `ss = softwareSystem "Name" "Description" "Tag"` | A system in its own right (may be out of scope) |
| Container | `c = container "Name" "Description" "Technology" "Tag"` | A deployable/runtime unit (app, DB, service) |
| Component | `comp = component "Name" "Description" "Technology" "Tag"` | A structural block inside a container |
| Group | `group "Name" { … }` | A visual grouping of elements |
| Deployment node | `node = deploymentNode "Name" "Description" "Tag" { … }` | Physical/cloud infrastructure |
| Infrastructure node | `infra = infrastructureNode "Name" "Description" "Tag"` | A piece of infrastructure (e.g. a database engine) |
| Instances | `softwareSystemInstance` / `containerInstance` | Deployment-specific instances of systems/containers |

Elements can be nested to express ownership (a `container` or `component` is declared inside its parent's `{ … }`):

```dsl
ibs = softwareSystem "Internet Banking System" "…" {
    api = container "API Application" "…" "Java + Spring" {
        controller = component "Account Controller" "Handles account requests." "Spring MVC"
        service    = component "Account Service" "Business logic for accounts." "Java"
    }
}
```

---

## Relationships

```dsl
a -> b "Uses" "HTTPS" "tag1,tag2"
```

| Part | Meaning |
|---|---|
| `a -> b` | Direction (source → destination) |
| `"Uses"` | Description (required) |
| `"HTTPS"` | Technology/protocol (optional) |
| `"tag1,tag2"` | Comma-separated tags (optional) |

**C4 relationship intent is the description** — it should read as a verb phrase ("Makes API calls to", "Reads from and writes to", "Sends payment instructions to"). Omit direction only when it is genuinely bidirectional.

---

## Views

Each view is a named block under `views { }`. The keyword sets the level:

```dsl
views {
    systemContext ibs "System Context" {
        include *            # everything at this level (people + systems)
        autoLayout
    }
    container ibs "Containers" {
        include *            # every container inside ibs
        autoLayout
    }
    component api "API Components" {
        include *            # every component inside the api container
        autoLayout
    }
}
```

| Keyword | Level | Shows |
|---|---|---|
| `systemContext <system>` | 1 — Context | People + software systems |
| `container <system>` | 2 — Containers | Containers within one system |
| `component <container>` | 3 — Components | Components within one container |
| `dynamic <element>` | Dynamic | Ordering of interactions (numbered) |
| `deployment <env>` | Deployment | Deployment nodes + infrastructure |
| `filtered` / `custom` | Custom | Hand-picked elements and relationships |

### Include / exclude

- `include *` — everything at this level (auto-expands to the correct elements).
- `include a b c` — specific elements only.
- `exclude a` — drop an element from an otherwise `*` view.
- `include a -> b` — include a specific relationship.

---

## Styles & Themes

Style elements once by **tag**, not inline:

```dsl
styles {
    element "Person" { shape Person background #08427b color #ffffff }
    element "Software System" { background #1168bd color #ffffff }
    element "Container" { background #438dd5 color #ffffff }
    element "Component" { background #85bbf0 color #000000 }
    relationship "HTTPS" { color #707070 }
}
```

Key style properties: `shape` (Box, RoundedBox, Circle, Ellipse, Hexagon, Person, Cylinder, Folder, Component), `background`, `color` (text), `stroke`, `width`/`height`, `fontSize`, `icon`, `opacity`.

To use a published theme instead of hand-writing styles:

```dsl
views {
    theme https://static.structurizr.com/themes/microsoft-azure-2021.01.26/theme.json
}
```

---

## Properties & Metadata

```dsl
api = container "API Application" "…" "Java" {
    properties {
        "Health Check" "https://api.example.com/health"
    }
    healthcheck "https://api.example.com/health"
}
```

`properties` is a free key/value bag; `healthcheck` is a first-class field.

---

## Includes & Imports

```dsl
!include https://example.com/shared-people.dsl
!include ./software-systems.dsl
!docs ./docs/adrs
```

`!include` pulls in another DSL fragment (inline); `!docs` attaches a folder of Markdown to the workspace for decision logs and supplementary docs.

---

## Exporting (Structurizr CLI)

```bash
# SVG — native browser-based renderer (needs Chromium/headless browser)
structurizr export -workspace workspace.dsl -format svg -output diagrams

# PlantUML — Structurizr dialect or C4-PlantUML dialect
structurizr export -workspace workspace.dsl -format plantuml -output diagrams
structurizr export -workspace workspace.dsl -format plantuml/c4plantuml -output diagrams

# Mermaid
structurizr export -workspace workspace.dsl -format mermaid -output diagrams

# Other formats: dot, d2, json, ilograph, websequencediagrams, static, theme
```

The CLI ships as `structurizr.sh` (from the release zip), a native `structurizr` binary, or the `structurizr/lite` Docker image (which also serves an interactive workspace with the browser renderer).
