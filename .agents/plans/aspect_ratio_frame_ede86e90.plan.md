---
name: aspect ratio frame
overview: "Mom picks a named preset. Settings own width, frame, fit, and an open class string (home for float_left). The m/t/d engine stays behind the YAML. Merge #51 first. No SC overrides in v1."
todos:
  - id: merge-51
    content: "Mark merges core #51 (drop auto); FF v1.x.x"
    status: cancelled
  - id: presets
    content: "Named presets in settings.haz_img; SC key is a preset id; CSS for ratio + cover; preset class merged onto the img"
    status: completed
isProject: false
---

# Named haz_img presets (mom keys)

**Status 2026-09-25:** shipped (core #52, child #78, staging #24). Do **not** merge #51 — `auto` stays; the frame is the height fix.

The paste proved the frame: `aspect-ratio` + `object-fit: cover` + `height: auto` on the `<img>`. No wrapper. No file `width`/`height`.

Spitball is the right API: **mom types a name**. She does not type `m100` or `16/9` or `cover`.

## Push back (keep this)

- **Do not kill the engine.** `m` / `t` / `d` percents, `sizes`, and the width classes stay. They become fields *inside* a preset. The shortcode `key` is no longer `m100_t100_d100`. It is a string that looks up settings.
- **Key names are the site’s.** `full_a` was only an example. Real ids should be helpful (`hero`, `story_wide`, `half_sqr_left`). Kit ships a small starter list; they rename.
- **`left` is mom’s word in the key.** In YAML, extra look lives on an open `class` string (`float_left`), not a `place:` field. We do not invent those class names; whoever writes the CSS owns them (child override is the usual home).
- **No SC overrides in v1** (agreed). No `ratio=` on the shortcode. Change the look in settings.

## What mom types

```
{{< haz_img key="story_wide" >}}
<img src="photo.jpg" alt="…">
{{< /haz_img >}}
```

Whatever string they put in settings. Not a packed `m100_t100_d100`.

Unknown key = today’s bad-key comment (do not guess).

## Settings shape

In [settings.yaml](project-modules/hugo-agent-zero-child/layouts/_partials/child/data/system_manifest/settings.yaml) under `settings.haz_img`:

```yaml
presets:
  story_wide:
    term: Wide
    m: 100
    t: 100
    d: 100
    ratio: 16/9
    fit: cover
  half_sqr_left:
    term: Half square left
    m: 50
    t: 50
    d: 50
    ratio: 1/1
    fit: cover
    class: float_left
```

`class` is an open extra-class string (space-separated if more than one). Merged onto the `<img>` with the width/frame classes. Typo is silent — that is the trade for “put anything.”

`m`/`t`/`d` ∈ 25|50|75|100. **`ratio` is used as-is** (no kit allowlist). YAML `16/9` becomes `aspect-ratio: 16/9`. Typo is bad CSS, same trade as open `class`. `fit` is `cover` for v1.

Because the value is open, do not ship one class per ratio. One frame class plus a custom property, e.g. `haz_img_frame` with `aspect-ratio: var(--haz_img_ratio)` and the shortcode sets `--haz_img_ratio: <yaml as-is>`.

`config` (column, BPs, `default_lazy`) stays as it is.

## What the shortcode does

Look up `settings.haz_img.presets[key]`. Build the same classes as today from `m`/`t`/`d` (`haz_img_m100` …). Add `haz_img_frame` + `haz_img_cover`. Set `--haz_img_ratio` from the preset `ratio` string as-is. Append `class` from the preset as-is.

`sizes` still from m/t/d × column / BPs. `auto` stays (do not merge #51).

## CSS

Same file: [pico-x-agent-zero.css](project-modules/hugo-agent-zero-core/assets/css/pico/pico-x-agent-zero.css)

- Keep width utilities.
- `.haz_img_frame { aspect-ratio: var(--haz_img_ratio); height: auto; }`
- `.haz_img_cover { object-fit: cover; }`
- Pico is classless — no float helpers. Ship a **handful** of kit helpers in the same file (or `haz.css`), `haz_` names: e.g. `haz_float_left`, `haz_float_right` (and maybe a clear). Starter presets put those strings in `class`. Extra/odd classes still go in the open `class` prop; child CSS owns anything we do not ship.

## PRs

- Do **not** merge [core #51](https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/51). Frame keeps `auto`.
- HQ work on [#81](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/81): core shortcode + CSS, child starter presets. New branches off `main`.
- Dogfood: one demo img on a starter preset name when you want eyes-on.
- After core merge: FF `v1.x.x` + new Pages dispatch; hard-refresh executed CSS.

## Gaps (not new product)

- **Old keys die.** Staging is one `m100_t100_d100`. Hard cut: unknown key fails; update that demo to a starter name. No dual-read unless you want a sitting of both.
- **`lazy=false` stays a shortcode attr** for now (heroes). A `lazy` field on the preset can wait.
- **Float + following text:** ship `haz_clear` in the handful so a later block can clear. Not magic.
- **[#81](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/81)** title is still “frame + object-fit”. Comment that it is named presets now, or open a follow-on. Same work.
- How To [#13](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13) becomes “pick a name from the site list.” Not this PR.

## Not in v1

- SC `ratio` / `fit` / author-typed `m100_t100_d100`.
- Wrapper `div`.
- File `width`/`height` attrs.
- Dropping `auto` (#51).
