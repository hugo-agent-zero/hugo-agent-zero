---
name: haz-img-exports
description: >-
  Compute haz_img export pixel widths (xs/sm/md/lg/xl/xxl) from kit image
  settings knobs. Use when exporting responsive image ladders for HAZ page
  bundles or when the user asks what widths to use for haz_img files.
---

# haz_img export widths

When exporting Affinity/Photoshop (or similar) sizes for `haz_img` page-bundle files (`stem.jpg`, `stem_xs.jpg`, … `stem_xxl.jpg`), derive widths from **child** `settings.images.config`. Do not invent a parallel ladder.

Size to the **band**. Do not subtract `content_inset`. Files run about 1rem larger than the padded hole; that overshoot is accepted.

Full-width px is `--haz_measure_type` (`65ch` in the child override) converted to px for image files. `content_width_px: 775` is that DevTools reading. Morning pass reconciles it with `--haz_measure` (`45rem`). Do not treat the `ch` spine and the image widths as unrelated.

## Knobs

From `layouts/_partials/child/data/system_manifest/settings.yaml` → `settings.images.config`:

| Knob | Meaning |
|------|---------|
| `content_width` | Measure (e.g. `45rem`) = full width |
| `content_width_px` | Full width in px (e.g. `775`) — use this for export px |
| `breakpoints.min_tablet` | Fraction of full width where the tablet band begins |
| `breakpoints.min_desktop` | Fraction of full width where the desktop band begins |

`content_inset` and `rem_px` are not part of this formula.

## Ladder

```
mobile_max = content_width_px × min_tablet
tablet_max = content_width_px × min_desktop
full_width = content_width_px

xs  = round(mobile_max × 0.5)   # half of mobile max
sm  = round(mobile_max)         # mobile max
md  = round(tablet_max)         # tablet max
lg  = round(full_width)         # full width
xl  = round(full_width × 1.5)
xxl = round(full_width × 2)
```

Author keys `m{pct}_t{pct}_d{pct}` are **% of that tier’s band** for `sizes` and CSS. They are not extra export rungs.

## Default kit (current dogfood)

`content_width_px: 775`, `min_tablet: 0.5`, `min_desktop: 0.8`:

| File suffix | Role | Width (px) |
|-------------|------|------------|
| (base / master) | ≥ xxl, or lg — author choice | |
| `_xs` | half of mobile max | 194 |
| `_sm` | mobile max | 388 |
| `_md` | tablet max | 620 |
| `_lg` | full width | 775 |
| `_xl` | 1.5× full width | 1163 |
| `_xxl` | 2× full width | 1550 |

Recompute if the knobs change.

## Output

Print a short markdown table of **suffix → role → px**, cite the knobs used, and remind: drop files next to the page as `stem.jpg` + `stem_{xs…xxl}.jpg` (or under `files/`), then `{{< haz_img key="m100_t100_d100" >}}`.
