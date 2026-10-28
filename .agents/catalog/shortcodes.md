# HAZ Shortcodes

**Layer 3 (deep).** Complete shortcode contract for agents and for humans who already care. Public How To posts on HAZ.com lead with **benefits** and a small recipe first — see **HAZ.com teach layers** in [AGENTS.md](../../AGENTS.md) and [plans/haz_teach_layers_8994454b.plan.md](../plans/haz_teach_layers_8994454b.plan.md). Do not paste this file into a blog post as the whole story.

Product surface for people who paste shortcodes. Designers curate. Mom types the names she was given.

## Images

### haz_img

Wrap an author `<img>` and add responsive `srcset` / `sizes` plus width and align classes from a named preset.

Do not invent HTML `srcset` by hand. Put the picture in the page bundle, point `src` at it, pick a preset.

#### Attributes

- `name` (required) — key under `settings.haz_img.presets` in the child. The preset owns width (`w`: 25|33|50|67|75|100), `align` (left|center|right|none), and `ratio` (for example `16/9`). Empty ratio means as-is (no frame).
- `lazy` (optional) — `false` skips `loading="lazy"` (heroes). Default comes from `settings.haz_img.config.default_lazy` (usually true).
- `process` (optional) — `true` fills missing `width_px` stubs via Hugo `Resize` (width-only; aspect unchanged). Page-bundle stubs still win. Default is `settings.haz_img.config.process` (false). Quality knobs later.

Inner content is the author’s HTML. The `src` stem must match page resources named with the `width_px` ladder (`_xs`, `_sm`, …). Sparse sets are fine. With `process=true`, a single master is enough — Hugo builds the missing rungs at build time.

#### Under the hood (`settings.yaml`)

The shortcode does not invent layout math. It reads the child sysMan settings.

1. **`settings.breakpoints`** — when the layout hops. `m` / `t` / `d` are mins (tablet / desktop / column). Those numbers land in the HTML `sizes` media queries.
2. **`settings.haz_img.config.width_px`** — the file menu for `srcset` (`xs` 240, `sm` 479, `md` 767, `lg` 1024, `xl` 1536, `xxl` 2048). Not the layout width. The shortcode looks for `photo_xs.jpg`, `photo_sm.jpg`, … next to the page.
3. **`settings.haz_img.config.default_lazy`** — default for `loading="lazy"` when the shortcode omits `lazy`.
4. **`settings.haz_img.presets.{name}`** — the named layout. `rwd.m` / `t` / `d` each may set `w`, `align`, and `ratio`. Omit a band or field and the band above is inherited (`t` from `m`, `d` from `t`).
5. **Build** — resolve the preset → CSS classes (`haz_img_m50`, `haz_img_m_left`, …) → `sizes` holes (file width × `w%` at each breakpoint) → `srcset` from page resources → optional frame (`haz_img_frame` + `--haz_img_ratio_*`) when any band has a ratio. Framed images prefix `sizes` with `auto`. As-is does not.

A designer changes behavior by editing presets (or `width_px` / breakpoints), not by hand-writing `srcset` in the Markdown.

Ultimately, what we want is to give the browser the largest image necessary without going over too much. That keeps the cumulative payload smaller, so the page loads faster.

#### What ships

The child ships a **bank** of presets: layout × crop, plus `as_is` and two alts.

Crops:

- `_sqr` → `1/1`
- `_portrait` → `3/4`
- `_landscape` → `4/3`
- `_widescreen` → `16/9`

Layouts (width stable across phone / tablet / desktop unless the key is an alt):

- `full_*` — 100% of the column
- `half_left_*` / `half_center_*` / `half_right_*` — 50%
- `third_left_*` / `third_center_*` / `third_right_*` — 33%
- `two_thirds_left_*` / `two_thirds_center_*` / `two_thirds_right_*` — 67%
- `quarter_left_*` / `quarter_center_*` / `quarter_right_*` — 25%
- `three_quarters_center_*` — 75%, centered

Also:

- `as_is` — 100%, no ratio, no frame
- `full_to_half_left` — full on phone, half left on desktop (alt)
- `three_quarters_from_half` — half centered on phone, three-quarters from tablet up (alt)

**Mom does not need this list.** The designer (or whoever set up the site) picks **3 to 5 keys** and says “use these.” You can add or change keys under `settings.haz_img.presets`.

#### Before / after

Markdown in. HTML out. Paths below match a page-bundle file `photo.jpg` with `_xs` … `_xxl` variants beside it. On a project Pages site the URLs include the site subdirectory.

**As-is** — natural file shape, no frame, no `auto` on `sizes`:

Before:

```
{{< haz_img name="as_is" >}}
<img src="photo.jpg" alt="As shot">
{{< /haz_img >}}
```

After (shape):

```
<img
  src="photo.jpg"
  alt="As shot"
  srcset="photo_xs.jpg 240w, photo_sm.jpg 479w, photo_md.jpg 767w, photo_lg.jpg 1024w, photo_xl.jpg 1536w, photo_xxl.jpg 2048w"
  sizes="(min-width: 768px) 1024px, (min-width: 480px) 767px, min(100vw, 479px)"
  loading="lazy"
  class="haz_img_m100 haz_img_t100 haz_img_d100">
```

**Half square left** — float, frame, cover crop, `auto` on `sizes`:

Before:

```
{{< haz_img name="half_left_sqr" >}}
<img src="photo.jpg" alt="Detail">
{{< /haz_img >}}
```

After (shape):

```
<img
  src="photo.jpg"
  alt="Detail"
  srcset="photo_xs.jpg 240w, photo_sm.jpg 479w, photo_md.jpg 767w, photo_lg.jpg 1024w, photo_xl.jpg 1536w, photo_xxl.jpg 2048w"
  sizes="auto, (min-width: 768px) 512px, (min-width: 480px) 384px, min(50vw, 240px)"
  loading="lazy"
  class="haz_img_m50 haz_img_t50 haz_img_d50 haz_img_m_left haz_img_t_left haz_img_d_left haz_img_frame haz_img_cover"
  style="--haz_img_ratio_m: 1/1; --haz_img_ratio_t: 1/1; --haz_img_ratio_d: 1/1">
```

**Alt hop** — full on phone, half left on desktop (`full_to_half_left`):

Before:

```
{{< haz_img name="full_to_half_left" >}}
<img src="photo.jpg" alt="Story">
{{< /haz_img >}}
```

After (shape): classes become `haz_img_m100 haz_img_t100 haz_img_d50 haz_img_d_left` plus frame/cover; desktop `sizes` hole is half of `lg` (512px). Ratio stays `16/9` on every band.

#### More examples

Hero, no lazy:

```
{{< haz_img name="full_widescreen" lazy=false >}}
<img src="hero.jpg" alt="Hallway">
{{< /haz_img >}}
```

Smaller than full, centered (not floated):

```
{{< haz_img name="half_center_landscape" >}}
<img src="photo.jpg" alt="Product">
{{< /haz_img >}}
```
