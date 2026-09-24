---
name: "#13 haz_img review"
overview: Do kit refactors first (settings.haz_img, Pico 768/992, drop 0.5/0.8 and inset subtract). How To outline stays in this plan. .com later. hugo.yaml-as-module is a parked spitball.
session: "2026-09-24"
status: in_progress
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13
core_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/46
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/74
related:
  - https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/45
  - https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/75
  - https://github.com/hugo-agent-zero/hugo-agent-zero-env-staging-content/pull/22
  - https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70
  - https://github.com/hugo-agent-zero/hugo-agent-zero/issues/72
todos:
  - id: refactor-settings
    content: Child settings.images → settings.haz_img; min_tablet/min_desktop = 768/992.
    status: completed
  - id: refactor-shortcode
    content: Core haz_img reads haz_img; Pico BPs for sizes; drop 0.5/0.8 and inset subtract.
    status: completed
  - id: refactor-css
    content: pico-x MQs 768px / 992px (stamp; no var() in @media).
    status: completed
  - id: refactor-skill
    content: Update haz-img-exports skill; drop fraction ladder.
    status: completed
  - id: outline-park
    content: How To outline stays in this plan. No .com this slice.
    status: pending
isProject: false
---

# #13 haz_img — review + How To outline

[#13](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13) **is** `haz_img`. We already shipped it.

**EOD 2026-09-24:** Kit refactors + `sizes` snap shipped. Staging dogfood OK (1× xs/sm/md/lg at the BPs). Next = flesh this How To. `sizes` is **px** (BPs × key), not ch/rem. Inset subtract is gone. Ladder `lg` = 1065. Type [#70](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70); width map [#72](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/72). After core → `main`, FF `v1.x.x` same sitting.

**A.** Trace the live kit. Kit PRs for the Pico pass have merged; `sizes` px is core #46.

**B.** The outline **lives in this plan** — the numbered steps below *are* the How To. Bullets stay thin (what / why / where). Real prose waits. `.com` stays closed; publishing needs a `haz-com-content` issue + both agree.

Working title: **Shortcode: haz_img Explained**

---

## 1. Set the measure

a. **Column:** `--haz_measure` = `min(var(--haz_measure_sweet), 95%)`; at `min-width: 768px` (`min_tablet`) → `min(sweet, 90%)`. Wider gutters once we leave mobile. Stamp px — rem MQs drift with type.
b. **Type:** parked on [HQ #70](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70). Last knobs: sweet **68ch**, type **100ch**, `font_vw` **0.75vw**, max **102.5% × delta**.
c. **Sweet:** `--haz_measure_sweet` = **68ch** — this typeface’s line. New face → maybe a new sweet.
d. **Settings echo:** `settings.haz_img.config.content_width: "68ch"` (column CSS). `sizes` is **px** from `content_width_px` / band × key — not ch/rem.
e. Column is how-wide for the box. It does **not** set the BPs (see **3**).

## 2. Read that width in px (how-wide only)

a. **BPs do not need this.** When = Pico **768 / 992**, stored on `settings.haz_img.config.breakpoints`.
b. **Inspect the column** (wide viewport): store as `content_width_px`. Live read: **1065**.
c. **`lg` = content_width_px** = **1065**. Do not cap at `min_desktop` (992). The box is north of the desktop BP.
d. `rem_px` / a second rem story are leftovers. One stored px is enough for srcset `w`. Re-read after any type or rem change.

## 3. Set the bands (when vs how wide)

a. **Abandon 0.5 / 0.8.** That was a dev scaffold. Measure does not define when tablet/desktop starts. Delete those fractions from settings, shortcode math, skill, and CSS (`22.5rem` / `36rem` go).
b. **When (locked):** Pico `md` / `lg` = **768px / 992px**. Put those in `settings.haz_img` (not 0.5 / 0.8). Pico-x / override uses the same pair for `haz_img_w_*` MQs.
c. **How wide** (export / `sizes`): hole ≈ column at that viewport (`min(measure, 95%/90% of vw)`). Mobile max ≈ column just below 768; tablet max ≈ column just below 992; desktop = measure.
d. **Rename:** settings key should be `haz_img`, not `images`.
e. **Two consumers, one YAML pair:** CSS MQs for `haz_img_w_*` live in pico-x / pico-override (if they swap Pico, that file gets a new stamp). The shortcode still needs the same numbers for `sizes` — that is not in the CSS library. `settings.haz_img` is what `haz_img.html` reads; Hugo can print the CSS stamp from it so we don’t hand-sync.
f. **Catch:** `@media (min-width: var(--x))` is invalid. Hugo prints the rem/px into `:root` *and* the `@media` literals.
g. **Gutter MQ:** 95%→90% joins `min_tablet` (768px). Not `min_desktop`. Stamp px — rem drifted with type.

## 4. Translate bands into image widths

a. Size to the **band**. Do not subtract `content_inset` (~1rem overshoot is OK)
b. Ladder ([`haz-img-exports`](../../.cursor/skills/haz-img-exports/SKILL.md)): `xs` = ½ mobile; `sm` = mobile; `md` = tablet; `lg` = full; `xl` = 1.5×; `xxl` = 2×
c. Dogfood table: xs 345 / sm 690 / md 892 / lg **1065** / xl 1598 / xxl 2130.
d. Inset subtract is gone. `sizes` = `(min-width: 992px) {lg×d%}px, (min-width: 768px) {md×t%}px, min({m%}vw, {sm×m%}px)`.

## 5. Author key (percent of the band)

a. `key="m{pct}_t{pct}_d{pct}"` (or `m*_d*`, tablet inherits mobile)
b. pct ∈ 25 | 50 | 75 | 100 — **not** extra export files
c. Shortcode writes `sizes` + `haz_img_w_m__*` / `_t__*` / `_d__*`
d. `srcset` = files that exist next to the page (`stem_xs.jpg` …). Sparse is OK
e. Author keeps the `<img>` (alt, class, loading). HAZ only enriches

## 6. See it on the page

a. Staging [`demo-post-1`](../../../project-modules/hugo-agent-zero-env-staging-content/content/blog/demo-post-1/index.md): `m100_t100_d100` (one `<img>`)
b. DevTools: `sizes`, `srcset`, which file the browser picks at mobile / tablet / desktop. 1× panel resize, not mobile sim, for the BP story. Sim = DPR / fatter files.
c. Markdown `![]()` stays dumb — opt in to `haz_img` when you care
d. Not this post: `<picture>` / art direction ([#6](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/6)); fluid type ([#54](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/54), [#70](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/70))

---

## Execute first (kit only — switch to Agent)

`.com` later. Staging dogfood is enough.

**Done 2026-09-24.** Next sitting = How To prose from steps 1–6. Still no `.com` PR until a content issue + both agree. FF `v1.x.x` after every core → `main`.

## Parked spitball — `hugo.yaml` as a module

Pain is real: child is the build root, so a kit child update can wipe site menus / `baseURL`. A config-only module would isolate that.

Simpler first try: a **site overlay** Hugo already merges (`config/_default/menus.yaml` or a tiny imported config module) owned by the site, not by child layouts. Full “hugo.yaml repo” is three modules per site — maybe later, not this slice.
