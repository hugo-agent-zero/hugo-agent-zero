---
name: haz-img-exports
description: >-
  Read haz_img export pixel widths (xs/sm/md/lg/xl/xxl) from kit
  settings.haz_img.config.width_px. Use when exporting responsive image
  ladders for HAZ page bundles or when the user asks what widths to use.
---

# haz_img export widths

When exporting Affinity/Photoshop (or similar) sizes for `haz_img` page-bundle files (`stem.jpg`, `stem_xs.jpg`, … `stem_xxl.jpg`), use **child** `settings.haz_img.config.width_px` as stamped whole px. Do not invent a parallel ladder or re-derive from gutters.

**When** (viewport) for `sizes=` / CSS comes from `config.max_px` (m/t ceilings; d = measure max). HAZ dogfood tracks Open Props `--sm` / `--md` / `--size-lg` → max_px 479 / 767 / 1024 (when = max + 1 → 480 / 768).

**How-wide** for files is `width_px` (sm|md|lg match max_px.m|t|d). Do not subtract `content_inset`.

## Knobs

From `layouts/_partials/child/data/system_manifest/settings.yaml` → `settings.haz_img.config`:

| Knob | Meaning |
|------|---------|
| `max_px.m` / `.t` / `.d` | Viewport max for m/t bands; d = column ceiling (whole px) |
| `width_px.*` | File menu key → width px. Stamp; do not derive at build |

Preset `rwd.m|t|d.w` is **% of column** for `sizes=` holes and CSS classes — not extra export rungs.

## Default kit (OP dogfood)

| File suffix | Role | Width (px) |
|-------------|------|------------|
| (base / master) | ≥ xxl, or lg — author choice | |
| `_xs` | smaller / half rung | 240 |
| `_sm` | = max_px.m | 479 |
| `_md` | = max_px.t | 767 |
| `_lg` | = max_px.d (measure) | 1024 |
| `_xl` | density | 1536 |
| `_xxl` | density | 2048 |

Re-stamp `width_px` (and matching `max_px`) if the theme library or measure changes.

## Output

Print a short markdown table of **suffix → role → px**, cite `width_px` / `max_px`, and remind: drop files next to the page as `stem.jpg` + `stem_{xs…xxl}.jpg` (or under `files/`), then `{{< haz_img name="…" >}}`.
