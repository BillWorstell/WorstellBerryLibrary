# BookCase01 · Shelf0

This folder holds the **per-volume Markdown notes** for Shelf 0 of BookCase01, plus a shelf spreadsheet and helper assets for MkDocs.

## What’s here

- `index.md` — the shelf landing page with links to every volume on this shelf
- `*.md` — one file per volume (see the list on `index.md`)
- `BookCase01Shelf0.xlsx` — working spreadsheet for this shelf
- `Volumes.csv` — optional flat export for scripting
- `Shelf0.jpg` — a photo of the shelf (used by `index.md`)

## Conventions

- **One file per book.** Filenames are short, human-readable (e.g., `JohnAdams_McCullough.md`).
- Each file begins with YAML front matter (metadata) followed by the narrative sections (hook, overview, ToC, author/perspective, reception, scope/style, readership, UDC tags, etc.).
- Images referenced inside a volume file are stored alongside the file and linked **relatively**.

## Quick tips (VS Code)

- Toggle preview: **Ctrl+Shift+V** (or `⌘+Shift+V` on macOS)
- Open preview side-by-side: **Ctrl+K, then V**
- MkDocs live preview (from repo root):
  ```bash
  mkdocs serve
