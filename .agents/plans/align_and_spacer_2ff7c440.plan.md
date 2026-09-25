---
name: Align and spacer
session: 2026-09-25
status: shipped
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/85
related:
  - HQ #84 — dogfood floats
  - HQ #87 — rename haz_tbd later
  - HQ #88 — nest w + align (followed same sitting)
---

# Per-band align + spacer

Shipped 2026-09-25. Presets get per-band align (`left` | `right` | `center` | `none`). Blank inherits the previous band. Mom does not type float classes.

`haz_clear` dropped. Catch-all `haz_tbd type="spacer"` (`size` rem default 1, `clear` default true). Air is inline `height`, not a `--var` hop. `---` stays a real line.

Do **not** merge [core #51](https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/51).
