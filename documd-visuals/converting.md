# Converting a document

This skill draws figures **as text in the Markdown**, rendered live by the viewer — editing the block is
editing the figure, and nothing is pre-rendered. The **`documd` CLI** is optional and downstream: it
renders a whole Markdown document to a finished file, converts a diagram source to an image, and pulls a
document's figures out as separate files. Nothing here is needed to *write* or *edit* a figure — reach for
the CLI only when the output is a file, or when a render check is explicitly wanted.

## Running it

Published on npm as **`@markdown-viewer/documd`**, so there is nothing to install:

```bash
npx @markdown-viewer/documd report.md report.docx
npx @markdown-viewer/documd report.md report.pdf
npx @markdown-viewer/documd notes.md book.epub
npx @markdown-viewer/documd architecture.puml architecture.svg
```

Install it once instead, if the same command runs repeatedly:

```bash
npm install -g @markdown-viewer/documd      # provides the `documd` binary
documd report.md report.docx
```

> ⚠️ **Use the scope.** The bare name `documd` on npm belongs to an unrelated package ("markdown object
> notation"). `npx documd` fetches that one, not this CLI, and fails in a way that looks like a bug in
> the document. Always write `@markdown-viewer/documd`, or install globally and call `documd`.

**Requires** Node 18+ and a Chrome/Chromium for the renderer (it bundles `playwright-core`). On a machine
where Chrome is not on the default path, pass `--chrome <path>`.

## Formats

The second positional argument is the output file; the format is inferred from its extension, or set with
`--format`. The input decides which half of the CLI you are using.

| Input | Outputs | What it does |
|---|---|---|
| `.md` · `.markdown` · `.mdown` · `.mkd` · `.txt` | `html` · `epub` · `docx` · `pdf` | Renders the whole document, figures included |
| `SUMMARY.md` with `--book` | `html` · `epub` · `docx` · `pdf` | Whole-book export, following the GitBook summary |
| `.puml` · `.vl` · `.vega` · `.json` … | `svg` · `png` | Renders one diagram source; `--diagram-type` overrides the inferred engine |

## Flags worth knowing

| Flag | Effect |
|---|---|
| `--format <f>` | `html` · `epub` · `docx` · `pdf` · `svg` · `png` — inferred from the output extension when omitted. With `--assets`: `png` or `svg`, the figure's format |
| `-b, --book` | Treat the input as a GitBook `SUMMARY.md` and export the whole book |
| `--assets <dir>` | Export the document's figures and images into `<dir>` instead of a document — see [Exporting the figures](#exporting-the-figures) |
| `--kind <k>` | With `--assets`: `all` (default) · `diagrams` · `images` |
| `--only <list>` | With `--assets`: which assets to write, by number — `1,3` |
| `--fail-on-error` | Exit 1 when a figure or image failed (default) |
| `--no-fail-on-error` | Report the failures but exit 0 |
| `--diagram-type <t>` | Force the diagram renderer instead of inferring it from the file extension |
| `-t, --theme <id>` | Viewer theme for the rendered document — **not** the figure theme; see the note below |
| `--title <text>` | Override the document title |
| `--language <code>` | Document language, for hyphenation and language-dependent layout |
| `--frontmatter <mode>` | `hide` (default) · `table` · `raw` — what to do with the YAML block |
| `--table-layout <mode>` | `left` · `center` · `center-full-width` |
| `--image-layout` / `--diagram-layout` | `left` · `center` |
| `--merge-empty-cells` | Merge empty table cells (on by default) |
| `--first-line-indent <n>` | First-line indent in characters, 0–4 |
| `--chrome <path>` | Explicit Chrome/Chromium executable |
| `--timeout <seconds>` | Overall render timeout (default 120) |

`-t/--theme` sets the **host document's** theme — fonts, page background, table chrome. It has nothing to
do with the figure themes in [`styles/palette.md`](styles/palette.md): a figure carries its own colours
and does not follow the host document. That separation is the point of the theme set, so do not reach for
`-t` to restyle a figure.

## What survives the export

The pipeline renders through a browser, so anything a browser can draw survives — but not everything
survives as *content*:

| Element | In `html` / `epub` | In `docx` / `pdf` |
|---|---|---|
| Diagram engines (`plantuml` · `vega` · `echarts` · `infographic`) | an `<img>` with the rendered figure | a rasterised image |
| Bare-HTML cards and architecture diagrams | live markup | **rasterised** — one image, class names and text gone |
| Markdown tables | a table | a table, reflowed to the page |
| Prose | reflowable text | reflowable text |

Two consequences worth designing around, both already stated in the engine references:

- **Never put a fact only inside a card.** It rasterises on the DOCX/PDF path, so the text is neither
  selectable nor searchable. Repeat the fact in prose.
- **Never rely on remote images or external data.** Fetch and inline them first, or the export ships a
  hole. The CLI now says so instead of shipping it silently — see below.

## Exporting the figures

A document is not always the wanted output: sometimes the figures are. `--assets <dir>` writes every
figure and image a Markdown document shows into a directory — the *rendered* result, so each figure is
named by the engine that drew it and each image is copied byte for byte, never re-encoded.

```bash
documd report.md --assets ./figures                    # every figure and image
documd report.md --assets ./figures --kind diagrams    # figures only
documd report.md --assets ./figures --only 1,3         # by number
documd report.md --assets ./figures --format svg       # figures as SVG, not PNG
```

The report is the index: assets are numbered in document order, and that number is what `--only` takes
back, so a batch can be narrowed to one figure without recounting anything.

```
report.md: 2 diagrams, 1 image (3 assets)
  1  image    icon48.png  line 6   -> report-01-icon48.png
  2  diagram  plantuml    line 8   -> report-02-plantuml.png
  3  diagram  echarts     line 15  skipped
```

The file name is `<document>-<number>-<label>.<ext>`, so a report row and a file always name the same
asset.

`--assets` is a mode of its own and rejects the combinations that have no meaning: the input must be
Markdown (not a diagram source), there is no output-file argument, `--book` is not supported yet, and
`--format` picks the figure payload rather than the document format — `png` (the pixels the page shows,
the default) or `svg`.

> ⚠️ **`--format svg` is not vector for every engine.** `plantuml` · `vega` · `echarts` ·
> `infographic` return a clean SVG with a correct `viewBox`. A **bare-HTML figure** returns the
> rasteriser's internal vehicle instead — a fixed 14000×14000 canvas, the content at
> `transform: scale(4)`, and the `outline: 1px solid #ff0000` that the PNG path uses as a crop marker —
> so the file carries a red border and a large empty margin. Export HTML figures as PNG.

## When a figure fails

A figure that fails to render is not a figure. The CLI reports every failure with its markdown line, its
engine and the engine's own reason — and exits 1, because the document it produced is not the document
the source describes:

```
Render errors (2):
  line 11  echarts  Invalid JSON in echarts option: Unexpected token '}', "{ "series": [ }" is not valid JSON
  line 15  image    Failed to fetch image: assets/missing.png - Unable to read resource (404): ...
```

The output is still written (a failed figure stays visible as an error block, a failed image as a red
placeholder), so the report and the artifact can be read together. Exit status is part of the contract:

| Situation | Exit |
|---|---|
| Every figure and image rendered | 0 |
| A figure or image failed | 1, and the report names each one |
| Same, but `--no-fail-on-error` | 0 — the report is printed, the pipeline is not stopped |

`--no-fail-on-error` exists for batches where one optional figure must not stop a hundred good
conversions. It never silences the report — only the exit code changes.

The split matters to a script: the artifact paths and the asset table go to **stdout**, warnings and the
error report go to **stderr**.

This is also the only way to *check* a figure — never a required step before delivering one. Rendering the
document is the one step that proves a block is valid — a fence that parses but draws the wrong thing, or
a bare-HTML block that silently ended early, is caught here and nowhere else.

## Which to use

| The task | Use |
|---|---|
| A figure inside a document the host application already renders | This skill, and nothing else — the text renders live |
| A `.docx` / `.pdf` / `.epub` of the finished document | `documd`, from a terminal |
| A `.png` or `.svg` of one diagram, for a slide or a ticket | `documd`, with the diagram source as input |
| Every figure and image a document contains, as files | `documd --assets`, see [Exporting the figures](#exporting-the-figures) |
| A whole book with chapters | `documd --book` on a GitBook `SUMMARY.md` |

## Version

The CLI is versioned with the extension, and the npm release carries that same version — so
`npx @markdown-viewer/documd` is the build this page describes, `--assets` and the render-error report
included. A flag rejected as unknown means the installed copy is older than the extension using it.

<!-- Reached from SKILL.md. Every claim here is from `documd --help` and real runs on the built CLI,
     plus the export boundaries recorded in engines/*.md. Verified 2026-09-23 against the published npm
     build: --assets/--kind/--only, the `skipped` rows, the exit-1 failure report and the document
     export's "Render errors (N)" block all match. The Exporting the figures and Render errors blocks
     are copies of a real run on test/fixtures/layout/asset-export.md and asset-export-error.md. -->
