# HAZ Shortcodes

Product surface for people who paste shortcodes. Designers curate. Mom types the names she was given.

## Images

### haz_img

Wrap an author `<img>` and add responsive `srcset` / `sizes` plus width and align classes from a named preset.

Do not invent HTML `srcset` by hand. Put the picture in the page bundle, point `src` at it, pick a preset.

#### Attributes

- `name` (required) — key under `settings.haz_img.presets` in the child. The preset owns width (`w`: 25|33|50|67|75|100), `align` (left|center|right|none), and `ratio` (for example `16/9`). Empty ratio means as-is (no frame).
- `lazy` (optional) — `false` skips `loading="lazy"` (heroes). Default comes from `settings.haz_img.config.default_lazy` (usually true).

Inner content is the author’s HTML. The `src` stem must match page resources named with the `width_px` ladder (`_xs`, `_sm`, …). Sparse sets are fine.

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

#### Examples

Hero, no lazy:

```
{{< haz_img name="full_widescreen" lazy=false >}}
<img src="hero.jpg" alt="Hallway">
{{< /haz_img >}}
```

Float half square left; text wraps:

```
{{< haz_img name="half_left_sqr" >}}
<img src="photo.jpg" alt="Detail">
{{< /haz_img >}}
```

Smaller than full, centered (not floated):

```
{{< haz_img name="half_center_landscape" >}}
<img src="photo.jpg" alt="Product">
{{< /haz_img >}}
```

Natural file shape:

```
{{< haz_img name="as_is" >}}
<img src="photo.jpg" alt="As shot">
{{< /haz_img >}}
```
