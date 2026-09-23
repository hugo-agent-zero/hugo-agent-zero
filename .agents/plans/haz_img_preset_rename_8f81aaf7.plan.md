---
name: haz_img preset rename
overview: "Pre-PR rename: haz_img uses key=\"M_D\" (mobile_desktop % of measure) as a mnemonic settings-bundle id; each key maps to explicit sizes + class. Two tiers only — tablet optional as extra key segment."
session: "2026-09-18"
status: shipped
hq_issue: "https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13"
child_pr: "https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/64"
related:
  - "https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/65"
  - "https://github.com/hugo-agent-zero/hugoagentzero_com-content/pull/10"
  - "https://github.com/hugo-agent-zero/hugoagentzero_com-content/pull/11"
todos:
  - id: rename-settings-presets
    content: "Child settings: widths→presets keyed 100_100 / 50_50 / 25_25 with explicit sizes+class"
    status: completed
  - id: rename-shortcode-preset
    content: "Core haz_img: param key; lookup presets; drop factor→sizes math; CSS classes match keys"
    status: completed
  - id: rename-demo-preset
    content: "Content demo: width=content → key=100_100"
    status: completed
  - id: update-plan-wording
    content: Refresh haz_img v1 plan Author API to key=D_M model
    status: cancelled
isProject: false
---

# haz_img — `key="100_50"` model (pre-PR)

## Insight (locked)

- Param is a **settings-bundle id**, not “width.”
- Author-facing ids: **`desktop_mobile`** as **percent of measure** (two tiers only).
- Still only a **key** — honesty = settings row matches the mnemonic.
- **v1 convention:** two segments `desktop_mobile` (`100_100`, `50_50`, …). No tablet required.
- **Not enforced:** the shortcode does not parse the key. A child can add `"100_75_50"` (or any string) as a preset id + matching `sizes`/`class` if they want a tablet story — same mechanism, no code change.

## Author API

```md
{{< haz_img key="100_100" >}}
<img src="hero.jpg" alt="…" loading="lazy">
{{< /haz_img >}}

{{< haz_img key="50_50" >}}
<img src="side.jpg" alt="…" loading="lazy">
{{< /haz_img >}}

{{< haz_img key="50_100" >}}
<img src="stack.jpg" alt="…" loading="lazy">
{{< /haz_img >}}
```

- Param: **`key`** (on `haz_img` only — not graph `haz key=`).
- Shape: **`{desktop}_{mobile}`** — integers 0–100 = % of measure at that tier.
- v1 keys: `100_100`, `50_50`, `25_25`. Later e.g. `50_100` (half desk, full mobile).

## Settings shape

```yaml
images:
  config:
    variant_sep: "_"
    class_prefix: "haz_img__"
    content_width: "45rem"
    rem_px: 16
    # Desktop floor for sizes strings (mobile = default in the sizes list).
    breakpoints:
      desktop: "(min-width: 45rem)"
  variants:
    xs: 0.25
    sm: 0.5
    md: 0.75
    lg: 1.0
    xl: 1.5
    xxl: 2.0
  presets:
    "100_100":
      sizes: "(min-width: 45rem) 45rem, 95vw"
      class: haz_img__100_100
    "50_50":
      sizes: "(min-width: 45rem) 22.5rem, 47.5vw"
      class: haz_img__50_50
    "25_25":
      sizes: "(min-width: 45rem) 11.25rem, 23.75vw"
      class: haz_img__25_25
```

Runtime v1: look up `presets[key]` → inject `sizes` + `class`. **Does not parse** key digits. `srcset` unchanged (stem → Resources → variants).

## CSS (pico-x) — deferred

Kit CSS defaults for `haz_img__100_100` / `50_50` / `25_25` come **after** settings + shortcode + demo are green. This pass may leave temporary class names from the prior `haz_img__content*` rules or inject the new class strings with layout TBD — do not block on pico-x polish.

- **`sizes`** (in settings) = what the browser downloads.
- **CSS class** = how wide it lays out (later).
- Custom keys still need both a preset row and CSS when we add them.

## Rename pass (local `feat/13-haz-img`, no PRs yet)

**This sitting:** settings + shortcode + demo only. **CSS later.**

1. Child `settings.yaml`: drop `widths`; add `presets` + `breakpoints.desktop`.
2. Core `haz_img.html`: `.Get "key"`; preset lookup; no factor→sizes.
3. Content demo: `key="100_100"`.
4. ~~Core pico-x class rename~~ — parked until after the above is verified.

## Out of scope

- Parsing or validating key digit patterns (any preset map key is legal)
- Shipping `50_100` or three-segment keys in v1 kit defaults (structure ready; child can add anytime)
- PRs / FF / real JPG ladder
