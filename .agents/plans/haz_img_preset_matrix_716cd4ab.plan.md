---
name: haz_img preset matrix
session: 2026-10-27
status: in_progress
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/133
core_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/125
related:
  - HQ #153 — Catalog: shortcodes.md (haz_img first)
  - HQ #142 — haz_img beta-ready; presets still dogfood-shaped
  - HQ #89 — preset key naming (historical)
  - staging content #52 — demo-post-1 names
todos:
  - id: rewrite-presets
    content: Replace child settings.haz_img.presets with the 56+as_is+2-alt matrix (includes *_center_*)
    status: completed
  - id: dogfood-names
    content: Update demo-post-1 (and haz_img.html usage comment) to the new keys
    status: completed
  - id: shortcode-doc
    content: Draft shortcodes.md haz_img section against the ship set for Mark review
    status: completed
isProject: false
---

# haz_img starter preset matrix

## Issue

The child ships `settings.haz_img.presets`, but the current keys are a dogfood mix. Some names are hard to remember (`half_sqr_left`, `desk_half_left`). Some widths hop across `m` / `t` / `d` without the name saying so (old `mid_center` 75→50→75). Two keys (`ratio_shift`, `two_thirds_ratio`) exist only to prove the engine.

Mom types `name="…"`. The starter child should ship a solid **bank** of expected defaults, not a POC. CSS already allows `w` of 25|33|50|67|75|100. What changes per site is mostly **aspect ratio**. Docs should say: start here; change `ratio` or add a key when you need something else.

Mom may never see the whole bank. The designer (or the person who set up the site) picks **3 to 5 keys** and tells her “use these.” The matrix is for that person and for HAZ.com / the catalog — not for Mom to memorize.

Product docs ([#153](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/153) / HAZ.com later) cannot list “ships with…” until this menu is clean.

## Plan

### Crop suffixes (width / height)

| Suffix | `ratio` | Job |
|--------|---------|-----|
| `_sqr` | `1/1` | Square |
| `_portrait` | `3/4` | Tall |
| `_landscape` | `4/3` | Classic photo |
| `_widescreen` | `16/9` | Wide / video-like |

### Layout prefixes (width stable across bands unless alt)

| Prefix | w | align |
|--------|---|-------|
| `full_*` | 100 | (none) |
| `half_left_*` / `half_center_*` / `half_right_*` | 50 | left / center / right |
| `third_left_*` / `third_center_*` / `third_right_*` | 33 | left / center / right |
| `two_thirds_left_*` / `two_thirds_center_*` / `two_thirds_right_*` | 67 | left / center / right |
| `quarter_left_*` / `quarter_center_*` / `quarter_right_*` | 25 | left / center / right |
| `three_quarters_center_*` | 75 | center |

`full_*` stays full-bleed in the column — no `_center_` (100% already fills). For a smaller image that sits centered, use `half_center_*`, `third_center_*`, `two_thirds_center_*`, `quarter_center_*`, or `three_quarters_center_*`.

Each layout × four crops = **56** framed presets (14 layouts × 4).

Also ship:

- `as_is` — w 100, no ratio, no frame
- `full_to_half_left` — alt: m 100 → d 50 left, one crop (`_widescreen`) — “you can also…”
- `three_quarters_from_half` — alt: m 50 center → t/d 75 center, one crop (`_landscape`) — “you can also…”

Total ≈ **59** keys. Drop the old dogfood set.

Example framed key:

```yaml
half_left_portrait:
  _term: Half left portrait
  fit: cover
  rwd:
    m:
      w: 50
      align: left
      ratio: "3/4"
```

Put width/align/ratio on `m` only unless the key is an alt hop. `_term` stays parked.

### Steps

1. Rewrite `settings.haz_img.presets` in the child sysMan settings file. Leave `config` and `breakpoints` alone.
2. Retarget staging `demo-post-1` to the new `name=` keys. Replace circus samples with one alt example each. Keep test copy plain.
3. Update the usage comment in core `haz_img.html` (`story_wide` → e.g. `full_widescreen`).
4. After the menu is live: draft `.agents/catalog/shortcodes.md` with `# HAZ Shortcodes` / `### haz_img` — attrs, ship bank, roll-your-own, show-and-tell. Say clearly: designers curate 3–5 keys for Mom; she does not need the full list. Mark reviews that before other shortcodes.

No CSS changes. Classes already match the `w` allowlist.

### PR order

1. Child — preset matrix → `main`
2. Staging content — demo names (after child is on Pages)
3. Core — usage comment only → `v1.x.x`
4. HQ — catalog `haz_img` section after eyes-on / draft approval

### Out of scope

- Copying presets into `hugo-agent-zero-child-content` if still missing (follow-up)
- Re-export demo JPEGs at `width_px` ([#159](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/159))
- reseter under Simple ([#161](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/161))
- `haz_do` / `haz_tbd` catalog pages until `haz_img` docs are approved

## Files

- [`project-modules/hugo-agent-zero-child/layouts/_partials/child/data/system_manifest/settings.yaml`](../../../project-modules/hugo-agent-zero-child/layouts/_partials/child/data/system_manifest/settings.yaml) — presets
- [`project-modules/hugo-agent-zero-env-staging-content/content/blog/demo-post-1/index.md`](../../../project-modules/hugo-agent-zero-env-staging-content/content/blog/demo-post-1/index.md) — dogfood
- [`project-modules/hugo-agent-zero-core/layouts/shortcodes/haz_img.html`](../../../project-modules/hugo-agent-zero-core/layouts/shortcodes/haz_img.html) — comment examples
- [`hugo-agent-zero/.agents/catalog/shortcodes.md`](../catalog/shortcodes.md) — product doc (after presets)
