---
name: "#13 haz_img review"
overview: How To starts with Why/What — sizes first, then srcset. Read Portis. Then the process. Pico is HAZ default, replaceable. .com later.
session: "2026-09-24"
status: in_progress
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13
core_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/46
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/74
related:
  - https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70
  - https://github.com/hugo-agent-zero/hugo-agent-zero/issues/72
todos:
  - id: process-doc
    content: Write the haz_img process (blog + settings/skill comments). Not more kit knobs.
    status: in_progress
  - id: outline-park
    content: How To on HAZ.com needs a content issue + both agree.
    status: pending
isProject: false
---

# Shortcode: haz_img Explained

This file **is** the How To until we open a HAZ.com content issue and both agree.

---

## Why

One photo file is a bad deal. A phone pulls a huge desktop picture and wastes time and data. A big screen gets a tiny picture and it looks fuzzy.

The browser can choose among several copies of the same picture — but only if we tell it two things:

1. **How wide will this picture be on the page?** That is `sizes`.
2. **How wide is each file we made?** That is `srcset`.

Most front-end people think the magic is `srcset` (the list of files). It isn’t. The list is the menu. `sizes` is the order you place. If you lie about how wide the picture will show, the browser picks the wrong file. Wrong `sizes` → wrong picture, every time.

That is the whole point of `haz_img`: we write `sizes` from the real page (when the layout changes, how wide the text column is, how much of that space the picture should take). Then `srcset` is just the matching files.

**Read this first:** [Eric Portis — Srcset and sizes](https://ericportis.com/posts/2014/srcset-sizes/). If you only remember one thing from it: the browser needs the on-page width (`sizes`) *before* it can use the file list (`srcset`).

## What

You write a normal `<img>` (alt text, the file name, lazy-load if you want). You tell the shortcode how much of the text column the picture should use on phone, tablet, and desktop. HAZ fills in `sizes` and `srcset`. You still own the tag.

HAZ ships a starting point (we like Pico). You can replace the CSS system, the column, the type. Then you copy the new numbers into settings and into the CSS. We are not married to Pico.

---

## How (do this in order)


## 1. Name *when* — breakpoints from the CSS library

**Where:** `settings.haz_img.config.breakpoints` and the matching CSS `@media` stamps (pico-x / child override).

**What:** `min_tablet` / `min_desktop` are the library’s tablet / desktop **viewport** starts. Viewport px. Not a fraction of the column. Not “when the type feels big.”

**HAZ default:** [Pico](https://picocss.com/docs) `md` = **768**, `lg` = **992**. Pico is our opinion — the kit is built so you can swap the library.

**If you swap:** restamp these two YAML numbers **and** the CSS literals. `@media (min-width: var(--x))` is invalid; you must print the px.

**Say this in the post and in the YAML.** The YAML comment must name the library, not just the numbers.

## 2. Set the column (*how-wide*)

**Where:** child CSS `--haz_measure` (sweet, 95% then 90% from `min_tablet`). Echo `content_width` in settings (`68ch` dogfood).

The column is the reading box. It does **not** choose the BPs. Type knobs are parked ([#70](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70)) — do not retune them in this process.

## 3. Inspect that column in px

Wide viewport. Store as `content_width_px`. That number **is** `lg`.

Dogfood: **1065**. Do not cap at `min_desktop` (992). The box can sit north of the desktop BP.

Re-read after any type or measure change.

## 4. Export the ladder

Skill `haz-img-exports`. Size to the **band**. Do not subtract `content_inset`.

```
lg  = content_width_px
sm  = min(lg, round(0.9 × (min_tablet − 1)))
md  = min(lg, round(0.9 × (min_desktop − 1)))
xs  = ½ sm
xl  = 1.5 × lg
xxl = 2 × lg
```

Dogfood: 345 / 690 / 892 / **1065** / 1598 / 2130.

`xl` / `xxl` are density (DPR), not extra BPs.

Optional stored width map vs this formula is parked ([#72](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/72)).

## 5. Author the key (*how much* of the hole)

`key="m{pct}_t{pct}_d{pct}"` (or `m*_d*`). pct ∈ 25 | 50 | 75 | 100. Not extra files.

The shortcode turns **when** (step 1) × **%** (this key) into `sizes` px:

`(min-width: {min_desktop}px) {lg×d%}px, (min-width: {min_tablet}px) {md×t%}px, min({m%}vw, {sm×m%}px)`

Author keeps the `<img>` (alt, class, loading). HAZ only enriches `srcset` / `sizes` / width classes.

## 6. Drop files and look

Page bundle (or `files/`): `stem.jpg` + `stem_{xs…xxl}.jpg`. Sparse is OK.

Staging proof: demo-post-1, `m100_t100_d100`, one `<img>`.

Check **1×** by resizing the window (not device sim): `xs` / `sm` until `min_tablet`, `md` until `min_desktop`, `lg` after. Device sim = same BPs, fatter files.

Markdown `![]()` stays dumb. `<picture>` / art direction is [#6](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/6).

After core → `main`, FF **`v1.x.x`** in the same sitting or Pages serves the old shortcode.

---

## Parked (not this process)

- Fluid type calcs — [#70](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70)
- Widths map in settings — [#72](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/72)
- `hugo.yaml` as a module — site overlay first if we ever do it
- HAZ.com prose — content issue + both agree
