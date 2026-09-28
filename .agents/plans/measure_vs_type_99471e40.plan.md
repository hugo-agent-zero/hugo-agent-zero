---
name: Measure vs type
session: 2026-09-28
status: in_progress
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/87
related:
  - HQ #51 — original measure-as-constant (closed)
  - HQ #54 — How To after this is explainable
  - HQ #72 — width map / content_width_px after A is trusted
  - HQ #90 — headline alt-font (not this ticket)
  - HQ #30 — heading scale = rem of root (same curve as body)
  - haz-com-child #4 — drop sweet/type debt
---

# Measure vs type — A/B/C (locked 2026-09-25 afternoon)

Implement under [#70](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70). No more coupled `type` / `sweet` / `delta` knobs.

## Progress (2026-09-28)

- Dropped `sweet` / `type` / `delta` ch debt (kit + haz-com-child #4).
- One-slope + hot `vw` cliffed at the BP. Now **two fluid-type calculator clamps**, seam at desktop (Pico **lg = 1024**, not Bootstrap 992). Band 1 `1rem→1.125rem`; band 2 `1.125rem→1.3rem`. Headings = rem of root (#30 = same curve; #90 = alt face).
- Open: [child #87](https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/87). Pico commitment in doubt — color skins win; tomorrow rethink base (hybrid / new.css / Water / Open Props). Fluid stays HAZ.

## Locked model

Column is the input. Font is the output of a ~65-character fit in **our** face.

- **A** — column max, **px**. Ultrawide must stop. `min(A, 90%)` on small screens.
- **B** — font max. The size that puts ~65 of a letter/digit sample (`abcdefgh10 ijklmnop20…`) in A. Not `ch` / zeros.
- **C** — font min (`100%`). Reader default wins.

Clamp is only C→B. Slope between them. At A, stop (or a tiny second slope later if we want it). Guess B, look at the page, nudge. Child changes the variables; swap the face → retune A/B (C almost always stays).

`ch` on `font-size` is just another length. Honest `max-width: 65ch` is column-follows-font — the other job. We are not doing that.

65 is a **desktop** target. On a phone, let the line go short; do not shrink type to keep 65 chars.

## Out of scope

- Headlines / brand face: [#90](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/90)
- Heading-size utilities: [#30](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/30)
- Do **not** merge [core #51](https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/51) (that is `haz_img` drop-`auto`, a different ticket)
