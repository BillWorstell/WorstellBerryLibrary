# WorstellBerryLibrary — Books House Style

> **Purpose.** This stub defines the canonical format for book pages under `docs/books/BookCaseXX/ShelfYY/`.  
> **Goal.** Every image’s textual info must be **redundant** with the Markdown so nothing essential is image‑only.

---

## 1) File & asset naming

- **Markdown file**: `Title_Author.md` (ASCII only; spaces → `_`).
  - Examples: `BigBurn_Egan.md`, `RiverOfDoubt_Millard.md`, `AgeOfReform_Hofstadter.md`.
- **Images** (same folder as the `.md`):
  - Cover: `Title_Author_Cover.jpg`
  - Copyright/CIP: `Title_Author_CopyRight.jpg`
  - TOC scans (one or more): `Title_Author_TOC.jpg`, `Title_Author_TOC2.jpg`, …
  - Optional maps/plates: `Title_Author_Map.jpg`, etc.
- **Alt text** is required and should echo the on‑page text (redundancy rule).

---

## 2) Standard section order (fixed)

1. **H1**: *Title* — Author  
   _Edition short note in italics_ (e.g., `(Bison Books ed., Vol. 1)`)
2. **Cover image**
3. **Why read this**
4. **What it’s about (concise overview)**
5. **Table of contents (from this copy)**  ← include page numbers; one line per item
6. **Author & perspective**
7. **UDC subject classification (for search)**
8. **Publication details (this copy)**  ← with optional copyright/CIP scan in a details block
9. **Related volumes on this shelf**

> Keep this order. Do not insert “Introduction” or “Back matter” sections *above* TOC; instead, place those lines inside the TOC with page numbers.

---

## 3) Header & cover block (paste‑ready)

```md
# The Big Burn — Timothy Egan
*(First Mariner Books ed.)*

![](BigBurn_Egan_Cover.jpg){ loading=lazy }

---
```

- Use an H1 `#`, not bold text.  
- Short edition/series note goes under the title in *italics*.  
- Images default to full width; supply only `loading=lazy` (no explicit sizes unless needed).

---

## 4) Table of contents rules

- **One line per item** with page number(s) at the end:  
  `I · In on the Creation, p. 17`  
  `1. “A Peculiar Intimacy”, p. 17`
- Use **·** (middle dot) between Roman part numbers and titles, **comma** before `p.`.
- Use **en dashes** for year spans (e.g., `1901–1930`), **em dashes** for asides.
- Include **Back matter** items with pages (e.g., `Notes, p. 287 • Acknowledgments, p. 307 • Index, p. 309`).  
  A centered dot `•` may separate multiple back‑matter items on one line.
- If the printed TOC lacks a page for a part title, omit `p.` on that line but include it on chapter lines.

**Example (paste‑ready):**
```md
## Table of contents (from this copy)

I · In on the Creation, p. 17
1. “A Peculiar Intimacy”, p. 17
2. Roost of the Robber Barons, p. 39
3. The Great Crusade, p. 53
4. Deadwood Days, p. 73
5. Showdown, p. 86

II · What They Lost, p. 105
6. Summer of Smoke, p. 105
7. Men, Men, Men!, p. 116
…
Back matter — Notes, p. 287 • Acknowledgments, p. 307 • Index, p. 309
```
> **Reminder:** Don’t wrap TOC into a single paragraph. Each line should render separately.

---

## 5) Collapsible **details** blocks (exact snippet)

Use this **exact** syntax for MkDocs Material with PyMdown’s “details” admonition:

```md
???+ details "Show original TOC scans (optional)"
    ![](BigBurn_Egan_TOC.jpg "Table of contents — page set 1"){ loading=lazy }
    ![](BigBurn_Egan_TOC2.jpg "Table of contents — page set 2"){ loading=lazy }
```

For copyright/CIP page:

```md
??? details "Show copyright / CIP page (scan)"
    ![](BigBurn_Egan_CopyRight.jpg "Copyright / CIP page"){ loading=lazy }
```

