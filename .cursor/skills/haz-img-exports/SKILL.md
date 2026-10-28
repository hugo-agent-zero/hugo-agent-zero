---
name: haz-img-exports
description: >-
  Read haz_img export pixel widths (xs/sm/md/lg/xl/xxl) from kit
  settings.haz_img.config.rwd_widths.*.px. Use when exporting responsive image
  ladders for HAZ page bundles or when the user asks what widths to use.
---

# haz_img export widths

When exporting Affinity/Photoshop (or similar) sizes for `haz_img` page-bundle files (`stem.jpg`, `stem_xs.jpg`, … `stem_xxl.jpg`), use **child** `settings.haz_img.config.rwd_widths.*.px` as stamped whole px. Do not invent a parallel ladder or re-derive from gutters.

**When** (viewport) for `sizes=` / CSS comes from site `breakpoints` (and parked `_max_px` ceilings). HAZ dogfood tracks Open Props → 479 / 767 / 1024 (when = max + 1 → 480 / 768).

**How-wide** for files is `rwd_widths.*.px` (sm|md|lg match those ceilings). Do not subtract `content_inset`. Process quality (`q.jpeg`) is build-time only — exporters still stamp JPEG files; Mom stubs win as written.

## Knobs

From `layouts/_partials/child/data/system_manifest/settings.yaml` → `settings.haz_img.config`:

| Knob | Meaning |
|------|---------|
| `rwd_widths.*.px` | File menu key → width px. Stamp; do not derive at build |
| `rwd_widths.*.q.jpeg` | Process Resize quality (1–100); `-1` = Hugo default. Not an export size |

Preset `rwd.m|t|d.w` is **% of column** for `sizes=` holes and CSS classes — not extra export rungs.

## Default kit (OP dogfood)

| File suffix | Role | Width (px) |
|-------------|------|------------|
| (base / master) | ≥ xxl, or lg — author choice | |
| `_xs` | smaller / half rung | 240 |
| `_sm` | ≈ band ceiling m | 479 |
| `_md` | ≈ band ceiling t | 767 |
| `_lg` | column / measure | 1024 |
| `_xl` | density | 1536 |
| `_xxl` | density | 2048 |

Re-stamp `rwd_widths` if the theme library or measure changes.

## Output

Print a short markdown table of **suffix → role → px**, cite `rwd_widths` / breakpoints, and remind: drop files next to the page as `stem.jpg` + `stem_{xs…xxl}.jpg` (or under `files/`), then `{{< haz_img name="…" >}}`.
