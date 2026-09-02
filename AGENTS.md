# hugo-agent-zero — context for assistants

Stable facts and conventions. For session carryover (the diary), see [.agents/notes.md](.agents/notes.md). Notes home is HQ: [hugo-agent-zero/hugo-agent-zero](https://github.com/hugo-agent-zero/hugo-agent-zero). The SOT copy may lag.

## Communication

Assistant replies: follow the **Assistant style (default)** section in [.agents/notes.md](.agents/notes.md). A matching Cursor rule under `.cursor/rules/` reinforces the same preferences.

- Default to short, conversational replies (TL;DR first).
- Give the minimum useful answer first; add depth only when the user asks.
- For nuanced topics, offer: "Want the deeper version?" instead of auto-dumping detail.
- If the user shows confusion, switch explanation style (example, analogy, or concrete diff) rather than repeating the same framing.
- Avoid repetitive re-explanations; summarize what changed in one or two lines before continuing.
- When appropriate, offer more than one solution (e.g., "We can do A, B, or C").
- When appropriate, call out trade-offs and include key pros and cons.

## What this is

- **Hugo** static site (no Node/Python app in-repo).
- **Config:** [hugo.toml](hugo.toml) — `title` “Hugo Agent Zero”, menus (Home, About), **min Hugo 0.146.0**, `extended = false`.
- **Content:** [content/](content/) — e.g. `_index.md`, `about.md`; [archetypes/default.md](archetypes/default.md).

## How to work on it

- From repo root: `hugo server` (dev), `hugo` (build to `public/`).
- Ensure local Hugo meets the minimum in `hugo.toml`.

## Layouts and assets (mental map)

- **Shell:** [layouts/baseof.html](layouts/baseof.html) → [home.html](layouts/home.html), [single.html](layouts/single.html), [list.html](layouts/list.html), etc.
- **Partials:** atomic-style under [layouts/_partials/](layouts/_partials/) — `atoms/`, `molecules/`, `organisms/`, plus `utils/`, `child/` (brand SVGs, overrides), [sysManifest.yaml](layouts/_partials/child/data/sysManifest.yaml).
- **Styles:** [assets/css/simple/](assets/css/simple/) and [assets/child/css/](assets/child/css/).
- **Static:** [static/](static/) — copied as-is.

## Conventions for edits

- Match existing naming and partial structure; avoid drive-by refactors unrelated to the task.
- Search layouts for `TODO` when touching JS/CSS framework hooks.
- In YAML/front matter, a leading underscore on a key (for example `_config`, `_props`) means the key is intentionally parked/disabled and retained for reference. Treat this as a valid convention; do not flag `_`-prefixed keys as naming errors by default.
- Folder Atomics may include **`_preset_example.yaml`** — a non-loaded starter shape (like `.env.example`). Live presets are `preset_*.yaml` beside the Atomic and/or under `content/presets/`.
- **sysMan first:** if composition can live in the graph (`order`, named slots, `inst` → multiplier), do it there. Do not bake `fn_multiplier` (or equivalent stacking) into an Atomic. Named slots on the Atomic; multiply in sysMan. Others may cheat; HAZ stays pure. One fill slot → **`content`** (match `tag_tag_wrapper`); several slots → role names (`col_brand`, `close_icon`).

## Atomic render boilerplate

Every atom / molecule / organism **render entry** (file-based `*.html` or folder `index.html`) should follow the same shell. Reference (not loaded by Hugo): [.agents/boilerplate/_atomics.html](.agents/boilerplate/_atomics.html). Content FM masters in the same folder: [`_blog_single.md`](.agents/boilerplate/_blog_single.md), [`_page.md`](.agents/boilerplate/_page.md) — full prop catalogs with typical keys live and fringe keys `_`-parked for copy/paste. That folder is primarily for agents; humans can skim it via this section.

- Top locals: `source`, `child`, `thisObj`, `sysManifest`, `context`, `thisObjProps`, `thisChildren`, `thisSource`, `props`, `enabled` (with the `gt (len $thisObj)` guard).
- **`if enabled`:** emit `fn_html_comment` with `$thisSource`, then the Atomic’s body.
- **`else if enabled_false`:** `fn_partial` to the `enabled_false` child.
- **Parents** under `helpers/parents/` are for shared **output** only. Do **not** put the enabled / comment / enabled_false gate in the parent — keep that on the Atomic index (e.g. `cols_two_tag_wrapper_000` → parent for markup).
- **Organisms:** default to a **single file**. Use a **folder** only with a strong case (e.g. defaults + multiple presets such as `cols_two_tag_wrapper_000`). Not a hard ban — justify the folder.

## CSS naming (HAZ)

We are mostly classless (framework + element styles), but when we invent classes or IDs, follow this so we don’t collide with framework tokens (e.g. Pico `.container`).

- **Namespace:** HAZ-owned classes and IDs use the `haz_` prefix. Custom properties use `--haz_*` (e.g. `--haz_measure`).
- **Separators:** underscores only in our tokens — no hyphens in `haz_*` names (double-click friendly).
- **Identity classes are optional:** an Atomic does **not** need a class just because it exists. Prefer classless markup (framework + elements) when one instance is enough (e.g. a lone `<article>`).
- **When you do add an identity class:** base it on the Atomic/html name most of the time so grep and mental model stay aligned. If the Atomic name includes a role word (e.g. `wrapper`), keep it in the class too (`page_title_wrapper_000` → `haz_page_title_wrapper`) — rare exceptions only. Prefer `__` for true sub-parts of that block (`haz_page_title_wrapper__heading`), not for renaming away the Atomic’s own words.
- **Light BEM-y join:** `haz_<block>` and `haz_<block>__<element>` (e.g. `haz_header_site`, `haz_header_site__controls`). Do not build deep chains (`haz_a__b__c`); uniqueness stays at the molecule/block — organism wrappers compose with short selector chains if needed.
- **Page kind on `<body>`** (not UI state): layout/content hooks such as `haz_single`, `haz_list`, `haz_blog`, `haz_page` — set via `routes.yaml` `map_body_attrs`, not on the article shell.
- **Global UI state** (often on `html`/`body`, JS-toggled): `haz_state__<token>` (e.g. `haz_state__scrolled`, `haz_state__nav_open`). Prefer data attrs already in use (`data-theme`, etc.) where that pattern fits; don’t force every flag into `haz_state__`. Page kind is **not** `haz_state__`.
- **Framework classes:** never rename Pico (or other vendor) classes; don’t invent bare globals that frameworks own.
- **Child sites:** optional and up to the child. Child may reuse `haz_`, invent its own prefix, or overlap parent names — if that conflicts with parent, treat it as intentional. HAZ is **not** opinionated about a required `child_` (or other) prefix.
- **Migration:** apply on new work and **migrate as touched**; no blanket renames of leftover legacy tokens. First migrate pass (2026-07-29): header chrome, brand/SVG classes, nav/buttons/IDs, HAZ utilities, `haz_state__nav_open`.

## Hugo first — when we must

If Hugo already owns a site-graph concern and leans on it at build time, **use Hugo’s model** — do not re-own or subvert it. Otherwise HAZ / `sysManifest` / child data should own the feature.

Examples of Hugo-first: **menus** (`Site.Menus`, `pageRef`, `IsMenuCurrent`), taxonomies/terms, page dates, content bundles. Examples of HAZ-owned: composition (`layouts.yaml`), chrome assembly, CMS payloads, social link lists, presentation defaults.

## Hugo naming (match Hugo, not display English)

Prefer Hugo’s **native identifiers** in manifest `props`, `settings` keys, and front matter—not human labels.

- **Taxonomies:** Profile keys and `props.taxonomy` use Hugo’s **plural** taxonomy names (`categories`, `tags`) — same as `.GetTerms`, URLs, and typical front matter. Optional **`getterms`** on profile/props only when it must differ from the profile key. Display labels live in **`term`**. (`hugo.yaml` `category: categories` is an FM alias only.)
- **Dates:** Hugo field names (`publishdate`, `lastmod`, `date`)—not display words like “Published” / “Updated” (those belong in `settings.dates.*.term`).
- **Labels vs keys:** `term`, formats, `link_rel`, etc. are display/behavior in settings; do not use them as lookup keys.

When adding a feature, check [Hugo docs](https://gohugo.io/) for the canonical name before inventing a project alias.

## Session carryover

Chats can be lost after Cursor updates or new threads. [.agents/notes.md](.agents/notes.md) is the repo-backed **diary** (HQ is home; this SOT copy may lag).

**What notes are:** one file, dated sittings, newest first. Not daily files. Not Issues.

Notes exist to show others the time + thoughts that went into the project, remind us what we discussed, and give the next person context. Mention tickets in prose (`Open Issue #4 — Restore main tag + skip to main`). Do not use notes as the backlog.

**Layout:**

- **Now** (top, optional) — a few live lines for cold start (next ticket, hard locks). Strike when superseded; do not rewrite the rest of the file to match.
- **Focus** — historical snapshot. Leave it. New work goes in Meetings.
- **Meetings** — the diary. `### YYYY-MM-DD — …`, newest first. Never rewrite or delete an old sitting. A one-line status on an old entry is OK. Optional **Plans:** bullets link to [.agents/plans/](.agents/plans/) when Plan mode was used that session.

**Start of session (agent):**

- At the beginning of a **new chat** (or when the user asks to continue prior work), read `.agents/notes.md` — the **newest Meeting** and **Now** if present. Skim older entries only if context is unclear.
- Briefly acknowledge current focus in your first reply when relevant (one line, not a recap dump). Do not re-read on every turn in the same thread.
- If this looks like a **new session** and the latest **Meetings** entry is clearly stale (e.g. dated before today, or chat/transcript context shows substantive work since that entry), ask once:

  > I sense we're about to start a new session, but we never updated `.agents/notes.md` from the last session — would you like me to do the last session now?

  If yes, backfill a Meeting entry from what you can recover (prior transcript, git diff, or the user's recap). Do **not** rewrite Focus or old meetings. If no, continue without updating.

**End of session (agent):**

- **Explicit trigger:** User says **wrap up**, **meeting notes**, or **end session** → append a dated Meeting entry (newest on top). Strike a **Now** line if it changed. Do not rewrite Focus or prior sittings. If Plan mode was used, archive plans per **Plans (project archive)** above. HQ notes: branch + PR; do not merge `main`.
- **Implicit wrap-up:** If the user's language suggests the session is ending (e.g. good night, that's all for now, I'll pick this up tomorrow, signing off, done for today) **without** asking for notes, ask once:

  > Do you want me to update `.agents/notes.md`?

  Only update if they say yes. Do **not** append minutes on every reply or without confirmation when the trigger was implicit.

## Plans (project archive)

Cursor Plan mode saves to `~/.cursor/plans/` by default (outside the repo). **Git-tracked copies** live in [.agents/plans/](.agents/plans/) — same basename Cursor used (slug + hash). HQ is home; SOT copy may lag.

**When to archive:** Any session that used Plan mode for substantive work.

**On wrap-up** (with Meeting notes):

1. Copy each session plan from `~/.cursor/plans/` → `.agents/plans/` (skip if already present and unchanged).
2. Set frontmatter: `session`, `status` (`parked` | `in_progress` | `shipped`), `hq_issue`, `core_pr`, `child_pr`, `related` — omit keys that do not apply. See [.agents/plans/README.md](.agents/plans/README.md).
3. In the Meeting entry, add **Plans:** bullets linking to archived files (one line each: title, HQ issue, PRs, status).

**During Plan mode:** When creating or updating a plan that maps to kit work, record HQ issue # and expected PR repos in frontmatter or a **Traceability** section at the top of the plan body.

## Cursor-specific (optional)

- Long-lived **rules** can live in `.cursor/rules/` (see Cursor docs). This file is the portable, tool-agnostic entry point.
- **Plan mode:** Do **not** execute instructions that change the project (edits, non-readonly tools, shell that modifies state). Treat ambiguous asks as planning or discussion unless the user clearly asks to execute. **Double-check with the user:** “If you want me to code or apply changes, please switch to **Agent** mode.”