- Indent content by **four spaces** (or one tab).  
- Keep the title text **exactly** as above so the site looks consistent.  
- Add more TOC images as additional lines inside the same block.

> If your site config prefers fenced‑block style, the alternative is:
> ```md
> ::: details Show original TOC scans (optional)
> ![](…TOC.jpg)
> :::
> ```
> But **default is the `???` form above**.

---

## 6) Author & perspective

A short (2–4 sentences) note about the author, the era/purpose of the work, and any known interpretive stance or bias that readers should keep in mind.

---

## 7) UDC subject classification (for search)

Use this bullet structure for quick scanning and sidebar snippets:

```md
**Primary:** 94(73) — U.S. history (specify era/topic)  
**Secondary:** 502 — Environmental impact; 630 — Agriculture (as needed)  
**Tags:** Theodore Roosevelt • U.S. Forest Service • Conservation • Wildfire
```

- Keep **Primary / Secondary / Tags** order.  
- Tags are **plain text bullets** separated by `•` (not commas).

---

## 8) Publication details (this copy)

Provide only what your physical copy shows, using this pattern:

```md
Bison Books (University of Nebraska Press) paperback reprint, 1994 — reissue of the 1870 revised text (orig. 1851).  
Introduction: Michael N. McConnell. ISBN: 0‑8032‑8733‑X (v. 1, pbk.); 0‑8032‑8737‑2 (v. 2, pbk.).

??? details "Show copyright / CIP page (scan)"
    ![](ConspiracyOfPontiac_Parkman_CopyRight.jpg "Copyright/CIP page — Bison Books ed."){ loading=lazy }
```

---

## 9) Related volumes on this shelf

Use a short list of nearby books with **subtitle on the next indented line** for readability:

```md
- [River of Doubt (Millard)](../RiverOfDoubt_Millard/)  
  Theodore Roosevelt’s Darkest Journey
- [The Worst Hard Time (Egan)](../WorstHardTime_Egan/)  
  The Untold Story of Those Who Survived the Great American Dust Bowl
```

> Links are **relative** to the current shelf folder.

---

## 10) Minimal template (paste this to start a new page)

```md
# <Title> — <Author>
*(<Edition/series note, if any>)*

![](<Title_Author>_Cover.jpg){ loading=lazy }

## Why read this
<2–4 lines on significance and use.>

## What it’s about (concise overview)
<3–6 lines covering scope/time/place, main through‑line, and how to read it.>

## Table of contents (from this copy)
<One line per item, with page numbers.>

???+ details "Show original TOC scans (optional)"
    ![](<Title_Author>_TOC.jpg){ loading=lazy }

## Author & perspective
<Short author blurb + perspective/bias note.>

## UDC subject classification (for search)
**Primary:** <code and label>  
**Secondary:** <code(s)>  
**Tags:** a • b • c

## Publication details (this copy)
<Publisher, year, series/intro, ISBNs (from this copy).>

??? details "Show copyright / CIP page (scan)"
    ![](<Title_Author>_CopyRight.jpg){ loading=lazy }

## Related volumes on this shelf
- [<Neighbor 1>](../<Neighbor1>/)  
  <Subtitle>
- [<Neighbor 2>](../<Neighbor2>/)  
  <Subtitle>
```

---

## 11) Pre‑commit QA checklist

- [ ] File lives in the correct shelf folder; filename matches `Title_Author.md`.
- [ ] Cover/CIP/TOC image filenames match the pattern and live **next to** the `.md`.
- [ ] TOC: each item on its **own line**; page numbers included; punctuation/style correct.
- [ ] Details blocks use the **`??? details`** syntax with proper indentation.
- [ ] All images have descriptive **titles/alt**; all textual info is **duplicated in Markdown**.
- [ ] “Related volumes” list uses relative links and next‑line subtitles.
- [ ] Spelling (en/em dashes), italic edition note, and section order verified.
