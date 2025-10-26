This is a great next step. Below is a **copy-paste prompt** you can use in a new chat to generate one Markdown file per book (based on a single row from your Catalog). It explains the purpose, method, format, and style, and includes a concrete template with all the sections you asked for (plus a few helpful extras).

---

# 📄 Prompt for successor chat (copy everything in this box)

You are helping me build a public, browsable catalog of my home library using MkDocs.
For **one book at a time**, generate a single Markdown (`.md`) page that is accurate, concise, and compelling.

## Inputs

* I will provide **one row** from my Catalog table (columns include: `VolumeID, Title, Subtitle, Author(s), Editor/Translator, Series, VolumeNo, Edition, PubYear, Publisher, PubCity, ISBN, Format, Pages, Height_mm, Width_mm, Thickness_mm, Condition, BookCase, Shelf, Section, Position, Tags, Photo_TitlePage, Photo_Spine, Photo_Cover, Notes`).
* Only use what is explicitly provided or what is clearly common knowledge about the book/author; **do not invent** details. If information is missing, mark it as `TBD` and keep going.

## Output requirements

* Produce **one Markdown file** that follows the template below.
* Include a **YAML front matter** block so MkDocs can generate navigation and search facets.
* Write with clarity and economy; aim for 500–900 words unless the book merits more.
* Tone: welcoming, informed, non-academic but precise. Avoid hype.

## File naming

* **Suggested filename (slug)**:
  `{VolumeID}__{safe-title}.md`
  where `safe-title` is lowercased, ASCII, words separated by dashes, 60 chars max (e.g., `BC01-S01-013__the-big-burn.md`).

## Suggested page title

* `{Title}` + (optional `: Subtitle`) + `—` + `{Author(s)}` + ` ({PubYear})`

## YAML front matter (make sure keys exist even if values are empty)

```yaml
---
volume_id: "{{VolumeID}}"
title: "{{Title}}"
subtitle: "{{Subtitle}}"
authors: "{{Author(s)}}"
editors_translators: "{{Editor/Translator}}"
series: "{{Series}}"
series_volume: "{{VolumeNo}}"
edition: "{{Edition}}"
publisher: "{{Publisher}}"
pub_city: "{{PubCity}}"
pub_year: "{{PubYear}}"
isbn: "{{ISBN}}"
format: "{{Format}}"
pages: "{{Pages}}"
dimensions_mm:
  height: "{{Height_mm}}"
  width: "{{Width_mm}}"
  thickness: "{{Thickness_mm}}"
condition: "{{Condition}}"
location:
  bookcase: "{{BookCase}}"
  shelf: "{{Shelf}}"
  section: "{{Section}}"
  position: "{{Position}}"
tags: ["{{Tags}}"]        # split semicolon-separated tags into a list if present
images:
  title_page: "{{Photo_TitlePage}}"
  spine: "{{Photo_Spine}}"
  cover: "{{Photo_Cover}}"
classification:
  udc_primary: ""         # main UDC number (e.g., 94(73) or 929 for biography)
  udc_secondary: []       # up to 2–3 more UDC numbers
  notes: ""
crossrefs: []             # slugs or VolumeIDs of related items
last_verified: "{{today}}"
---
```

## Body template (fill each section realistically; use bullets where helpful)

### Why read this

A short hook (2–4 sentences) that **invites** a general reader: what’s at stake, why it matters now, and who will enjoy it.

### What it’s about (concise overview)

One tight paragraph (5–8 sentences) that explains the book’s scope, argument/narrative arc, and time/place coverage. Avoid spoilers for memoirs/novels; for history, summarize the core thesis or contribution.

### Table of contents (if readily available)

* If a chapter list is visible or provided, render as a bulleted list.
* Otherwise write `TBD`.

### Author & perspective

* 3–6 sentences on the author/editor: role, expertise, vantage point, likely biases, and the work’s historical context (time written vs. time covered).
* If an anthology/edition, clarify editor’s contribution (intro, notes, maps, selection).

### Reception & impact

* Briefly summarize how the work was received (awards, notable reviews, influence on scholarship/public debate).
* Cite only what is common knowledge or present in the book materials; else mark `TBD`.

### Scope & style

* Scope (period, geography, themes).
* Method/style (archival narrative, popular history, biography, policy analysis, etc.).
* Reading experience (dense/accessible, maps/figures/notes presence).

### Publication & readership

* Type (hardback/paperback, trade/academic, edition).
* Intended/likely audience (general readers, students, specialists).
* Any notable apparatus (index, bibliography, maps, photos).

### UDC subject classification (searchable)

Provide **1–3 UDC numbers** most relevant to the book, from general → specific, plus place auxiliaries if apt.
Format like this:

* **Primary**: `94(73)` United States history (example)
* **Secondary**: `929` Biography; `502/504` Environmental science & conservation (examples)
* **Notes**: short rationale (“biography of a U.S. president during conservation movement”).
  If unsure, suggest candidates and mark as `TBD`.

### At-a-glance facts

* Year: {{PubYear}} | Pages: {{Pages or TBD}} | Format: {{Format}} | ISBN: {{ISBN or TBD}}
* Dimensions (mm): H {{Height_mm or TBD}} × W {{Width_mm or TBD}} × T {{Thickness_mm or TBD}}
* Shelf location: {{BookCase}} › Shelf {{Shelf}} › Section {{Section}} › Pos {{Position}}

### Related items in this library

* List 2–6 **likely** related volumes (by author, era, theme) using `VolumeID` if known; otherwise add `TBD`.

### Notes

Include any catalog notes or caveats that were in the row.

## UDC quick-reference (for this collection’s common topics)

*(Use as hints; adjust per the full UDC scheme.)*

* **94(73)** United States history (place auxiliary in parentheses for the U.S.)
* **929** Biography
* **32** Politics; **327** International relations; **355/359** Military affairs
* **34** Law; **342.73** U.S. constitutional law (when relevant)
* **502/504** Environmental science & conservation; **630** Forestry & related (for conservation/parks)
* **81’** Language/linguistics (for text editions/translations, if central)
  When in doubt, choose **one** primary number and at most **two** secondary numbers; include a one-line rationale.

## Style rules

* No filler. Prefer short paragraphs, active voice, and concrete nouns.
* Avoid unsourced superlatives. If evidence of prizes/reviews is not in hand, write `TBD`.
* Keep headings exactly as in the template (MkDocs nav/search depends on them).

## Deliverable

Return **only** the final Markdown page (front matter + body). No extra commentary.

**Here is the single Catalog row to use next:**

> *(I will paste one row per run.)*

---

### Extras I recommend adding to each page (optional but useful later)

* **People/Places/Periods** facets in the front matter (arrays): `people:[]`, `places:[]`, `periods:[]`.
* **Edition history** (especially if you own a reprint).
* **Links** to your photos (spine/cover/title page) and to a stable external reference (publisher page or LOC permalink) when you have it.
* **Reading path**: “If you liked this, next try …” (cross-link within your library).

Want me to run this now for a specific volume? Paste one row from your Catalog and I’ll generate the `.md`.
