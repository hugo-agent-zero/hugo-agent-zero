---
name: Shortcode name simmer
session: 2026-09-26
status: parked
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/86
related:
  - HQ #87 — today’s haz_tbd becomes haz_do
---

# Shortcode names (simmer)

No rename this sitting. Check the mouthfeel in ~24 hours, then implement under [#86](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/86) / [#87](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/87).

## Family (three stamps)

- **`haz_img`** — stays. Mom picks a preset key.
- **Layouts tap** (today `{{< haz key="…" >}}`) — **`haz_dc` or `haz_tbd`**. Tilt: **`haz_tbd`**. Declared spot; fill from the graph; keep filling it. We will explain it. Fontaines can sit down.
- **Stream toolbox** (today `haz_tbd`) — **`haz_do`**. First blade: `add="spacer"`. Attr name is the verb; value is which tool. One verb per call.

## Toolbox doctrine

- One shortcode, not 4–6 helpers (`haz_spacer`, …).
- Not WordPress. Sweet spot only. We say no.
- Extensible later via a **yaml registry** (verb/value → HTML partial). Child can add blades. Core ships the handful. Implementation TBD. Smart even if only we use it. Not a mall we merge from the internet.

## If we rename later (order)

1. Helper `haz_tbd` → `haz_do` first (free the name).
2. Then `haz` → `haz_tbd` (or `haz_dc` if the tilt flips).
3. FF `v1.x.x` before Pages.

`what=` / `haz_add` / `sak` / `util` are out of the lead. `add add=` is a stutter.
