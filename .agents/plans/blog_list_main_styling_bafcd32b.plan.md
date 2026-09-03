---
name: Blog list main styling
overview: "HQ #43 — Phase 1 shipped (section + main card). Phase 2: finish list rows — article teasers, title heading via props.tag (blog = h2), reuse single meta. Follow-on: params.short_desc in meta dl."
todos:
  - id: wrap-section
    content: "Phase 1 — Child: section wrapper around blog_index_000; routes map_layouts_entry"
    status: completed
  - id: main-card-css
    content: "Phase 1 — Core pico-x: copy Pico article card styles onto main only; leave article/section alone"
    status: completed
  - id: prs-smoke-p1
    content: "Phase 1 — Core + child PRs refs #43; Pages smoke /blog/ + singles light+dark"
    status: completed
  - id: list-row-markup
    content: "Phase 2 — article + h2 title prop; reuse single_blog_meta_wrapper (dl/dt/dd)"
    status: completed
  - id: list-row-css
    content: "Phase 2 — light row spacing only; keep haz_blog_meta styles"
    status: completed
  - id: prs-smoke-p2
    content: "Phase 2 — core/child PRs refs #43; Pages smoke"
    status: completed
  - id: summary-intro-later
    content: "Follow-on — params.desc_short / desc_long in meta dl (term Summary/Overview); never .Summary"
    status: completed
isProject: false
session: 2026-09-03
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/43
status: shipped
core_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/24
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/35
related:
  - Phase 1 core https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/22
  - Phase 1 child https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/26
  - Phase 2 core https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/23
  - Phase 2 child https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/29
  - Phase 3 core https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/24
  - Phase 3 child https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/31
  - content desc FM https://github.com/hugo-agent-zero/hugoagentzero_com-content/pull/3
  - meta polish + grid columns child https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/34
  - meta grid child https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/35
---

# Blog list structure + main continuity (HQ #43)

Live: https://hugo-agent-zero.github.io/hugoagentzero_com-content/blog/

## Phasing

| Phase | Status |
|-------|--------|
| **1 — section + main card** | **Shipped** |
| **2 — finish the list rows** | **Shipped** |
| **3 — desc_short / desc_long** | **Shipped** |
| **Meta columns (grid)** | **Shipped** (child #35) |

---

## Phase 1 (done)

- Blog index in `<section class="haz_section--blog">`
- Pico `article` card styles copied onto `main` (nested article/section left alone)

---

## Phase 2 — how the row is built today

Spike markup, not finished composition.

[`hugo_pages_list_000.html`](layouts/_partials/haz/atomic/atoms/hugo_pages_list_000.html) — opens `ul`/`ol`, hardcodes `<li>` around each child partial.

[`hugo_pages_list_item_000.html`](layouts/_partials/haz/atomic/atoms/hugo_pages_list_item_000.html) — **hardcoded**:

```html
<p><a href="…">Title</a> — <time>…</time></p>
<p>summary</p>
<p>Categories: …</p>
<p>Tags: …</p>
```

- Title is **not** a heading and **not** a prop
- No `<article>`
- Date uses wrong context (`.Date` on the dict, not `$context.Date`) — leftover spike smell

sysMan [`blog_pages_list_item_000`](layouts/_partials/child/data/system_manifest/layouts/atoms.yaml) has almost no props.

---

## Phase 2 decisions (locked)

1. **KISS for launch** — one solid row Atomic now; invent `_010` / `_020` later when we need different fields.
2. **`<li><article>…</article></li>`** — teaser is an article; Pico article chrome stays.
3. **Title = heading via `props.tag`** — blog sets **`h2`** (under page `h1`). Default if omitted: `h2`.
4. **Reuse single-post meta, don’t reinvent taxonomies** — drop the POC `Categories:` / `Tags:` `<p>` strings (also fixes the missing space after `Tags:`). Point the row at the same meta stack as singles: [`single_blog_meta_wrapper_000`](layouts/_partials/child/data/system_manifest/layouts/atoms.yaml) → dl / dt / dd (`haz_blog_meta`). sysMan-first: row is mostly **title + meta child**, not a second taxonomy renderer.
5. **Light hierarchy CSS** only if the reused meta needs list-row spacing tweaks — not a parallel meta design.
6. **Graduate the POC** — core Atomic + child props; fix leftover spike bugs (e.g. wrong `.Date` context) as we touch the file.

### Shape (launch)

```text
li
  article
    h2 > a (title)     ← props.tag
    haz_blog_meta …   ← same inst as single: single_blog_meta_wrapper_000
```

Date/byline follow whatever single meta already does — don’t invent a third place.

### Parked (follow-on after Phase 2 list row) — `params.short_desc`

**Do not use Hugo `.Summary`.** Auto-fallback when empty was a blocker.

**Field:** shipped as `params.desc_short` / `params.desc_long` — empty = omit.

**Primary presentation (locked intent):** add to the **blog meta `dl`** (same box as dates/taxonomies) — `dt` label from settings `term` (e.g. “Summary” or “Overview”), `dd` = value. Sites rename the label without renaming the field.

**Also later:** optional heading presentations (single `h2`, list `h3`) reading the same field — not required for first wiring.

**Phase 2 launch:** title + reuse existing meta (no `short_desc` row yet). Next ticket after list row: settings profile + meta Atomic for `short_desc`.

---

## Phase 2 implementation

### Markup (core + child)

- Rewrite list-item Atomic as a thin shell: `<article>` + heading title link (`props.tag`) + `fn_partial` to meta child (not inline category/tag HTML).
- Child: `blog_pages_list_item_000` props `tag: h2`; `children` include meta → `single_blog_meta_wrapper_000` (or equivalent slot name).
- Keep or drop summary in this pass: if single meta doesn’t show summary, prefer **title + meta** for parity; summary can return as its own slot later.
- List parent keeps wrapping `<li>`.

### CSS

- Only what’s needed so teaser + `haz_blog_meta` read as a row inside the list (gap/margin). Reuse existing meta styles.

### Ship

- Core PR + child PR; ref [#43](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/43); pin + Pages.

---

## Test plan (Phase 2)

- [x] `/blog/` each row: `<li><article><h2><a>…</a></h2>` + same dl/dt/dd meta as singles
- [x] No handmade `Categories:` / `Tags:` paragraphs; no `Tags:` spacing glitch
- [x] Outline: one `h1`, post titles `h2`
- [x] Light + dark smoke

---

## Out of scope

- Vanilla starter / Lorem cleanup
- Fuchsia theme
- Reworking single page `<article>` wrappers
- FAQ redesign
