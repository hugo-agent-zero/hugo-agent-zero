---
name: Nested m t d bands
session: 2026-09-25
status: shipped
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/88
related:
  - HQ #85 — align + spacer first
  - HQ #89 — revisit ship keys later
---

# Nest `w` + `align` under `m` / `t` / `d`

Shipped 2026-09-25. Hard cut scalars. Each band is a map: `w` (25|50|75|100), optional `align`. Omit a band or field → inherit the one above (`t` from `m`, `d` from `t`). `class` stays preset-level leftovers.

`story_wide` is 100/100/100. `desk_half_left` is 100/100/50 with `d.align: left` only.

Pages failed until `v1.x.x` fast-forwarded to the map-reading shortcode. FF before Pages.

Do **not** merge [core #51](https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/51).
