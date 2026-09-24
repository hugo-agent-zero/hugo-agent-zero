---
name: haz-img-exports
description: >-
  Compute haz_img export pixel widths (xs/sm/md/lg/xl/xxl) from kit
  settings.haz_img knobs. Use when exporting responsive image ladders for HAZ
  page bundles or when the user asks what widths to use for haz_img files.
---

# haz_img export widths

When exporting Affinity/Photoshop (or similar) sizes for `haz_img` page-bundle files (`stem.jpg`, `stem_xs.jpg`, … `stem_xxl.jpg`), derive widths from **child** `settings.haz_img.config`. Do not invent a parallel ladder.

**When** (viewport) is Pico `md` / `lg` = `min_tablet` / `min_desktop` (768 / 992). Not a fraction of measure.

**How-wide** is the column, capped by the desktop BP. `lg` = `min(content_width_px, min_desktop)`. DevTools on `--haz_measure_type` (65ch) → store as `content_width_px`. Do not subtract `content_inset`.

## Knobs

From `layouts/_partials/child/data/system_manifest/settings.yaml` → `settings.haz_img.config`:

| Knob | Meaning |
|------|---------|
| `content_width` | Measure (e.g. `55rem`) — desktop `sizes` length |
| `content_width_px` | Column px from DevTools (e.g. `990` = 55rem at 18px) — `lg` = min(this, min_desktop) |
| `breakpoints.min_tablet` | Viewport px where tablet starts (Pico md, 768) |
| `breakpoints.min_desktop` | Viewport px where desktop starts (Pico lg, 992) |

`content_inset` and `rem_px` are not part of this formula. Column vs viewport above 40rem uses 90% (child `--haz_measure`).

## Ladder

```
lg  = min(content_width_px, min_desktop)        # column, never the BP itself
sm  = min(lg, round(0.9 × (min_tablet − 1)))    # column just below tablet MQ
md  = min(lg, round(0.9 × (min_desktop − 1)))   # column just below desktop MQ
xs  = round(sm × 0.5)
xl  = round(lg × 1.5)
xxl = round(lg × 2)
```

Author keys `m{pct}_t{pct}_d{pct}` are **% of that tier’s hole** for `sizes` and CSS. They are not extra export rungs.

## Default kit (current dogfood)

`content_width: 55rem`, `content_width_px: 990`, `min_tablet: 768`, `min_desktop: 992`:

| File suffix | Role | Width (px) |
|-------------|------|------------|
| (base / master) | ≥ xxl, or lg — author choice | |
| `_xs` | half of mobile max | 345 |
| `_sm` | mobile max | 690 |
| `_md` | tablet max | 892 |
| `_lg` | min(column, 992) | 990 |
| `_xl` | 1.5× lg | 1485 |
| `_xxl` | 2× lg | 1980 |

Recompute if the knobs change.

## Output

Print a short markdown table of **suffix → role → px**, cite the knobs used, and remind: drop files next to the page as `stem.jpg` + `stem_{xs…xxl}.jpg` (or under `files/`), then `{{< haz_img key="m100_t100_d100" >}}`.
