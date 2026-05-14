---
name: remark
description: Use Remark Mode in Markdown Viewer for block-level annotation and AI-structured review. Human annotates with semantic colors, exports structured feedback, AI applies changes by line reference.
metadata:
  author: Remark Mode is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Remark Mode — Block-Level Annotation for AI Review

## Setup (one-time)

Install [Markdown Viewer](https://chromewebstore.google.com/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk) extension, then enable file access:
- Chrome/Edge: `chrome://extensions/` → "Markdown Viewer" → **"Allow access to file URLs"** ON

## Opening Files in Remark Mode

Append `?remarker=true` to auto-activate annotation mode.

**⚠️ macOS**: `open -a` strips query strings from `file://` URLs. Use `osascript`:

```bash
# macOS (Chrome)
osascript -e 'tell application "Google Chrome" to open location "file:///path/to/file.md?remarker=true"'

# macOS (Edge)
osascript -e 'tell application "Microsoft Edge" to open location "file:///path/to/file.md?remarker=true"'

# Linux
google-chrome "file:///path/to/file.md?remarker=true"

# Windows
start chrome "file:///C:/path/to/file.md?remarker=true"
```

Without the parameter, user clicks ✏️ in the toolbar manually.

## Export Format

User clicks **📋 Copy remarks** → pastes into AI conversation:

```
I reviewed "filename.md" and have the following feedback:

1. [🟡 Suggestion] L5–L8: "quoted text from the document"
   Note: "reviewer's comment explaining the change"
2. [🔵 Question] L12: "another block of text"
   Note: "why was this approach chosen?"
3. [🩷 Concern] L20–L25: "problematic section here"
   Note: "this might fail under condition X"
4. [🟢 Keep] L30: "well-written explanation"
   Note: "clear and concise, don't touch"
```

## Processing Feedback (for AI agents)

### Color Semantics

| Color | AI Action |
|-------|-----------|
| 🟡 Suggestion | Apply the change described in Note |
| 🟢 Keep | Do NOT modify this section |
| 🔵 Question | Answer the question; revise if needed |
| 🩷 Concern | Fix the issue or explain why it's safe |

### Attribution

After applying changes, report what each annotation caused:

```
- L5–L8 → expanded per [🟡 L5–L8]
- L20 → added error handling per [🩷 L20]
- L30 → unchanged per [🟢 L30]
```

### Iteration

Generate updated file → open again with `?remarker=true` → user annotates again → repeat until user says "OK" / "LGTM" / "好了".

## Key Design Notes

- Annotations are **block-level** (tied to source line numbers via `data-line`), not character-level
- Line references (`L5–L8`) map to source Markdown line numbers
- Multiple annotations on the same block export as separate numbered items
- Media blocks (images, diagrams, SVG) are not annotatable
- Storage is per-file path — each file has independent annotations

