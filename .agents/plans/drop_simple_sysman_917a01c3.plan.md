---
name: Drop Simple sysMan
session: 2026-09-01
status: shipped
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/40
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/24
overview: Remove parked `_framework_css_simple_css` from child sysMan. Core Simple assets and `framework_css.html` remain for other children.
todos:
  - id: hq-issue
    content: "HQ issue #40 opened 2026-09-01"
    status: completed
  - id: delete-node
    content: Delete _framework_css_simple_css from child atoms.yaml
    status: completed
  - id: pr
    content: PR Refs HQ#40; do not merge main
    status: completed
isProject: false
---

# Drop Simple.CSS from child sysMan

**Status:** Shipped 2026-09-01. HQ [#40](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/40) closed. Child [PR #24](https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/24).

## Intent

This child is Pico-only in the graph (`multipliers.yaml` already `inst: framework_css_pico_css`). The parked `_framework_css_simple_css` node was leftover swap-demo, not a live stack. Removed from child sysMan so manifests stay Pico-clean.

**Keep:** `cta_simple_000` (CTA molecule). Core Simple CSS files. `framework_css.html` Atomic. `assets/child/css/simple/simple-override.css` on disk (optional reference for a future Simple child).

## Scope (child PR only)

Delete `_framework_css_simple_css` from child `layouts/_partials/child/data/system_manifest/layouts/atoms.yaml`. No core PR. No graph rewires.

## Verify

`hugo` still emits Pico + `haz.css` + pico-x + child override. No Simple `<link>` in `<head>`.
