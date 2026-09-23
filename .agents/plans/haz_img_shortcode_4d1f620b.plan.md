---
name: haz_img shortcode
overview: "Implement HQ #13 as a paired `haz_img` shortcode that wraps an author-owned `<img>` and injects `srcset`, `sizes`, and a matching layout class from `settings.yaml` — without re-specifying every HTML attribute."
todos:
  - id: settings-images
    content: Add settings.images.variants + windows (core defaults + child)
    status: pending
  - id: shortcode-haz-img
    content: "Implement paired haz_img.html: parse src, build srcset, inject sizes/class"
    status: pending
  - id: css-windows
    content: Add haz_img__* CSS matching window sizes strings
    status: pending
  - id: demo-proof
    content: Minimal page-bundle variants + one haz_img call for proof
    status: pending
  - id: ship-prs
    content: "Core/child PRs Refs #13; Pages dispatch if live demo"
    status: pending
isProject: false
session: 2026-09-14
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13
status: parked
related:
  - https://github.com/hugo-agent-zero/hugo-agent-zero/issues/49
  - https://ericportis.com/posts/2014/srcset-sizes/
---

# haz_img: srcset + sizes shortcode (#13)

**GOTO (mental model):** [Srcset and sizes — Eric Portis (2014)](https://ericportis.com/posts/2014/srcset-sizes/) — author supplies hole (`sizes`) + blocks (`srcset`/`w`); browser applies viewport + DPR. Retina is not a separate mode.

## Author story

Paired shortcode wraps a normal `<img>`. Author keeps full control of id/class/data-*/alt/loading/etc. HAZ only makes **performance attrs + layout window** easy and correct.

```md
{{< haz_img window="content" >}}
<img src="hero.jpg" alt="Demo hero" loading="lazy">
{{< /haz_img >}}
```

Output (conceptually): same tag, plus `srcset`, `sizes`, and `class` token for that window (merged if `class` already exists).

Plain `![alt](file.jpg)` stays dumb via existing [`render-image.html`](layouts/_markup/render-image.html) — unchanged in this ticket. Opt in to `haz_img` when you care; ignoring it is fine. Either way the kit shows we’re mindful of performance for people who want it.

Not in scope: [`#6`](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/6) `<picture>` / art direction.

## Mental model (locked)

| Piece | Role |
|--------|------|
| **`srcset` + `Nw`** | Asset menu: each file + its pixel width |
| **`sizes`** | Layout “image window” — how wide the img lays out |
| **Window key** | One knob → `sizes` string; **class derived** as `haz_img__{key}` (do not trust authors to sync) |
| **Variants** | Filename suffixes + **pixel widths derived from measure** (not a fixed Pico ladder). Menu can still include 2× rungs; browser skips them when `sizes` is small. |

Same files can serve different windows; only `sizes` (+ derived class) change.

**Scope (core):** mobile-first **single column** in a content measure — not multi-column desktop magazine layouts, not a required full-viewport hero. Viewport-bleed + extra-large rungs are child extensions.

**Design order (locked):**

1. Decide the content measure ceiling from fluid type + line-length/readability (**≤ `45rem`** recommended max; comfort ~65ch / ~36–40rem).
2. Below that ceiling, column is **full available width** (prefer `width: 100%` + horizontal padding gutters — not a perpetual `90%` shrink). Calibrate `--haz_measure` / column CSS when wiring image `sizes` (today: `min(45rem, 90%)` may become `45rem` + padding).
3. **Reverse-engineer** image windows (`sizes` + `haz_img__*` widths) as **fractions of measure** (`×1` / `×0.5` / `×0.25`). Change `--haz_measure` → those `sizes` lengths trickle down. Not Pico’s stepped `.container` viewport table.
4. **Reverse-engineer** variant pixel widths from the **same** `content_width` (× factors for 0.25 / 0.5 / 1 / 2× DPR, etc.). If measure is ~1000px, half is ~500 — a hard-coded `sm: 576` is already too big for that slot at 1×. Fixed Pico 576/768/1024/1280 is **not** the source of truth.

Do not invent `srcset` rungs first and then hope the layout matches. The measure boundary is the source of truth; image “stuff” follows.

**Must not:** serve a large-ish (1000px+) file to a phone when the slot is ~viewport or half-measure. Honest `sizes` + small rungs (`xs`/`sm`/…) on the menu are what prevent that; a menu that only has `lg`+ will always over-fetch on mobile.

**Product constraint:** do not recommend content `max-width` **> `45rem`**.

**Agent / human config story (later docs + AIX):**

1. Agent asks: content width? Recommended band **~36–40rem comfort, ≤ `45rem` ceiling** (tied to fluid type / line length).
2. That value becomes `content_width` (and should match CSS `--haz_measure` ceiling).
3. Agent then says: when you export images, use **this scale** (derived px per variant key from measure × factors).
4. Author does **not** need every variant on every asset. Full ladder exists in settings; **ship the subset that matches the window**:
   - `content` → often `sm`, `md`, `lg` (maybe `xl`/`xxl` if you care about fat DPR)
   - `content_half` → often `xs`/`sm`/`md` (through ~1× half / 2× quarter territory)
   - `content_quarter` → often `xs`, `sm`, `md`
5. Shortcode still only emits files that exist — sparse bundles are first-class.

## Settings (`settings.yaml`)

**Core ships a fixed obvious set.** Child may add more variants/windows (+ matching CSS for new window keys).

Leading `_` on keys stays the HAZ **parked** convention — do not use `_sm` as a live variant key.

```yaml
settings:
  images:
    config:
      variant_sep: "_"
      class_prefix: "haz_img__"
      # Aligned with CSS --haz_measure ceiling (Hugo cannot read the CSS var).
      content_width: "45rem"
      # srcset `w` descriptors are px. Assume 16px root unless overridden (45rem → 720).
      rem_px: 16
      measure_media: "(min-width: 45rem)"
    # Variant keys = suffixes; widths = round(content_width_px × factor).
    # Example at 45rem × 16 = 720px measure:
    #   xs 0.25 → 180   (quarter 1×)
    #   sm 0.5  → 360   (half 1× / quarter ~2×)
    #   md 0.75 → 540
    #   lg 1.0  → 720   (content 1× / half 2×)
    #   xl 1.5  → 1080
    #   xxl 2.0 → 1440  (content 2× retina) — keep a 2× rung; DPR is not a separate mode
    variants:
      xs: 0.25
      sm: 0.5
      md: 0.75
      lg: 1.0
      xl: 1.5
      xxl: 2.0
    windows:
      content: 1
      content_half: 0.5
      content_quarter: 0.25
```

- `content_width_px` = parse(`content_width`) × `rem_px` (for `rem`)
- File: `{stem}{variant_sep}{variant_key}{ext}` — `srcset` uses **derived px** as `Nw`
- Class: `{class_prefix}{window_key}`
- **One upstream measure** feeds both `sizes` and variant widths
- Only emit variants whose files exist
- Keep CSS `--haz_measure` ceiling equal to `content_width`
- No core viewport-bleed window

**Retina / DPR:** not a separate setting. Browser does `layout_width_from_sizes × devicePixelRatio` and picks from `srcset`. **`xxl: 2.0`** covers full-column @2×; optional file per asset. Sparse subsets per window are expected.

Optional later: `windows.*.suggest_variants: [sm, md, lg]` for agent copy — not required for v1 shortcode behavior.

## Shortcode behavior

**File:** core `layouts/shortcodes/haz_img.html` (sibling to [`haz.html`](layouts/shortcodes/haz.html) — not the graph `haz key=` path).

**Open-tag params (v1):**

- `window` (required) — key into `settings.images.windows`
- No need to pass every img attr

**Inner:** exactly one author `<img …>` (double-quoted attrs for v1 contract). Boilerplate + agent cover mum/edge cases.

**Pipeline:**

1. Read settings via existing sysManifest / settings access pattern.
2. Trim `.Inner`; validate it looks like a single `<img …>`.
3. Parse `src` from the inner tag (path basename) → stem + extension (`hero.jpg`).
4. For each variant (`key` → factor): width_px = round(content_width_px × factor); `GetMatch` `{stem}{variant_sep}{key}{ext}`; on hit add `url {width_px}w` to `srcset`.
5. Resolve `window` → factor; build `sizes` from `content_width` × factor + `measure_media`; derive layout class `{class_prefix}{window}`.
6. **Enrich tag:**
   - If `class="…"` present: splice derived class into the class list (split on `class="`, merge token, rejoin).
   - If no class: inject `class="{class_prefix}{window}"` together with `srcset` and `sizes`.
   - Inject/replace `srcset="…"` and `sizes="…"` (strip any pre-existing `srcset`/`sizes` on the inner tag so the shortcode wins).
   - Surgical append before final `>` / `/>`.
7. Emit enriched HTML (`safeHTML` as appropriate).
8. Fail closed with a clear development comment (or empty) if window missing / no inner img / no usable src — no silent wrong `100vw` default that ships a 1920 on mobile.

**Fallback `src`:** leave the author’s `src` as-is (usually the base / largest they chose). Do not invent a second source of truth.

**Rem math:** `content_width` `45rem` × factor `0.5` → `22.5rem` in `sizes`; same measure × `rem_px` × variant factor → `Nw` in `srcset`.

## CSS

Core ships rules for the default window keys so class layout matches `sizes`:

- `haz_img__content`
- `haz_img__content_half`
- `haz_img__content_quarter`

Child adding a new window key (e.g. viewport bleed) also adds `haz_img__{that_key}` CSS. Author decorative classes remain on the same element.

## Demo / proof

After merge: one content bundle with `hero.jpg` + `hero_sm.jpg` … and a paired `haz_img` call (thin slice on an existing demo post; full lorem refresh stays [#49](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/49)).

## Ship path

1. HQ [#13](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13) — branch `feat/13-haz-img`
2. Core PR: shortcode + default `settings.images` + CSS for default windows
3. Child may extend settings/CSS; optional demo markup/assets in content
4. Pages dispatch if live demo needs it
5. PRs `Refs hugo-agent-zero/hugo-agent-zero#13`

## Explicit non-goals (v1)

- Markdown image auto-`srcset` in the render hook
- Hugo `Resize` generating variants from one master (possible later with **extended** Hugo; not v1)
- Local “web app” / tool: drop in one image → spit HAZ-named ladder from settings factors (same vibe as other Mark tools); not v1
- `<picture>` / art direction
- Full HTML parser / single-quoted attr support
- Catalog of every `<img>` attribute on the shortcode open tag
