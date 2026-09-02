---
name: "#41 dialog + enqueue note"
session: 2026-09-01
status: shipped
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/41
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/25
related:
  - HQ #34 — composition vs enqueue lanes (comment only)
overview: Ship #41 as a one-slot sysMan move (search dialog lower in DOM). Add a design comment on parked enqueue issue #34 — no enqueue revival now.
todos:
  - id: 41-move-slot
    content: "Child PR: move search from block_main_pre to block_main_post (before body_end)"
    status: completed
  - id: 34-comment
    content: "Comment on HQ #34 with composition vs enqueue lanes + #41 pointer"
    status: completed
  - id: 41-verify
    content: "Smoke: dialog low in DOM, search still works from header"
    status: completed
isProject: false
---

# #41 dialog move + enqueue issue note

## Short answer to your question

You are **not** overthinking the *idea* of head vs foot zones — HAZ already has them, just under different names:

| Intent | Already exists | Parked |
|--------|----------------|--------|
| Up / head | `head_main` — meta, `framework_css` | `_enqueue_head` atom + `_enqueue.yaml` (asset registry) |
| Body early | `block_main_pre` — skip, header, **search (today)** | — |
| Body late | `block_main_post` → `body_end` → `body_end_scripts` (toggler, modal JS) | `_enqueue_footer` atom |
| Hugo content | `{{ block "main" }}` in `baseof.html` | — |

**Two lanes — keep them separate:**

- **Composition slots** = markup landmarks (header, footer, `<dialog>`, skip). Order in multipliers.
- **Enqueue** ([#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34)) = declarative **asset** lists (CSS/JS paths by `location: head|footer`). Not loaded today; `_enqueue_000.html` is parked MVP.

The Pagefind dialog is **markup**, not enqueue. Moving it does not need `block_main_post_enqueue` or a new multiplier — that would duplicate `body_end` and blur the lanes.

## #41 — KISS implementation (child only)

In child `multipliers.yaml`:

1. Remove `search` from `block_main_pre.props.order`.
2. Add `search` to `block_main_post.props.order` **before** `body_end` (after `post_footer`).
3. Move the `search` child block from `block_main_pre.children` to `block_main_post.children` (same `inst: search_pagefind_modal_000`).

Header trigger unchanged. `script_modal` still finds dialog by id.

**Verify:** build; search opens from header; view source shows `<dialog>` after footer, before `body_end_scripts`; skip → header → `<main>` unchanged.

Branch `feat/41-search-dialog-dom`. PR refs [#41](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/41). Mark merges; do not merge `main`.

## Enqueue issue #34 — comment only (no code)

Post a comment on [#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34) capturing today's decision:

- Head/foot **zones already exist** (`head_main`, `body_end_scripts`); parked `_enqueue_*` is for **assets**, not composition.
- Overlays/modals belong in **composition** slots (`block_main_post`, low) — see #41.
- Do **not** add `block_main_post_enqueue`; avoid parallel systems.
- Revisit #34 when we need ad-hoc asset lists (FA, third-party) without new Atomics — not for dialog DOM position.

No changes to `_enqueue.yaml` or `_enqueue_000.html` in this sitting.
