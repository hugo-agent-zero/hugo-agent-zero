# Agent notes (diary)

**Home:** [hugo-agent-zero/hugo-agent-zero](https://github.com/hugo-agent-zero/hugo-agent-zero) (HQ). This SOT copy may lag.

This file is a **diary**: one file, dated sittings, newest first. Not daily files. Not Issues.

**Notes exist to:**

- Show others the time + thoughts that went into the project
- Remind us what we discussed
- Give the next person context so they can pick up the project. Context matters

Mention tickets in prose (`Open Issue #4 — Restore main tag + skip to main`). Do not use this file as the backlog. Issues stay the tickets; notes stay the story.

**Layout:**

- **Now** (top) — a few live lines for agent cold start (next ticket, hard locks). Strike when superseded; do not rewrite the rest of the file to match.
- **Focus** — historical snapshot. Leave it. New work goes in Meetings.
- **Meetings** — the diary. `### YYYY-MM-DD — …`, newest first. Never rewrite or delete an old sitting. A one-line status on an old entry is OK. Optional **Plans:** bullets link to [plans/](plans/) when Plan mode was used that session.

Stable kit facts belong in root `AGENTS.md`. **Plans** (Plan-mode artifacts) live in [plans/](plans/) — see **Plans (project archive)** in [AGENTS.md](../AGENTS.md).

## Assistant style (default)

- Default to **short**, **conversational** answers; skip preamble and recap unless asked.
- **No long brain dumps**—prefer a few sentences; use bullets only when they save time.
- Expand with detail, steps, or alternatives **only when the task needs it** or the user asks for depth.
- For code changes: brief **what / why**, then the diff or file pointers—avoid repeating what the files already show.
- If unsure, ask **one** clarifying question instead of covering every edge case.
- **“What do most themes / people do?”** — answer in **2–4 sentences** unless the user asks for depth.
- Notes preference: keep a trail — add newest items on top and use ~~strikethrough~~ for superseded items instead of deleting.

---

## Current status

### Now

- **Next sitting:** Pre-#21 in order — (1) [#26](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/26) light meta-debugger smoke on live (home + blog single + one page; Meta/X/LinkedIn; fix **global** head_tags only), (2) Pico **fuchsia** (close [#12](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/12), new issue; vendor in core + child `1_main`), (3) [#21](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21) HAZ.com content — **blog = FAQ/How To** (additive posts, e.g. swap Pico theme, change font; GH UI upload path for child-only tweaks).
- **Launch musts:** all done ([#4](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/4) closed 2026-09-01).
- **Issue first / PR workflow** locked; Mark merges; do not merge `main`.

### Focus

- **Next (when back):** HQ [#4](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/4) — `<main>` + skip-to-main. Last launch-must kit ticket before shifting to HAZ.com content. [#21](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21)/[#22](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/22) come from writing the site, not homework first.
- **Issue first (locked 2026-08-31):** HQ issue before coding. PR mentions `hugo-agent-zero/hugo-agent-zero#N`; issue gets the PR URL. Branch `feat/N-short-slug` when we remember. [#38](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/38). Agent opens PRs; Mark merges. Do not merge `main`.
- **Launch musts:** [#2](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/2) READMEs → HQ **done**; [#3](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/3) Issues/Wiki/Projects off on core/child/content **done**; [#5](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/5) default OG image **done** (core PR #20, child pin #20, Pages). [#4](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/4) still open.
- **Search DRY [#11](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/11) closed.** Toggle ≠ modal: `script_toggler` (class on `html`) vs `script_modal` (`showModal`). Menu vs search. Slot `inner` → `content`. Old hamburger/search JS parked then dropped from sysMan; delete files later [#36](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/36). Overlay look [#7](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/7)/[#8](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/8) closed (recheck if pink→lime [#12](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/12)). `fn_tag_script` stays with enqueue [#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34).
- **`content/pages/` is organization only.** Do not publish `/pages/` ([#37](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/37), content PR #2 merged). Children still publish.
- ~~**Tomorrow (2026-08-28), first:** Overlay **light mode**… Then README one-by-one; Issues home. **Contact form = v2.**~~ Overlay look closed enough ([#7](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/7)/[#8](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/8)). Contact still v2.
- **EOD 2026-08-27:** Search overlay Refine ~99% **dark mode**. Core PR #10 merged (`76b8ef9`); child pin + Pages. Parked: pink→lime / Godzilla; PF CSS as sibling repo; bookkeeping below.
- ~~**Paused (2026-08-27, afternoon):** Search overlay polish — Mark doing a full review later. **Open:** chip type is still Pagefind’s size, not the site default (hosts inherit; chips don’t). Card/chip background still parked (inspector). Core `main` `094beeb` (PR #4); child pointed at that (PR after). Live via content **pages** workflow.~~ **Superseded same day** — overlay polish ran through core PRs #5–#9 (`1fb3311`); live via content **pages**. Chip type inherit mostly landed; card vs chip fill still parked.
- ~~**After search is complete — bookkeeping:** (1) Notes home… (3) Universal modal JS… `inner` → `content`; `fn_tag_script`.~~ HQ exists. Modal vs toggler landed 2026-08-31. Still parked: kit vs HAZ.com org; `fn_tag_script` with enqueue [#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34).
- **Holy grail (2026-08-18):** GitHub Hugo modules + Pages **passed**. Public core / child / content + Pages = **kit shipped** (quiet alpha). SOT monolith stays local (no remote; don’t edit unless asked). Org clones: `C:\_au\work\hugo\dev\hugo-agent-zero-org\`.
- **Pagefind overlay shipped (2026-08-26).** Kit search is Pagefind 1.5.x Component UI, local assets, not CDN / hugomods. Overlay = HAZ `<dialog>` + `<pagefind-input>` + `<pagefind-results>` (not `<pagefind-searchbox>` / not their modal-trigger). Off = graph only (header search **and** `block_main_pre.search`). **`settings.search.pagefind` deleted.** Filters = next after overlay polish. Core PR #1 merged (`fcd3cd4`); child pinned + merged. Live: https://hugo-agent-zero.github.io/hugoagentzero_com-content/ — content Pages dispatch still needed after child merge (content has no rebuild on child merge).
- **Pagefind is kit search (locked 2026-08-20).** Not a `go.mod`; post-`hugo` indexer (`npx pagefind@1.5.2 --site public`). JS/CSS **local** (`public/pagefind/`, `relURL`). Index hook: `data-pagefind-body` on page/blog `<article>`.
- ~~**Next coding — Pagefind chrome:** POC works; layout/aesthetics next after Mark skims Pagefind modal+trigger docs.~~ **Done 2026-08-26** — HAZ dialog + header icon `showModal`; not Pagefind’s modal-trigger.
- ~~**Pagefind composition:** … named slots (`close_icon`, `inner`); … Parked DRY: rename `inner` → `content`; generic open JS; `fn_tag_script`.~~ **DRY 2026-08-31** — `content` slot; generic toggler + modal; `fn_tag_script` still enqueue.
- ~~**Parked (still):** overwrite core `static/defaults/meta_tag_default_image.png`…~~ **Done 2026-08-31** — HQ [#5](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/5).
- **Launch bar:** Search **POC unblocked**. **Contact form is kit** — we’ll pick a backend *we* like, then integrate (same arc as Pagefind). Mailto/social is not the n00b story. Vendor TBD; Hugo won’t POST for us. Other Atomics come from dogfood. Then HAZ.com content + READMEs.
- ~~**Launch bar:** Search POC unblocked. Email / social @ for contact is enough (form later, nicer on CF).~~
- ~~**EOD 2026-08-19:** Sit. First thing next: OG default image, **then** search spike.~~ Search went first. Workflow: **dev local, ship when tested** — but this sitting, module pins mean **push to GH to see it live**.
- ~~**Launch bar:** **Search is the blocker.**~~
- ~~**Next coding — search:** Header slot is `inst: todo`. Spike Pagefind vs hugomods/search.~~ **Pagefind won** (not hugomods/search, not Algolia as default).
- **Next big step — HAZ.com content:** build-in-public **alpha on GitHub Pages**. Not CF yet.
- **Proper HAZ.com (later):** cut over to **Cloudflare as origin**. Add **CF Web Analytics** in that same move (not GA; Matomo overkill for default HAZ). GH stays git. Skip CF-in-front-of-Pages.
- **Git (later):** GitHub = production. **Push-mirror / backup to GitLab** — not a second forge for work.
- **Live:** https://hugo-agent-zero.github.io/hugoagentzero_com-content/
- ~~**Tomorrow mop (parked, unpushed):** Pages subdirectory `baseURL`…~~ **Done 2026-08-19.** `fn_page_path_extract` (was `fn_page_route_path`) — clean path for routes + shortcodes. `fn_href_trim_host_root` + CSS `relURL` via `ExecuteAsTemplate`. HAZ favicon from on-scroll SVG; dropped `startup.png` / unused `favicon.ico`. Leave `favicon_000.png` untracked (source).
- ~~**Next (paused until a longer session):** 3-repo Hugo module split on **GitHub** (not GitLab). Need SSH keys / org setup. Then search as first optional module. Keep the monolith runnable until then.~~ **Done 2026-08-18.**
- ~~**Module split (locked 2026-08-17, not built):**~~ **Built.** Locked model: **core** = shared kit (PRs welcome); **child** / **child-content** = templates (copy, no PRs back). For now only **content** is a GitHub template. Child is the Hugo **build root**; content-push can trigger CI; the job still builds from child. Same org. Local: sibling checkouts + `HUGO_MODULE_REPLACEMENTS` with **abs** paths (relative `../` broke on Windows). FAQ `name` accordion is a non-issue (attrs).
- **Non-issue (FAQ exclusive open):** native HTML `name` on `<details>`. Layouts `props.attrs` already emit it (or not). Same name = page-wide one-at-a-time; omit = independent (preferred default). Not a HAZ knob; docs later if useful.
- **Recently landed (2026-08-17, later):** FAQ `details`/`summary` chrome — pink summary + Pico chevron masked to `--haz_chrome` at `1.5rem`; body copy stays `--pico-color`; always-on card panel (`--pico-card-background-color` + `--pico-card-box-shadow`) so light mode still reads as a block. Copyright holder is `settings.site.copyright` (not `site.name`); empty emits nothing.
- **Recently landed (2026-08-17):** Footer stacks and centers together at `max-width: 40rem`. Wordmark `max-width: 100%` / `height: 1.5rem`. Override SVG heights now use `rem` (not `em`).
- **Recently landed (2026-08-13, late):** Chrome pink follows **resting** Pico link color (`--haz_chrome` → `--pico-primary`), not hover. `fill: currentColor` on the home brand SVG picked up Pico’s `[aria-current]` / `:hover` (`--pico-primary-hover`). Wordmark/icons now set `fill` / mask `background-color` to `--haz_chrome` directly. Same token in light and dark (hex still theme-shifts for contrast). Small type vs large SVG can still look slightly different optically.
- **Shortcodes v1 landed (2026-08-12):** one strict `haz key="…"` content opening; optional call `enabled` is omitted=true / literal bool true only. Folder loader → registry (`direction` + `key_profile`) → `route_key` or `key_route` → shared layouts entry → existing `fn_partial` graph. No `map_child` needed. Missing/parked mapping falls back; present `enabled:false` hard-stops that exact context.
- **Pass B+ landed (2026-08-10):** catalog → one file Atomic hydrate proved with `tag_details_summary`: layouts node sources `cms/faq.yaml`, filters to one row, and merges that row into props (no list molecule). The same SOT row can feed different Atomics/columns at different tree positions.
- **Filter / collection direction (2026-08-10):** source-agnostic filtering is first-class. A master collection can hydrate lists or individual layout nodes; one SOT row may be reused at different points in the node tree, with each Atomic cherry-picking the columns it consumes and layouts owning placement/attrs/order. Single hydrate = first filtered row (use `limit: 1` to state intent). `limit`: omitted/negative = all, `0` = no rows, positive = cap.
- **Recently landed (2026-08-10):** `tag_details_summary` DOM lean-up — native `<summary>` has no identity class; details HTML emits directly (no automatic panel `<div>`). Authors may provide their own inner wrapper/attrs in trusted `details` HTML and select the outer disclosure with `details:has(> …)`. HAZ CSS uses direct-child selectors.
- **Recently landed (2026-08-10):** **`fn_collection_filter_run`** — always baseline row-`enabled`; `filter.enabled` (default true) gates match/order/limit; `filter.fn` override; missing fn → `hugo.IsDevelopment` warn+empty else `errorf` (message: node + fn + full filter). FAQ/socials call the runner.
- **Today (2026-08-08, wrap):** Collection noun migrate + row-contract doctrine; layouts folder split; #14 boilerplate masters; #12 brand/CTA process thin (`skip_render` post-step). Fly-forward mindset noted (unknown unknowns / balloon-grabs OK).
- **Recently landed (2026-08-08, late):** **#12 brand/CTA process thin** — extract `fn_folder_resolve_props` (merge returns props); `process_basic` = resolve → render; brand href + CTA `a_href` are thin post-steps. (Avoided Hugo `return` footgun on render path.)
- **Recently landed (2026-08-08, late):** **#14 boilerplate masters** — `.agents/boilerplate/_atomics.html` (rename), `_blog_single.md`, `_page.md`. Full prop catalogs; typical keys live, fringe `_`-parked; copy/paste into new content with minimal thinking. AGENTS.md pointer updated.
- **Recently landed (2026-08-08, late):** **layouts folder split** — `system_manifest/layouts/{layouts_root,atoms,molecules,organisms,multipliers}.yaml`; `fn_get_sys_manifest` `readDir`+merge (same pattern as `cms/`). Monolith `layouts.yaml` removed. Parked follow-on named **`library`** (child-carted or HAZ-shipped).
- **Recently landed (2026-08-08, late):** **`items` → `collection`** noun migrate (page resolve, `fn_list_000`, og video/audio, socials + fail-closed filter, parked enqueue). Same key everywhere a loopable row set is the contract.
- **Recently landed (2026-08-08):** **`fn_collection_filter`** — `props.collection` + `props.filter` (enabled → match eq/neq/in/nin → `order: random` → `limit`). FAQ CMS = collection rows only; demo attrs/filter on layouts. Yaml inst `eq` one key; headless `order: random`. Dogfood expected to find edge cases.
- **Recently landed (2026-08-07):** FAQ / `details`/`summary` POC — atom + list molecule + section header; layouts section + list wrappers (no-cheating); dual CMS doors stacked in pre_footer.
- ~~**Next (2026-08-08):** List `props.filter`…~~ **Pass B done.**
- ~~**Next (2026-08-07):** FAQ / `details`/`summary` chrome…~~ **Done enough for POC** (filter design parked, not built).
- **Today (2026-08-06, wrap):** Brand + **#10**/**#11** landed earlier; **#6** empty-title prefix/suffix gate done. Head_tags **architecture closed** (migrate/mop/peel + contract debt); remaining = retest + dogfood on haz.com (site = docs). CF/X parked.
- **Brand (shipped enough):** `brand_on_load` + `brand_on_scroll` Affinity redo cleaned into haz.
- **X / Twitter:** Account created; wire `twitter:site` / `twitter:creator` later (after CF or placeholders). Bluesky via OG.
- **Cloudflare:** Parked — timeouts / DNS; not blocking.
- **Debt/DX:** ~~**#6**~~ ~~**#10**~~ ~~**#11**~~ ~~**#12**~~ ~~**#14**~~ done. **#7** OG image w/h/type = **v2** (not beta). ~~**#1**~~ ~~**#2** account~~. Full head_tags retest early next week.
- ~~**TODO (brand — scroll monogram AZ → HAZ):**~~ Done enough 2026-08-06.
- **Drop / non-issue:** **#9** one-line `process.html` stubs — keep (transparent/explicit MO).
- **Later:** **#3** description/summary review; **#4** live URL meta debuggers; **#5** override/must-do matrix (can be haz.com content); **#8** demo FM alignment; ~~**#6**~~; **#7** v2.
- ~~**Next chrome — FAQ / section (plan locked):**…~~ **Shipped as POC 2026-08-07** — see Recently landed; filter next.
- **Shortcode proof:** `page` uses `key_route` on `/about/` + `/page-test2/`; `blog` uses `route_key` on `blog/*`. Exact `blog/demo-post-2` overrides the wildcard and repoints the same Markdown shortcode to a different layouts entry/Atomic message; demo post 1 remains on wildcard. Build and generated HTML verified. The shortcode stays dumb; contextual composition lives in manifests.
- **V2 superpower — parameterized shortcode as data source (not v1):** A future sibling to `haz` accepts a standardized payload; the manifest selects a child adapter/folder Atomic. Treat shortcode args as another provider beside CMS YAML, page params, headless, and Hugo-built collections. `defaults.yaml` defines the allowed contract; adapter whitelists/types/normalizes payload into props; normal HAZ graph renders. Unknown/B.S. args do not leak into props. Prototype in child, promote proven patterns to parent molecules/organisms without changing Markdown.
- ~~**TODO (v1 chrome — site tagline):**~~ **Done 2026-08-13** — `settings.site.tagline`; `tagline_000` in nav panel (below socials) and footer brand (below SVG).
- **Parked (discuss — single blog structure):** subtitle (`h2`?) + summary; where blog meta sits in that stack.
- ~~**TODO (child must-do — Twitter/X handle):**~~ Account created 2026-08-06; still need wire meta.
- ~~**TODO (low-hanging — default share image):**~~ **Done 2026-08-05** — `static/defaults/meta_tag_default_image.png` (1200×630); OG/Twitter defaults point at `/defaults/meta_tag_default_image.png`.
- **TODO (review — description / summary):** Not assumed broken. Avoid Hugo auto-`.Summary` into meta. Wire `.Description` if useful; keep opt-in list teaser pattern.
- **TODO (later — head_tags override matrix):** Table of Atomics × override surfaces + Must-Do for child? (`robots` → production `index,follow`, etc.).
- ~~**TODO (nice-to-have — drop process.html stubs):**~~ **Drop 2026-08-04** — keep explicit wrappers.
- ~~**TODO (debt — tagList vs defaults):**~~ **#10 done 2026-08-06** — `tag_white_list` top-level in Atomic contract file (sibling of `defaults` / `merge_paths`; old `$tagList` shape); extract in `fn_folder_process_basic`; index uses `index . "tag_white_list"`. CMS/layouts cannot override.
- ~~**TODO (debt — multi og video/audio):**~~ **#11 done 2026-08-06** — list-of-maps; noun now **`collection`** (2026-08-08 migrate). Page path still `meta.og_video` / `og_audio` as array/`false`; `defaults` = shared row *field* fillers, not row on/off.
- ~~**TODO (boilerplate kit):**~~ **#14 done enough 2026-08-08** — `_atomics.html` + `_blog_single.md` + `_page.md`. Expand later if head_tags props grow; keep masters in sync when adding page-get paths.
- **Agent boilerplate home:** [`.agents/boilerplate/`](boilerplate/) — `_atomics.html`, `_blog_single.md`, `_page.md`.
- **TODO (enqueue revisit, not now):** Parked `_enqueue*` — revisit later; enqueue ≠ socials.
- **Recently landed (2026-08-03, late):** **head_tags manual peel complete.** Settings `head_tags` parent emptied/removed. Static defaults under `static/defaults/` (`meta_tag_default_image|audio|video`); media helper: http(s) → `/` absURL → page/home Resources. Favicon + apple-touch assets in `static/`. `og:type` default `website`. `verification_000` back to **file** Atomic + layouts `part._file` → `child/atoms/head_tags/verification.html` (no double-park). Final proof later via live URL debuggers.
- **Recently landed (2026-08-03):** **head_tags mop done.** `head_tags_base` → `fn_head_tags_taglist`; `fn_folder_process_basic` + thin callers (15 head_tags + `socials_000` + `cols_two_tag_wrapper_000`). ~~Brand/CTA process left intentional~~ **#12 done 2026-08-08** (basic + post-step). Folder molecules today: socials, brand, cta_simple only — flat is fine when nothing to merge.
- ~~**Recently landed (2026-08-02):** **head_tags folder migrate…**~~ see migrate meeting; verification later corrected to file Atomic (2026-08-03 late).
- **Recently landed (2026-08-01):** Bucket B pilot + section/chrome naming parks; local Atkinson preload (no Google CDN).
- **Recently landed (2026-07-30, late):** `.agents/boilerplate/` move; `document_title_000` golden scrub; domain **HugoAgentZero.com**.
- **Recently landed (2026-07-30):** Brand SVGs; socials in **pre_footer**; FA masks; enqueue parked.
- ~~**TODO (debt — remaining head_tags → folders):**~~ **Done 2026-08-02** (migrate).
- ~~**Parked (mop — next):** DRY `process.html` + `head_tags_base` → `fn_head_tags_taglist`.~~ **Done 2026-08-03.**
- ~~**TODO (type scale / fluid fonts, not now):**~~ **Root fluid landed 2026-08-13** — `--pico-font-size: clamp(100%, 0.9rem + 0.35vw, 112.5%)` in `pico-override.css` (kept in the existing override; not a one-line extra file). **Still later:** heading-size utilities (`haz_type_*`) so Atomic visual scale can diverge from semantic `h1`–`h6`; Pico heading defaults stay as Markdown fallback.
- ~~**TODO (next chrome — socials …):**~~ **Socials landed 2026-07-30.** Remaining chrome: icon set + **pre_footer / mega-footer** via **`details`/`summary`** over a second hamburger: e.g. summary **“Footer Menu”** (or pre_footer panels) with thoughtfully curated links/lists underneath — optional depth, not always-on TMI. Contrast: mega-*menus* = noisy; a deliberate **mega-footer** / disclosure footer can work. Same primitive as CMS FAQ accordion.
- **TODO (layouts `part.decider` / children packs, not now — optional POC):** mid-tree decision sockets during layouts traversal — sibling to `part.folder` / `part.prep`, not a free jump across the graph. **vs filter:** `fn_filter_sys_manifest` rewrites the whole map once up front; decider chooses *at this node* during the walk. **vs routes:** routes = page front door; decider = hallway door. **Shape:** `part.decider: child/deciders/….html` on a node; decider may only select among options declared on **this** node. For one-of, return a child key under `children`. For many-of (header-like), introduce numbered packs `children_000`, `children_010`, … and decider returns which pack to walk; unnumbered `children` can stay shared gates (`enabled_false`) only. **Worth it if optional:** no `part.decider` → today’s behavior unchanged (default pack / plain `children`); adding the hook must not break existing graphs. Feels POC-able; open question remains product value vs complexity — park until a real multi-pack need appears.
- ~~**TODO (layouts folder merge):**~~ **Done 2026-08-08** — `system_manifest/layouts/*.yaml` by Atomic silo; `readDir`+merge in `fn_get_sys_manifest`. Optional follow-on still parked: **`library`** — either/or (same idea): (1) child carts a portable `layouts/library.yaml` (`level: library`, `group`/`inst`…), or (2) HAZ itself ships a growing standard library the child can point at / override. Name was briefly “boilerplate”; **library** ≠ `.agents/boilerplate/` content masters.
- **Cadence (locked 2026-07-28):** alternate **debt** ↔ **new** — one debt slice, then one new feature (or reverse), not all one pile. Prefer debt that unblocks or cleans the area you’re about to build in.
- **HAZ CSS naming (locked 2026-07-29):** see **CSS naming (HAZ)** in [AGENTS.md](../AGENTS.md) — `haz_` / `--haz_*`, underscores, light `block__element`, `haz_state__*`. Identity class optional (not every Atomic); when present, usually based on Atomic/html name. Page kind on `<body>` via routes (`haz_single` / `haz_list` + `haz_blog` / `haz_page`) — not `haz_state__`. **First migrate pass done** (header/brand/nav/SVG/utilities + parked Simple CSS synced).
- **cols_two_tag_wrapper_000 (landed 2026-07-29):** shared organism (folder) + parent helper; presets `preset_header` / `preset_footer`; slots `col_brand`, `col_other`, optional `row_below` (header nav). Live header/footer point here. Legacy parked: `headers/_header_000.html`, `footers/_footer_000.html` (layouts entries removed). Organisms default to **file**; this folder is the strong-case (tag + presets).
- ~~**Next (now):** Header chrome ~**shippable / 90%+** — pause here. Resume later with **footer** organism → **socials** (HAZ data) → CMS **FAQ** (`details`/`summary`). Brand SVGs still FPO (“Brand Name”); user may replace with Agent Zero art.~~ **Superseded:** brand + socials landed 2026-07-30; see **Next session** above.
- **Ship path (locked mindset, 2026-07-27):** finish Agent Zero site chrome/content on the **monolith** → **parent/child Hugo module split** → **search as a module** (Pagefind/Lunr) → ship. Don’t invent the full Atomic catalog up front; grow parent Atomics from real child needs.
- **Pico + header (landed 2026-07-28):** Pink theme active (`pico.pink.min.css`; vanilla `pico.min.css` kept to demo swap). `--haz_measure` body grid + header rows (no Pico `.container`). Sticky opaque header. Light/dark via generic `script_color_scheme` (`mode: attr` → `data-theme`; class mode still supported). Child override: light `--pico-primary` darkened for link contrast; `--haz_chrome`; nav size/gap + open animation + full-bleed open-menu border. Simple parked `_framework_css_simple_css`.
- **Preset example naming (locked):** beside-Atomic starter shape = `_preset_example.yaml` (not loaded; copy/adapt). Live presets stay `preset_000.yaml` / `content/presets/...`.
- **File → folder migrate rule (2026-07-24):** when revisiting a cluster — keep file-based pieces that stay in use but **`_`-prefix** parked/superseded files; **convert active contentful pieces to folders**; if a preset example is implied, add one under `content/presets/...`. Don’t blanket-rewrite shared shells (`tag_a_href`, etc.) just for consistency.
- **First real site = Agent Zero (dogfood):** the product site ships on HAZ itself; build **site + documentation together** so the public face proves the system and teaches it in the same pass.
- **File ≈ folder (locked):** same Atomic; folder just makes CMS-y layering easier (`defaults` + preset + provider + process). Migrate to folders when a provider/payload helps — not as a blanket rewrite.
- ~~**Next (header_000 hygiene):** …~~ **Mostly done** — dual brand molecule + Pico chrome restored; footer is the complementary organism next.
- **Molecule vs layouts-only (2026-07-24):** don’t fear molecules when layouts could assemble the same thing. Workflow: **prototype in `layouts.yaml`**, then promote what proves to be a **standard pattern** into a named molecule (e.g. dual brand). One-offs can stay layouts-only.
- **Brand dual molecule real (2026-07-27):** `brand_logo_dual_000` owns slots `on_load` / `on_scroll` / `scroll_js` (layouts fills them). Deleted `brand_dual` multiplier + wrapper molecules. CSS wrap spans live in the molecule index.
- **Brand marks in core (2026-07-24):** SVGs live in haz as `atoms/brand/brand_on_load.html` (ex-name) and `brand_on_scroll.html` (ex-logo). Child keeps setup copies: `_brand_on_load_example.html`, `_brand_on_scroll_example.html` (not loaded — customize & point layouts when overriding).
- **Brand dual folder wired (2026-07-24):** `molecules/brand/brand_logo_dual_000` — folder molecule (`part.folder`), Hugo home href + aria defaults. Header brand points here.
- **Hugo string values:** `fn_get_page_value_from_string` now resolves `.Site.Home.RelPermalink` / `home` (and Permalink variants) for brand href defaults.
- **Pre-launch hygiene (2026-07-24):** prefer correct Atomic tier / folder contracts now over “fix later” — avoid shipping half-baked taxonomy.
- **Speculative stubs removed (2026-07-24):** deleted `section_header_000`, `card_000`, `cta_standard_000` (and their group folders). Keepers remain: `document_title_000`, `cta_simple_000` (ex-announcement).
- **Announcement → CTA rename (2026-07-24):** molecule `announcement_000` → `cta_simple_000` under `molecules/ctas/`; CMS/presets/headless paths updated. Layout **slots** keep `announcement_bar` / `announcement_bar_wrapper` (placement ≠ Atomic).
- **Organism assembly breakthrough (2026-07-23):** We already have the answer. Organism ≈ structured multiplier: HTML shell with named child slots; `layouts.yaml` children point at reusable molecule/atom nodes. Multiplier = flat list-y assembly; organism = same idea with structure. Do **not** invent mini-organisms inside molecules (no deep `args`/`props`/`children` nesting under card CTA). Making organisms work too hard / `layouts.yaml` not hard enough was the wrong turn.
- **Slot ≠ Atomic (2026-07-23):** Placement (announcement bar, card action region) ≠ molecule identity. CTA is a thing (finite family: e.g. future `cta_simple_000` from announcement shape, stub `cta_standard_000` = title+copy+action). Layouts/organisms assign which CTA fills which slot.
- ~~**Molecule stubs parked (2026-07-23, likely trim tomorrow):** `section_headers/section_header_000` …~~ **Removed 2026-07-24.**
- **`document_title_000` page-get hardening (2026-07-23):** `get_page.yaml` declares Params path; `fn_source_page_resolve` uses it (optional `cms.get` override); stopped using `level/group/inst` for page provider. Legacy flat `document_title_000.html` removed. Preset starter → `_preset_example.yaml` (was `_preset_template`).
- **Head-tags folder pilot shipped:** `document_title_000` folder-based (`defaults` + `process` + `index` + content preset) via `part.folder` + `provider: page`.
- **`provider: page` adapter:** `fn_source_page_resolve` + layered merge; migrated nodes do not pull from `settings.yaml` (legacy-only for unmigrated head tags).
- **Head tags architecture direction aligned (today):** team agreed head tags should move to the same folder-based contract model used by CMS-enabled Atomics (defaults + preset + provider + process), with `provider: page` as the canonical source semantic for page-derived head-tag values.
- **Head tags consistency decision (today):** avoid maintaining a second “file-only settings pattern” for head tags; exceptions should live in per-component `process.html` logic, not in a separate architectural standard.
- **Head tags rollout strategy refined (today):** migrate one or two head-tag nodes first (pilot), keep legacy path intact during the transition, and verify output parity before scaling the conversion.
- ~~**TODO (head_tags refactor — finish folder migrate):**~~ **Superseded** — migrate + peel done 2026-08-02/03; verification is file Atomic again. Struck 2026-08-04 triage (#13).
- **Organism composition principle reaffirmed (today):** organisms are composition templates made from molecules (with optional helper atoms), while molecules remain the primary contract-bearing unit.
- **Provider naming refinement (today):** canonical local manifest-file provider renamed from `data` to `file_local` (`part.cms.provider: file_local`). Resolver aliases keep `data`/`src_data` working during transition.
- **Underscore cleanup pass completed (today):** old `X*`/`x*` parked keys were migrated to `_` or removed where dead blocks/backups were confirmed obsolete; active YAML/front matter now follows `_` parked-key convention.
- **CMS namespace update (today):** local file-backed source namespace now lives at `sysManifest.cms.file_local` (`cms/file_local.yaml`), replacing `cms/data.yaml`.
- **Underscore parked-key convention (today):** in YAML/front matter, `_`-prefixed keys are now the standard way to park/disable a prop without deleting it (retain for reference); agents/reviews should treat this as intentional rather than as a naming error.
- **CMS/provider + config contract locked (today):** `part.cms.provider` is now canonical (with legacy `type` fallback). `level/group/inst` remain structural locators. This aligns manifest wording with resolver dispatch and removes mental translation friction.
- **Source namespaces stabilized (today):** `sysManifest.cms.headless` and `sysManifest.cms.data` are now the active provider namespaces. `data` supports the same `config + props` entry shape as headless for copy/paste consistency.
- **Preset layering + path strategy locked (today):**
  - single-preset resolution remains: `layouts part.preset` wins; else provider entry `preset`; no preset merging.
  - folder nodes can use short preset refs (e.g., `preset_000`) resolved beside the Atomic.
  - file nodes require explicit preset paths (warning on bare names).
  - child-owned configs live under `content/configs/child/atomic/...`; CMS content remains under `content/cms/...`.
- **Merge-path enforcement hardened (today):** only component `defaults.yaml` controls `merge_paths`. Incoming `merge_paths` from configs/provider payloads/layout overrides are stripped/ignored to keep contract authority in one place.
- **Announcement pilot now validates provider swap (today):** same node can run `provider: headless` or `provider: data` using the same level/group/inst hierarchy and consistent config layering.
- **Next (fresh session):** decide whether to extract a generic process orchestrator after 2-3 more folder-based Atomics (avoid premature DRY); keep current per-Atomic `process.html` pattern until repetition is proven.
- **Prep dispatch baseline locked (today):** `layouts.yaml` announcement node now follows the aligned shape (`part.file` + `part.prep` + sibling `source` + `props`). `fn_partial` now acts as traffic-cop dispatcher (direct render vs prep redirect), and prep re-enters `fn_partial` for final `part.file` render with hydrated props.
- **Preps naming/housekeeping shipped (today):** renamed announcement orchestration path from `helpers/adapters` to `helpers/preps`; switched manifest key to `part.prep`; removed old adapter file; clean `hugo` build verified.
- **Next (fresh session):** generalize prep boilerplate (shared source-get + shared handoff + merge fn reuse) so one prep can support `source.type=headless` and `source.type=src_data` without duplicating plumbing.
- ~~**Headless pipeline wired + re-org pending (today):** announcement now renders through `announcement_000.html` using `map_headless -> bundle params.props/merge_paths -> instance overrides` with parity confirmed; next step is housekeeping re-org: keep FE atoms “atom-like”, keep DRY parent render contract, and consider renaming orchestration layer to **`preps`** (between CMS-like sources and presentation).~~
- **Headless bundle source direction (new, big win):** scaffolded `map_headless.yaml` + `content/headless/` cascade + first atomic bundle (`announcement_000`) with `params.props` + `params.merge_paths`; `announcement_000_src_data` render path intentionally unchanged for now while evaluating a pivot from `src_data` records to headless bundle-backed records with layered overrides.
- **Announcement wrapper-parent refactor (today, temporary victory):** `announcement_000_src_data` now acts as controller/wrapper with local `defaultProps` + `mergePaths`; generic helpers added (`fn_source_payload_resolve`, `fn_merge_fake_deep`); presentation moved to `helpers/parents/atoms/announcement_parent`; contract is now `props.source.*` (no `props.component` fallback); build verified clean.
- **`src_data` namespace cleanup (today):** renamed `components.yaml` → `src_data.yaml`, switched manifest lookup pointer `level: components` → `level: src_data`, and updated `fn_get_sys_manifest` + announcement resolver wording; clean build verified.
- **Announcement fake-merge POC (active):** announcement pilot now uses `component_data_announcement_000.html` + `fn_announcement_payload_resolve` (POC-specific helper). Override contract switched to `props.component.props`; layered merge proof still verified.
- **Manifest namespace normalization (today):** `layouts.yaml` now follows the same wrapped pattern as other manifests: top-level `layouts` with `layouts_root`, `atoms`, `molecules`, `organisms`, `multipliers`. Runtime lookups now use `sysManifest.layouts.*` (entry map = `sysManifest.layouts.layouts_root`). Build verified clean.
- **Data components POC (new):** Migrated `announcement_bar_000` payload from `layouts.yaml` props into `components.yaml` with manifest pointer (`props.component.level/group/inst`) and atom-local resolver in `announcement_000.html`. Behavior verified unchanged.
- **Routes schema + entrypoint (today):** `all.html` is now a pure Hugo entry adapter (no `layouts|all` dependency). `routes.yaml` owns route policy using `enabled_true` / `enabled_false` branch objects (`key_layouts_entry`, `key_html_attrs`) in both `map_child` and `defaults`. `map_layouts_entry.enabled` remains the hard gate.
- **CSS + chrome (next):** **`fn_body_class`** + `<body>` classes (WP-style); **footer** organism; Pico polish (scheme toggle, header measure). ~~`simple-x-agent-zero.css`~~ → pico-x / pico-override.
- **Routes html attrs (done):** `<html>` attrs from **`routes.yaml`** — site base + dynamic overlay verified on live build (TODO class keys prove tiers). Swap TODO1/2/3 for real body/layout classes when ready.
- **Routes + regular pages:** Child router **verified**; map fallback key = **`.Section`**; rename **`content/page/` → `content/pages/`**; wire **`map.pages`** when executing.
- ~~**`all.html` entrypoint (active):** Root wrapper uses `fn_get_route_type` for policy (`route_type`) and `layouts|all` for manifest source. Home and other kinds verified through `all.html`; `x_*` root templates retained temporarily during soak.~~
- **Blog listing:** Wire **`blog_index_000`** meta/content/pages; **`blog_index_meta_wrapper_000`** still placeholder.
- **sysManifest first (decided):** Atoms-heavy; routes give path-level control; optimization later.

### Architecture / direction

- **`collection` row contracts by source (working rule, 2026-08-08):** **`props.collection`** = array of row maps (a loop is coming) — same noun from page FM, CMS, headless, or Hugo-built lists. **Row semantics differ by source** (best-effort while flying; ah-has in a week or two are expected, not failures):
  - **CMS catalogs** (FAQ, socials): managed rows → fail-closed row `enabled` + optional `props.filter` (`fn_collection_filter`).
  - **Page params** (og:video / og:audio): FM slice or `false` → normalize to `collection`; shared defaults fill row *fields*; presence + resolvable `url` emits. No row-`enabled` required today.
  - **Hugo-built** (taxonomy / author terms via `GetTerms`): synthetic rows; Hugo already gates pages (`draft` / publish). Layouts node **`enabled`** still turns the whole Atomic on/off.
  - Do **not** force catalog row-`enabled` onto page/Hugo collections unless a real need shows up (e.g. FM opt-out rows).
- **Hugo first — when we must (locked, 2026-07-24):** if Hugo owns a site-graph concern at build time, use it (don’t reimplement/subvert). Otherwise HAZ owns it. Menus → Hugo; socials/composition/CMS → us. See [AGENTS.md](../AGENTS.md#hugo-first--when-we-must).
- **First ship target (2026-07-24):** Agent Zero’s own site + docs on HAZ (dogfood). Not a separate demo client first.
- **Organism model (locked direction, 2026-07-23):** Organism = layout/structure assembly (closer to multipliers than to CMS molecules). Building blocks already exist; missing piece was recognizing assembly belongs in `layouts.yaml` + thin organism HTML (`header_000` pattern), not new nested molecule graphs. Provider/CMS can sit on the assembly node; molecules stay reusable and provider-agnostic.
- **FE structure vs slots:** Often similar language, not 1:1 synonyms — don’t bake placement names into Atomic identity.
- **Parent vs child (conceptual):** `hugo.toml` = thin parent wiring (imports, `baseURL`, minimum config). **Customization** (site name, meta, composition) should lean on **`sysManifest`** + child partials/assets, not bloated parent config.
- **Monorepo for now;** split parent/child **Hugo modules** after Agent Zero chrome/content is shippable — then search as a module. Virtual merge of `layouts/` + `assets/` at build time is a feature. Growing Atomics into parent from real child needs is the model.
- **Stubs transition:** Moving from kind-specific root stubs to one `layouts/all.html` hook. Hugo remains data/runtime; routes + sysManifest own render policy. Keep legacy root stubs as `x_*` during validation, then remove.
- ~~**Route policy vs layout source (new split):** `route_type` is computed and used for routes/defaults/html attrs. Manifest lookup source is separate (`layout_source` concept; currently hardcoded to `layouts|all` in `all.html`).~~
- **Route policy now fully in routes:** `all.html` always enters the router; no manifest lookup source gate. Route branching is explicit per profile/default via `enabled_true` / `enabled_false`.
- **Component vocabulary (locked):** use **data components**, **content components**, **hybrid components** for model/source distinctions (rendering stays Atomic).
- **Content model:** Home copy = `content/_index.md` (not `home.md`). **`/content/` = pages** (front matter, `params.head_tags`, body) — taxonomies in `hugo.yaml` are Hugo’s grouping wrapper; **`content/{taxonomy}/{term}/_index.md`** merges meta/copy onto term URLs (verified on `author_0001`). **`content/pages/`** (rename from `page/`) = generic pages with optional `url:` to hide folder segment from published URL; `.Section` still follows disk path. Pagination (`/page/2/`): **canonical → parent** when wired. Non-Hugo lists (e.g. socials) → prefer `data/*.yaml` + atoms; **main nav stays Hugo menus**.
- **Nav vs socials:** Similar `ul`/`li` shape, different ownership — nav = Hugo `Menus` (site graph); socials = our data. Shared list/row partials still a target; today [`nav_list_000.html`](../layouts/_partials/haz/atomic/atoms/nav_list_000.html) / [`default_000.html`](../layouts/_partials/haz/atomic/organisms/sections/default_000.html) still inline loops.
- **Hugo naming:** Manifest/settings keys follow **Hugo identifiers** (plural taxonomy profile keys like `categories` / `tags` matching `.GetTerms`; date fields like `publishdate` / `lastmod`); human labels live in `term` only. Full rule: [AGENTS.md](../AGENTS.md#hugo-naming-match-hugo-not-display-english).
- **Date stack:** `fn_page_date_resolve` (method + profile via `settings.dates.default`) → `fn_get_page_value_from_string` → for lastmod: `fn_page_date_lastmod_show` (`require_explicit`, `must_be_after` key, `must_be_after_seconds`) → `fn_page_date_compare`. Atoms print; fns decide/return.
- **Author stack:** `authors.yaml` (merged in `fn_get_sys_manifest`) — stable `author_id` + `authors: [term, …]` on posts. **`fn_page_author_resolve`** (`Params.author_id`; author **term** pages: `.Name`). **`fn_page_author_terms`** — multi-author list; yaml `name` via **`.Name`** (not `.LinkTitle`); links `/authors/{author_id}/`. Taxonomy = filter + URL; **`content/authors/{term}/_index.md`** merges with term page (title, `.Content`, `params.head_tags` like about). Term pages use `term_000` / `default_000` until custom author-term layout.
- **Blog meta markup (live):** `single_blog_meta` → `single_blog_meta_wrapper_000` → [`tag_dl_list_wrapper_000`](../layouts/_partials/haz/atomic/atoms/tag_dl_list_wrapper_000.html) → `single_blog_meta_dt_dd_list` multiplier. Verified on demo posts.
- **`haz/` partials (done):** `layouts/_partials/` = **`haz/`** + **`child/`** only. Structure: `haz/atomic/` (atoms, molecules, organisms; `templates/` + `pages/` README stubs for atomic tiers 4–5), `haz/helpers/` (`fn/` + `fn/page/`, `multipliers/`, `parents/`). Manifest `part.file`, `settings.yaml` `row_partial`, layout stubs, and internal `partial` calls use `haz/*` paths. See [`haz/README.md`](../layouts/_partials/haz/README.md).
- **CSS stack (current):** `pico.min.css` → `pico-x-agent-zero.css` (HAZ chrome + classless body measure) → `child/.../pico-override.css`. Prefer `--pico-*` overrides; no Pico utility-class religion. Simple parked (`_framework_css_simple_css`).
- ~~**Routes as bottleneck:** [`routes.yaml`](../layouts/_partials/child/data/system_manifest/routes.yaml) — **rules** → `routeKey`; no rule → **`.Section`**; **`map_child[routeKey]`** → child; miss → **`defaults[route_type]`**. Shared **[`route_resolve_parent`](../layouts/_partials/haz/helpers/parents/route_resolve_parent.html)** feeds **`fn_router_processor`** (child) and **`fn_router_processor_html_attrs`** (dynamic `<html>` overlay). **`parents/`** = abstracted base (OOP parent); **`fn/`** = concrete processors.~~
- **Routes as bottleneck (current):** [`routes.yaml`](../layouts/_partials/child/data/system_manifest/routes.yaml) — `rules` → `routeKey`; no rule → `.Section`; `map_child[routeKey]` and `defaults[route_type]` each branch via `enabled_true` / `enabled_false` objects (`key_layouts_entry`, `key_body_attrs`). `map_layouts_entry` resolves `level/group/inst` and enforces hard gate `enabled`.
- ~~**Routes entry-shape discussion (new):** exploring `map_child` as route “start child” selector with explicit entry object (e.g. `layouts_entry` / `layout_entry`), possibly mirroring `level/group/inst` shape but resolving exactly one start node. Guardrail: routes selects entry; `layouts.yaml` remains component graph owner.~~
- ~~**Html attrs (live):** **[`fn_html_attrs`](../layouts/_partials/haz/helpers/fn/fn_html_attrs.html)** = **`fn_get_routes_html_attrs_default`** (required `settings.html_attrs_key` → `map_html_attrs`) + dynamic tier + **`fn_merge_attrs_dict`** (`class` concat). **[`tag_html_open`](../layouts/_partials/haz/atomic/atoms/tag_html_open.html)** calls orchestrator; **`html_open.props.attrs`** removed from manifest. Routes owns `<html>` attrs; manifest owns other component attrs.~~
- **HTML/Body attrs split (current):** global `<html>` attrs restored to `layouts.yaml` (`html_open.props.attrs`); route overlays renamed to body attrs (`map_body_attrs`, `key_body_attrs`); dynamic identity moved to `<body>` path metadata (`data-path-segments`, `data-path`, `data-path0..n`).
- **`fn_get_route_type`:** Uses Hugo **`.Layout`** when FM sets `layout:`; else Kind (`page` → `single`). Optional child hook now supported via `child/utils/fn_filter_get_route_type.html` (safe no-op when absent). Prefer **routes** over custom Hugo layouts for composition — see routes doc backlog.
- **Body classes (planned):** [`baseof.html`](../layouts/baseof.html) has bare `<body>` today; target WP-style helper + optional `params.body_class`; can reuse routes html attrs pattern or parallel fn stack.
- **`{{ block "main" . }}` vs passing `sysManifest`:** `block` only receives `.` (page context), not a dict like `partial`. Options: (1) `.Scratch.Set "sysManifest"` in `baseof` before `block "main"`; (2) small shared partial that rebuilds manifest; (3) child router partial on `.Kind` / `.IsHome`.

### Open questions

- **Confirm organism = `header_000` pattern (tomorrow):** After re-reading `header_000` + its layouts children, decide keepers among today’s stubs and whether card-section assembly is just another organism shell + multipliers/children.
- ~~**CTA family naming (later):** `announcement_000` → `cta_simple_000`? …~~ **Done 2026-07-24** (slot names kept).
- **`fn_get_route_type` / layout FM:** Resolved via **`.Layout`**; long-term prefer routes rules over FM `layout:` (e.g. about) where possible.
- **`home.html`:** Route through **`default_router_parent`** (like single/section) vs keep thin stub / drop if redundant with Hugo layout lookup.
- ~~**routes entry object naming:** settle `layout_entry` vs `layouts_entry` (team preference leaning `layouts_entry`).~~
- ~~**multipliers placement convention:** top-level `multipliers` restored for clarity; keep `_multiplier` naming explicit for readability.~~
- **Manifest namespace follow-through:** keep all layout domains under `sysManifest.layouts.*`; avoid re-introducing root-level siblings in `layouts.yaml`.
- ~~**Component override shape (announcement pilot):** prefer `props.component.props` over `props.component_overrides` so override payload sits under the component object and follows existing prop mental model.~~
- **Component naming convention (pilot decided):** use filename prefix for type clarity (`component_data_*`, future `component_content_*`, `component_hybrid_*`) rather than splitting by nested folders first.
- **Root stubs cleanup:** When to remove `x_single/x_section/x_taxonomy/x_term/x_list` after all.html soak testing.
- Router-in-child vs Scratch + per-kind stubs for passing manifest into `main`.
- Where first **data-driven** slice lands: menu YAML, socials, or testimonials.
- **Router debug:** Layout stubs print `.Section` only — add `routeKey` + map hit/miss when polishing router (backlog).

### Backlog

- ~~**CSS base → Pico (next):** …~~ **Landed 2026-07-27** (vanilla + pico-x + child override; Simple parked).
- ~~**CSS naming convention (revisit / establish):** …~~ **Locked 2026-07-29** — see AGENTS.md **CSS naming (HAZ)**; migrate legacy `tsys_*` / `header_site` / `#btn-*` as touched.
- ~~**Pico polish (header ~90%):** …~~ **Mostly done 2026-07-28** (measure, data-theme, pink, sticky, nav). Left: Agent Zero brand SVGs; FOUC head script optional; fluid type later.
- **Footer + socials + FAQ:** footer organism (complement header); socials from HAZ data source; CMS FAQ via `details`/`summary` (Pico accordion).
- **`authors.yaml` placement (later):** currently root `system_manifest/authors.yaml` merged as `sysManifest.authors`. Feels closer to CMS/entity reference data than layouts/settings/routes; consider moving under `cms/` (or `cms/entities/`) once we decide if authors are `file_local`-shaped or a dedicated entity registry. Update `fn_get_sys_manifest` + author resolvers when doing it — not urgent.
- **Molecules root hygiene (later):** loose one-offs like `button_toggle_000.html` sit at `molecules/` root while newer work uses group folders (`announcements/`, `cards/`, `section_headers/`). Open question: real domain folders vs a catch-all for true one-offs (`misc` is weak). Also naming nits when grouping (e.g. `section_headers` vs `sections` vs `headers`) — discuss when touching, don’t force now.
- **Schema skill idea (new):** add an Agent Zero schema skill to generate page-level JSON-LD from `.Page`/bundle content + global site schema defaults (org/website), so humans avoid manual per-page schema key/value params; include schema.org + rich-result guidance in the skill.
- **Routes polish:** Replace TODO1/2/3 with real **`map_html_attrs`** keys; DRY layout **`$route`** stubs via **`fn_get_route_type`** (include **`layout`** FM / section-leaf nuance); optional `enabled` on `site_default` if ever needed.
- **Routes execution:** `content/pages/` rename + `map.pages`; clean test keys (`Xpage`, `page-test2`); about section vs leaf rules as needed.
- **`home.html` + router:** Revisit whether home layout stub still needed; wire main through router if yes.
- **all.html rollout:** Keep `x_*` root stubs for one more validation pass, then remove and commit single-entry layout approach.
- **Home manifest parity:** Refactor `layouts|home` to match single/blog wrapper pattern (e.g., `home_main_wrapper_000` + inner `home_main_000`) so home follows the same composition convention as `single_page_000` / `single_blog_000`.
- ~~**Fallback flags review:** Revisit `layouts|all.children.default_allow_false` vs `allow_default_true` semantics and whether both are needed; currently `default_router_parent` only uses `default_allow_false`.~~
- ~~**Routes schema refactor (candidate):** evaluate moving route start-point wiring from `layouts|all.children` aliases into `routes.map_child.{key}.layouts_entry` while keeping `layouts.yaml` as graph source of truth.~~
- **Home cleanup next:** finish `layouts|home` cleanup and sub-partials/sub-components with tighter scope (avoid architecture drift while implementing).
- **Identity hooks (TODO):** add per-page/term/taxonomy identity layer (classes and/or `data-*` attrs) with collision-safe path strategy.
- **Body classes + footer + AZ CSS:** See Focus — before Hugo parent/child module split.
- **Search (after module split):** Static client-side (Pagefind or Lunr + JSON index); header `search` slot in manifest is `inst: todo`; Hugo docs are guides, not baked-in search.
- **`layouts.yaml` inventory (planned):** Tree map of manifest keys — not started.
- **Doc:** Update [`AGENTS.md`](../AGENTS.md) mental map for `haz/` + `child/` (README in haz exists).
- **Doc — routes:** Write routes guide — HAZ policy layer (`rules`, `map_child`, `map_html_attrs`, `defaults`, `settings`). **Custom Hugo layout** (`layout: contact` + `contact.html`) is dev-only and rare; **`fn_get_route_type`** passes FM layout name through as routes key → needs matching **`defaults.{name}`** (and usually path rules / `map_child`). Prefer **routes + manifest** for page composition; author FM layout only at dev discretion (update routes when used).
- **HTML attrs naming review (later):** revisit dynamic bool/value class naming in `fn_html_attrs_dynamic` after real usage (`has/no` vs `*-true/*-false`, hyphen vs underscore for bool tokens, and collision-safe value namespace).
- **Components rollout:** extract reusable resolver (`fn_get_component_data`) from announcement POC; document pointer contract (`props.component.level/group/inst`) and error behavior for missing keys.
- **Overrides model (next):** explore 3-level override chain (component-native defaults → data component → usage/instance) with explicit non-recursive semantics (replace by default; no automatic deep merge).
- **Fake deep merge design (next):** implement selective merge by declared key-path arrays (manual/data-driven deep-merge effect without full recursive merge).
- **Component placement follow-up (later):** revisit whether prefixed component files should stay in-place or move under a dedicated subfolder once more pilots exist.
- **Hugo image resource metadata (#7, v2):** When wiring `og:image`, check image resource width/height/type from `GetMatch`; use only when reliable. Not beta.
- ~~**Title + prefix/suffix:**~~ **#6 done 2026-08-06** — empty resolved base skips emit in `document_title_000` + `meta_og_basic` `og:title`.
- **`fn_get_page_value_from_string` rename:** → `fn_get_page_method_value` (README backlog); param `value` → `method`.
- **Blog meta polish:** Row wrapper classes on `<div>`; `dl_aria_label` on [`tag_dl_list_wrapper_000`](../layouts/_partials/haz/atomic/atoms/tag_dl_list_wrapper_000.html); index meta content.
- **CSS rename/add:** Introduce `simple-x-agent-zero.css`; update `framework_css_simple_css` manifest keys; migrate content from `simple-extended.css`.
- **Authors (later):** Multi-author **bio** (bio atom uses primary `author_id` only); custom `author_term_000` (yaml names on term pages); `content/categories|tags/{term}/` for term copy + head tags.
- **DRY: taxonomy vs author term fns (later):** [`fn_page_taxonomy_terms`](../layouts/_partials/haz/helpers/fn/page/fn_page_taxonomy_terms.html) vs author terms — keep two files for now.

### Recently landed

- **2026-07-23:** `get_page.yaml` + page-resolve path for `document_title_000`; nested defaults/index stubs for `section_header_000`, `card_000`, `cta_standard_000`; organism insight validated against existing `header_000` (assembly, not nesting hell).
- **Announcement fake-merge POC (updated):** added `fn_announcement_payload_resolve`; announcement now renders via prefixed file `component_data_announcement_000.html`; contract moved to `props.component.props`; layered merge proof works (`component` data retained while nested usage override for `a.text_anchor` wins).
- **Layouts namespace migration (shipped):** normalized `layouts.yaml` to wrapped schema (`layouts.layouts_root`, `layouts.atoms`, `layouts.molecules`, `layouts.organisms`, `layouts.multipliers`); updated lookups in `baseof`, root stubs, `fn_partial`, `fn_partial_from_entry`, and `fn_get_sys_manifest`; build verified clean.
- **Routes branch-object schema (shipped):** `map_child` and `defaults` now use `enabled_true` / `enabled_false` objects with `key_layouts_entry` + `key_html_attrs`; processors updated to read branch objects.
- **All entry decoupled (shipped):** `all.html` no longer reads `layouts|all`; `default_router_parent` no longer depends on `default_allow_false`; `layouts|all` removed from `layouts.yaml`.
- **Routes html attrs (verified):** `route_resolve_parent`; `fn_get_route_type`; `fn_router_processor` refactor; `fn_get_routes_html_attrs_default`, `fn_router_processor_html_attrs`, `fn_merge_attrs_dict`, `fn_html_attrs`; `tag_html_open` wired; `html_open.props.attrs` cleared from `layouts.yaml`. User verified `<html class="color-scheme-dark class-todo-*">` on home, blog, about, taxonomies.
- **all.html + home pilot (verified):** Added `layouts/all.html` wrapper using `fn_get_route_type` + `default_router_parent`; prefixed root stubs with `x_` during tests and confirmed pages route through `all.html` (explicit `ALL` marker). Home also renders through `all.html` when `home.html` is prefixed.
- **Route-type extension hook:** Added optional child hook `child/utils/fn_filter_get_route_type.html`; core checks `templates.Exists` and falls back gracefully when hook is absent.
- ~~**Routes schema:** `key_child` / `map_child`; `settings.html_attrs_key`; `key_html_attrs` on rules, map entries, defaults; `map_html_attrs` with `enabled` on dynamic entries.~~
- **Git:** Repo initialized; [`.gitignore`](../.gitignore), [`.gitattributes`](../.gitattributes), project-local identity + `core.eol=lf`. Initial commit includes **home_main** refactor.
- **Home layout:** [`home.html`](../layouts/home.html) → one `fn_partial` → `templates/home_main_000` multiplier (five `main_*` children moved under manifest). User renamed inst to `_000` convention.
- **Multiplier stack:** [`parents/multiplier_parent.html`](../layouts/_partials/parents/multiplier_parent.html); [`multiplier.html`](../layouts/_partials/templates/multiplier.html) delegates to parent (`.bak` kept); [`multiplier_2`–`_4`](../layouts/_partials/templates/) thin wrappers with fixed `order` slices.
- **Cleanup:** Removed dead `hamburger_icons` / old `multiplier_2` API; fixed corrupted `false:` block in yaml earlier in session.
- **Session carryover:** `.agents/notes.md` restructured; [`AGENTS.md`](../AGENTS.md) + [`.cursor/rules/session-carryover.mdc`](../.cursor/rules/session-carryover.mdc).
- **Routes manifest shape:** `routes.yaml` — `rules` + `map_child` + `map_html_attrs` + `defaults` + `settings`.
- **Blog meta taxonomies:** [`hugo_page_taxonomy_dt_dd_000`](../layouts/_partials/atoms/hugo_page_taxonomy_dt_dd_000.html), [`fn_page_taxonomy_terms`](../layouts/_partials/utils/fn_page_taxonomy_terms.html); plural profile keys (`categories` / `tags`); `format: list|inline`, delimiter inside `<li>` via list fn `suffix`; category + tag verified on demo posts.
- **Generic list fn:** [`fn_list_000`](../layouts/_partials/utils/fn_list_000.html) + [`fn_list_row_link_000`](../layouts/_partials/utils/fn_list_row_link_000.html); taxonomy fn builds items → delegates loop/row partial.
- **Date atom cleanup:** [`hugo_page_date_dt_dd_000`](../layouts/_partials/atoms/hugo_page_date_dt_dd_000.html) slimmed; [`fn_page_date_resolve`](../layouts/_partials/utils/fn_page_date_resolve.html), [`fn_page_date_lastmod_show`](../layouts/_partials/utils/fn_page_date_lastmod_show.html), [`fn_page_date_compare`](../layouts/_partials/utils/fn_page_date_compare.html). `settings.dates.default: publishdate`; lastmod profile: `require_explicit`, `must_be_after: publishdate`, `must_be_after_seconds: 0` (fixed seconds unit; baseline via fn_get key). Hugo partial quirk: single `return` at end of fns, no early `return bool`.
- **AGENTS.md:** **Hugo naming** section — keys match Hugo identifiers; labels in `term`.
- **Authors POC:** [`authors.yaml`](../layouts/_partials/child/data/system_manifest/authors.yaml) (`name`, `slug`, `bio`); `hugo.yaml` `author: authors`; resolve + terms + dt/dd + bio atoms. Multi-author on demo-post-1 and demo-post-2. [`content/authors/author_0001/_index.md`](../content/authors/author_0001/_index.md) merged term page. Test inst toggled dt/dd vs bio. Placeholder mock in `x_blog_meta_wrapper` uses `author_0001` link (not yaml `slug`).
- **Blog meta stack (prod):** [`tag_dl_list_wrapper_000.html`](../layouts/_partials/haz/atomic/atoms/tag_dl_list_wrapper_000.html); manifest chain `single_blog_meta_wrapper_000` → dl → `single_blog_meta_dt_dd_list`; removed test path; index meta placeholder.
- **`haz/` reorg (complete):** Copy → internal path rewrites → manifest + layout stub flip → `xxx_*` legacy trees deleted (two commits). `_partials/` = `haz/` + `child/`; Hugo layout hooks stay in `layouts/*.html`.
- **Routes clarity (session):** Map key `"page"` was Hugo `.Section` from `content/page/`, not layout type; `/about/` uses Section `about` + `defaults.single` → `single_page_000`.

---

## Meetings

### 2026-09-01 — #4 shipped; debt tidy; pre-#21 queue

**Shipped / closed:** [#4](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/4) `<main>` + skip-to-main (core + child PRs; `main: false` test on home/blog index; restore defaults child #23). [#40](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/40) dropped parked Simple from child sysMan (child #24). [#41](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/41) Pagefind dialog moved below footer (child #25; live OK). [#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34) comment: composition slots vs enqueue lanes — no `block_main_post_enqueue`.

**Kit stance:** Launch-must bar cleared. Module workflow (core → child pin → content Pages) feels slow then **right** — review at each layer = confidence. Ready to **alpha / dogfood** HAZ.com; not “finished product.”

**Pre-#21 (agreed):** Don’t go crazy on debuggers — smoke [#26](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/26) on a few URL shapes so new pages inherit good meta; wider pass after real content. Then Pico pink → **fuchsia** (bolder; [#12](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/12) lime/Godzilla superseded). Then [#21](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21).

**Parked:** [#22](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/22) Getting Started; contact form v2; enqueue [#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34).

**EOD — #21 content model:** Site docs via **blog as FAQ/How To** — one question per post, keep adding (swap Pico theme, different font, etc.). Pipes/architecture elsewhere; issues stay tickets. **GH-only path:** download Pico CSS → upload to child `assets/child/css/pico/` → sysMan `1_main: child/css/pico/…` (no core PR required). Copilot + Codespaces can help; bare GH UI needs the how-to, not magic.

**Plans:**
- [#41 dialog + enqueue note](plans/%2341_dialog_%2B_enqueue_note_af4fe94a.plan.md) — HQ [#41](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/41), child [PR #25](https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/25); shipped
- [Drop Simple sysMan](plans/drop_simple_sysman_917a01c3.plan.md) — HQ [#40](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/40), child [PR #24](https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/24); shipped

### 2026-08-31 — HQ execute; search DRY; launch musts; /pages/; pause on #4

**Next:** [#4](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/4) `<main>` + skip. Mark out (errands).

**Process:** HQ Issues as shared brain. Issue **before** code ([#38](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/38)): PR `Refs hugo-agent-zero/hugo-agent-zero#N`; issue gets PR URL. Agent PRs; Mark merges.

**Search DRY ([#11](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/11) closed):** Toggle (class on `html`) and modal (`showModal`) are **not** one script. Overlay look [#7](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/7)/[#8](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/8) closed (recheck on [#12](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/12)). Slot `inner` → `content`. Old JS parked then removed from sysMan; delete files [#36](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/36). `fn_tag_script` → [#34](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/34).

**Launch musts:** #2/#3 done (READMEs → HQ; Issues/Wiki/Projects off). #5 OG image live. #4 not started. #21/#22 = writing HAZ.com.

**`/pages/`:** Folder is organization only ([#37](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/37); content PR #2 merged). No public section index.

**Git:** HQ has no PRs for kit work — those live on core/child/content. Open filter empty after merge is expected.

### 2026-08-27 — Search overlay Refine; inspector day; haz_pf parked

**Shipped (org, core `main` through PR #9 `1fb3311`):** Overlay CSS in `pico-x-agent-zero.css`. Field 26rem / results rule full-width / cards 34rem at ≥40rem. Dialog `overflow: hidden`; `html.haz_state__searching` locks page scroll. Cards/chips `border-radius: inherit` (vanilla boxes — Pico radius is for controls, not `li`/`div`; card class is `.pf-result-card` not `.pf-result`). Field: 3px `--haz_chrome` border, inherit radius/weight, end padding 3.5rem. Clear: chrome fill, inherit radius, inset/height vs border. Result/chip links = site `a` (chrome, underline, `--pico-primary-hover`). Child pins followed each core merge; live = content Actions → **pages** (**new** run, not re-run).

**Unmerged tonight:** `feat/search-clear-nudge` — clear `5px` / `calc(100% - 10px)`, no summary `margin-bottom`, `.pf-heading-chips` `padding-inline-start: 1rem`. Create PR, then child pin + Pages.

**Locked / learned:** `unset` is not a hole (winning declaration; non-inherited → `0`). `inherit` on radius only works if the parent has a radius — overlay `dialog` doesn’t. Matching PF’s `(3,1,0)` + restating values is the stopgap. **Real fix:** **`haz_pf.css`** we own and edit (2026), dump/demote `pagefind-component-ui.css`. Magnifier color is baked into `--pf-icon-search` SVG data URI — leave it; PF-WTF list. Cadence: commit per tweak, one PR per look, agent does not merge `main`. `gh` not on PATH — compare URLs.

**Parked:** `haz_pf.css` peel after this look is in bed. Light-mode glance (tokens should follow; check chrome rule, clear inverse, card borders). Pink → lime-y green / Godzilla–Monster Zero — `--pico-primary` / `--haz_chrome`, not search-only. Card vs chip fill. `pagefind-config` `base-url` for project Pages. Semver tags on core. Notes home / kit org / universal modal JS / `inner` → `content`.

**Mood:** Inspector-vs-Pagefind ate the day. Don’t call search complete until the nudge PR is live and Mark looks once more (dark + light).

**Next:** Merge `feat/search-clear-nudge` → child pin → new Pages. Fresh-eye overlay pass. Then `haz_pf.css`.

### 2026-08-26 — Pagefind overlay Atomic-ified; UX polish parked overnight

**Shipped (org):** Peeled POC blob `search_pagefind_000` into folder atoms (`pagefind/*`) + organism `search_pagefind_modal_000` (`<dialog id="haz_search_pagefind_modal">`). Shared emit `pagefind_el_parent` (YAML underscores → kebab). Overlay pie: assets → config → input → results. Header: `button_search` clones hamburger; `svg_search_000` + `svg_close_x_000`; `script_search_000` (`showModal` / `close`, `haz_state__searching`). Core PR #1 merged (`main` `fcd3cd4`); child pin + overlay sysMan merged. Live after content Actions → **pages** dispatch.

**Locked (overlay):** `<pagefind-searchbox>` is the floating combobox — wrong for binary overlay. `<pagefind-config>` is invisible instance setup, sibling of assets. Off = omit from graph (not a settings flag). **sysMan first:** named slots on the Atomic; multiply in sysMan; don’t bake `fn_multiplier` into an Atomic. One fill slot should be **`content`** (organism still says `inner` — rename parked). Cadence named: POC → Refine → DRY; DRY not this merge.

**UX feedback (live, go one-at-a-time then Mark said related items can share a PR; some are discuss):** (1) SVG hover = Pico link hover — **done locally**, child `feat/chrome-icon-hover` `e912429`, pushed, no PR yet. (2) Modal open animation — ship. (3) Longer input + ~1.25rem — ship. (4) “Hit return to search”? — discuss; overlay is already as-you-type. (5) Instant search — yes, debounce 300. (6) Parent vs child result rows — Pagefind page + heading chips; restyle or hide. (7) Term highlight — `<mark>` + `--pf-mark` already. Close X = same `svg_close_x_000` as menu.

**Parked (not tomorrow morning unless it falls out of UX):** project-home 4th org repo for notes/AGENTS/Issues; generic dialog JS; `fn_tag_script`; content workflow comment still mentions `settings.search.pagefind`. Local SOT `AGENTS.md` has uncommitted sysMan-first + `content` slot convention. Core local checkout may still sit on `feat/search-pagefind-modal` (merged).

**Git:** Keep **branch + PR**. Mark likes it — review on GitHub Files changed keeps him in the loop. Agent does not merge `main` unless asked.

**Next:** First thing 2026-08-27 — finish search UX loose ends on the hover branch (discuss items before coding them). Don’t merge until Mark reviews.

### 2026-08-20 — Pagefind kit search POC live

**Locked:** Pagefind is what HAZ **offers**. Not hugomods/search (JSON/`.Content` vs our graph). Not Algolia as default (account/keys per child; optional later, same pattern as CF analytics). Core owns the header **slot** + index hooks; indexer is post-`hugo`, not a Go module.

**Shipped (org, not SOT):** `search_pagefind_000` — Component UI modal (`compact`, `hide-shortcut`), `relURL` bundle so Pages subdirectory works. `data-pagefind-body` on page + blog articles (home included via `single_page_wrapper_000`). Child `settings.search.pagefind: true` (atom ANDs with layouts `enabled`). Pages CI: `npx -y pagefind@1.5.2 --site public` after hugo. Live confirmed working. **hugo server** has no index unless you copy `public/pagefind` → `static/pagefind`.

**Optional:** `settings.search.pagefind: false`; or header search child `enabled: false`; or swap `inst`. Park article `data` → `_data`. Omit CI Index search step if you drop Pagefind.

**A11y (parking chrome):** Modal is native `<dialog showModal()>` — good. Compact icon-only + hidden shortcut is the HAZ choice: SR still get `aria-label="Search"`; sighted keyboard users get no hint; **Ctrl+K can fight the browser**. Next pass: HAZ icon + `modal.open()`, and/or show shortcut / switch to `/`.

**Composition (remind on chrome pass):** Peel Pagefind into Atomics (icon, JS, CSS, modal) so remove/restore is graph, not a monolith helper. POC blob is fine until then.

**Local, not CDN:** Pagefind writes JS/CSS/WASM into `public/pagefind/`; we link those. Keep it that way.

**Pins:** core `b232f4b` → child `a52d56a` → content `e30164c`.

**Next:** Mark reads Pagefind modal/trigger docs; then chrome. OG default image overwrite still parked. **Contact form:** kit will ship one — pick a backend we’re happy with, then integrate (not mailto-as-the-offer). Hugo has no form backend; host list can mention Kinsta later. HAZ.com content + READMEs after search looks honest.

### 2026-08-19 — subdirectory URL mop; sit and think

**Shipped (org, not SOT):** Clean path extract renamed **`fn_page_path_extract`** (single job: page → site-relative path; routes/shortcodes are callers). Live blog meta back after child pin. HAZ brand icons in child `static/` (on-scroll SVG as `favicon_000.svg`, 32×32 ico, 180 apple-touch). Dropped `startup.png` / `apple-touch-startup-image` / unused `favicon.ico`.

**URL mop:** Hugo `relURL`/`absURL` on a leading `/` is **host-root** and drops the Pages project folder. `fn_href_trim_host_root` before those funcs (tags, href build, og/twitter media). CSS `url("/…")` never went through Hugo — `pico-x-agent-zero.css` + child `pico-override.css` now `{{ "path" | relURL }}`, stylesheet helper `ExecuteAsTemplate` only when the file contains `{{`. Local subdir build: fonts, FA socials, favicon, apple-touch, `og:image` all under `/hugoagentzero_com-content/…`.

**Pins:** core `0693168`; child `0586d49`. Pages CI is on **content** — re-run that workflow (no content commit this mop).

**Workflow (locked enough):** develop local; ship when tested. GH build time is not the dev loop.

**EOD:** Quiet alpha is already on the internet. First thing next session: new **OG default image** → core `static/defaults/meta_tag_default_image.png` (same name, 1200×630). Then search. Contact stays email/social. Stop for today.

### 2026-08-18 — modules + Pages landed; holy grail; pause to think

**Shipped:** GitHub org [hugo-agent-zero](https://github.com/hugo-agent-zero). Four public repos + private monorepo backup. Challenge #1 (modules from GitHub) passed. GH Pages POC passed. Baseline 40 pages.

| Repo | Role |
|---|---|
| [hugo-agent-zero-monorepo](https://github.com/hugo-agent-zero/hugo-agent-zero-monorepo) | Private SOT backup |
| [hugo-agent-zero-core](https://github.com/hugo-agent-zero/hugo-agent-zero-core) | Public kit (MIT) |
| [hugo-agent-zero-child](https://github.com/hugo-agent-zero/hugo-agent-zero-child) | Public build root (MIT); imports core + `hugoagentzero_com-content` |
| [hugo-agent-zero-child-content](https://github.com/hugo-agent-zero/hugo-agent-zero-child-content) | Public **template** (MIT) |
| [hugoagentzero_com-content](https://github.com/hugo-agent-zero/hugoagentzero_com-content) | HAZ-owned content; Pages CI lives here |

**CI:** `hugoagentzero_com-content/.github/workflows/pages.yml` — on push to `main`, checkout **child** into `site/`, Hugo 0.152.2 + Go, `GOPROXY=direct`, `hugo mod get` content `@ ${{ github.sha }}`, `--baseURL https://hugo-agent-zero.github.io/hugoagentzero_com-content/`. Does **not** auto-pull latest core unless child’s `go.mod` pin is already bumped.

**Landmines / already-fixed:** Go module zips omit any folder named `vendor` — Font Awesome vanished until `static/vendor` → `static/third_party`. Markdown `cover.svg` was relative → RSS 404; core `render-image.html` now uses page-bundle `Resources.GetMatch` → `.Permalink`. Child pin `c646dd3`. Demo post 1 SVG had an invalid control character (cleaned in content).

**Parked for tomorrow (Pages subdirectory):**
- Blog meta missing on live posts — **not** the module split. RelPermalink is `hugoagentzero_com-content/blog/…`, so `routes.yaml` `blog/*` misses; fallback `single_page_000`. Local org core has unpushed `fn_page_route_path.html` + wires in `route_resolve_parent`, `fn_shortcode_route_candidates`, `fn_body_attrs_dynamic`. Local verify with Pages `baseURL` restored `haz_blog` + `.haz_blog_meta`.
- Favicon 404 — preset `href: /favicon_000.svg` (same root-absolute class as `og:image` / apple-touch). **Also** replace AZ artwork with on-scroll HAZ (`brand_on_scroll.html`) + `.ico`.
- CSP `img-src 'self'` in head_tags may still bite subdirectory/CDN.

**Next moves (not tonight):** Plenty to tighten — public READMEs, Getting Started, repo hygiene, template vs kit story. Then **use** it: try the Hugo search module as the first optional third-party import on child (prove modules compose, don’t invent HAZ search yet). We’re closer.

**Parked / later:** Stupid-easy Getting Started for the content template (`go.mod` path + point child at it). Micro.blog = RSS follow, not HAZ hosting (their Hugo overlay ≠ `go.mod`). Email `@hugoagentzero.com`. HAZ.com / Cloudflare origin. Stale SOT `README.md` TODOs. Don’t touch SOT except notes.

**Mood:** Grail found. Stop. Think next moves, then use it.

### 2026-08-17 — module split direction locked; paused for a longer session

**Locked, not built:** Three Hugo modules — core / child / content. Host = **GitHub** (Copilot Pro ~$10; GitLab + Duo Pro ~$50 out). Private **child** is the build root so public content CI never holds a token that reads chrome. Same org; don’t split forges; don’t GitLab-first then migrate n00bs. Hosted Copilot can edit child without a local clone; still need CI preview (no `hugo server`).

**Paused:** Actual split + SSH/org setup needs a longer session (aim tomorrow). Monolith stays the dogfood site.

**Also:** FAQ exclusive `name` = non-issue (layouts `attrs`). Notes tweak applied.

### 2026-08-17 — notes catch-up; resume footer responsive

**Backfill from 2026-08-13 late:** After the tagline/chrome commit, announcement link rest was darker than the brand SVG; hover matched the SVG. Cause: Pico paints `a:is([aria-current], :hover, :active, :focus)` with `--pico-primary-hover`, and `fill: currentColor` on the home wordmark followed that. Fix: chrome fills use `--haz_chrome` (`--pico-primary`) explicitly. Light/dark share the token. Residual “two pinks” on small type vs large SVG is optical, not a second variable.

**Parked / next:** Exclusive FAQ `name` is a non-issue — attrs already emit `name=` if wanted; default is omit. Then modules.

**Also this session:** Footer responsive — stack + center at one `40rem` query (no wrap-then-center). Footer wordmark `1.5rem`; remaining override SVG heights converted `em` → `rem`. Prefer `rem` for chrome unless a size must track local font-size. FAQ details chrome (pink summary/chevron, card panel + shadow for light mode). `settings.site.copyright` as legal holder, separate from `site.name`.

**Files:** `pico-override.css`; `settings.yaml`; `copyright_000.html`; layouts `atoms.yaml`; `.agents/notes.md`

### 2026-08-13 — nav panel socials + site tagline; chrome pink unified

**Shipped:** Mobile nav panel (`#haz_nav_main_panel`) stacks `nav_main` + reused `socials_000`. Site tagline from `settings.site` (HAZ-owned, not `hugo.yaml`); `tagline_000` atom uses `fn_get_nested` — dropped a mistaken `site_setting_value` atom. Placed below socials in the panel and under the footer brand SVG. Fluid root type (16→18px) in `pico-override.css`. Active nav weight removed (underline only).

**Pink mismatch:** Pico keeps two pinks — `--pico-primary` (links/text; dark `#f7708e`, light overridden to `#9d1945`) vs `--pico-primary-background` (`#d92662`, buttons). Chrome uses `--haz_chrome` → `--pico-primary`. ~~`fill: currentColor` so wordmark/icons match tagline/link text.~~ **Corrected later same day:** explicit `fill`/`background-color: var(--haz_chrome)` — `currentColor` followed Pico current-page/hover. Tagline selector is `p.haz_tagline` so it beats Pico’s `p { color: var(--pico-color) }`.

**Parked:** Footer responsive nits; heading-size utility classes; remaining light style polish on the panel/tagline.

**Next:** GitLab / parent-child Hugo module split, then search as first optional module.

**Files:** `pico-override.css`; `settings.yaml`; `tagline_000.html`; layouts atoms/molecules/organisms; header preset; `site_setting_value_000.html` removed; `.agents/notes.md`

### 2026-08-12 — contextual shortcodes shipped; module transition next

**Shipped:** Full v1 `haz` shortcode path: shortcode folder manifests load into sysManifest; strict call gate (`enabled` omitted or literal bool `true` only); registry dispatch; exact → parent wildcard → default candidates; `route_key` + `key_route` resolvers; shared terminal layouts-entry validation; development comments for unresolved mappings; handoff to normal `fn_partial` traversal. No parallel renderer and no `map_child`.

**Live proof:** Added `page` shortcode calls to About and Page Test (`key_route`) and `blog` calls to both demo posts (`route_key`, `blog/*`). Both initially converged on shared note nodes. Then exact `blog/demo-post-2` → `blog_route_010` → a distinct Atomic message while demo post 1 retained wildcard output. No Markdown change for the override. Hugo build clean; generated output inspected.

**Architecture confirmation / v2:** A future parameterized sibling is naturally another data provider: standardized shortcode payload → manifest-selected child adapter/folder Atomic → `defaults.yaml` contract whitelist/type normalization → ordinary props/graph render. Not v1; major v2 capability. This reinforced that HAZ sources, adapters, contracts, and graph boundaries are sound.

**Next:** Start GitLab/module work deliberately: inspect current remote/repo state, define parent vs child/site ownership, split without losing the runnable dogfood site, document the resulting workflow, then implement search as the first optional module. No push performed in this session.

**Files:** `layouts/shortcodes/haz.html`; shortcode resolver/parent helpers; sysManifest loader; `system_manifest/shortcodes/*.yaml`; layouts molecules; About/Page Test/demo-post content; `.agents/notes.md`

### 2026-08-11 (midday pause) — shortcode YAML contract mocked and reviewed

**Built (data only):** Added `system_manifest/shortcodes/{registry,route_key,key_route,layouts_entry}.yaml` with unwired mock data. Stable content call remains `{{< haz key="…" >}}`. Registry selects direction and internal `key_profile`; `route_key` is literally route → grouped keys → layouts entry, while `key_route` is key → grouped route rules → layouts entry. Shared terminal registry provides `level/group/inst`; normal HAZ traversal takes over there. No loader/resolver/shortcode code yet.

**Semantics:** Missing or `_`-parked contextual key means no match and continues toward wildcard/default. A present `enabled:false` mapping is an intentional hard stop for that exact slot/context; the same shortcode remains active elsewhere. Default mapping is the simple same-everywhere shortcode. Missing registry/profile/entry fails closed; optional development-only `fn_html_comment` can explain why.

**Communication:** Author story stays simple: shortcode creates a named opening in Markdown; HAZ mapping decides what Atomic subtree fills it. Route/key orientation is advanced internal organization, not required author knowledge. Layout hooks remain direct graph slots around content; Hugo shortcodes are openings inside content.

**Next:** Add folder loader and shared processing around the YAML, then kick both directions and decide from evidence whether `map_child` is useful.

### 2026-08-11 (pause) — contextual shortcode contract POC planned

**Direction:** One author-facing `haz` shortcode (`key="…"`) creates a stable opening in content and enters the existing HAZ graph. Registry decides each key’s orientation: `route_key` (vertical/page-context first) or `key_route` (horizontal/message first). Proposed split manifest: `shortcodes/{registry,route_key,key_route,layouts_entry}.yaml`; one shared resolver/renderer path. Start without `map_child`, then build/kick both orientations and add that layer only if true/false profile rerouting proves necessary. Plan saved as `contextual_shortcodes_poc`.

**Clarified:** Hugo expands shortcode calls in content markup during page rendering; layout Atomics use partials/the graph directly. Routing chooses which block; Hugo page context/filtering chooses block data. Site tagline added to the v1 TODO, placement deliberately undecided.

**Small cleanup:** Reordered `routes.yaml` sections to match runtime mental flow (`rules` → `map_child` → `map_layouts_entry`); Hugo build clean. Change remains uncommitted at this pause.

**Next:** Let the contract simmer, review the plan, then implement the POC. After shortcodes: module split → search module → HAZ.com dogfood.

### 2026-08-10 (wrap) — single-row hydrate; shortcode direction

**Shipped:** Pass B+ proved a file Atomic can self-hydrate from a filtered CMS collection row without a list molecule. `tag_details_summary` receives `cms/faq.yaml`, runs the common dispatcher, and merges the first result into props. `fn_collection_filter` limit semantics are now explicit: omitted/negative = all, `0` = no rows, positive = cap. Zero and negative behavior were exercised; final Hugo build clean.

**Direction:** Filtering any source is first-class composition: one SOT row can be reused through the node tree while each Atomic consumes only its columns. HAZ complexity stays opt-in (“HAZ Lite” can remain simple). Next critical path: dumb shortcode → `shortcodes.yaml` alias → existing layouts graph; then parent/child module split → search module → HAZ.com dogfood. Contextual shortcode routing is compelling (route/params may repoint a stable alias) but parked until a real use justifies it.

**Files:** `layouts/atoms.yaml`, `layouts/molecules.yaml`, `tag_details_summary.html`, `fn_collection_filter.html`, `.agents/notes.md`

### 2026-08-10 — filter runner override hook

**Shipped:** `fn_collection_filter_run` is now the public collection-filter entry. Row `enabled` remains the always-on baseline; `filter.enabled: false` skips only match/order/limit. Layout nodes may set `filter.fn` to a custom partial. A missing custom fn warns + returns no rows in development, and fails non-development builds with `errorf`; diagnostics include the Atomic node, missing path, and full filter object. FAQ and socials use the runner.

**Next:** Pass B+ POC — filter a catalog to one row and hydrate a simple file Atomic from a node in `layouts/atoms.yaml`.

**Files:** `fn_collection_filter_run.html`, `fn_collection_filter.html`, FAQ/socials indexes, `layouts/molecules.yaml`, `cms/socials.yaml`, `.agents/notes.md`

### 2026-08-08 (wrap) — collection migrate, layouts split, boilerplate, #12

**Shipped:**
- **`collection` noun migrate** — page resolve, `fn_list_000`, og video/audio, socials (+ fail-closed filter), drop `items` hoist, parked enqueue rename.
- **Row-contract doctrine (working):** CMS catalogs = row `enabled` + filter; page-param og = field defaults / presence; Hugo `GetTerms` = synthetic. Unknown unknowns / balloon-grabs expected — fly forward.
- **Layouts folder split** — `system_manifest/layouts/{layouts_root,atoms,molecules,organisms,multipliers}.yaml`; `readDir`+merge. Parked follow-on renamed **`library`** (child-carted or HAZ-shipped).
- **#14 boilerplate** — `_atomics.html`, `_blog_single.md`, `_page.md` (typical live / fringe `_`-parked masters).
- **#12** — `fn_folder_resolve_props` + thin brand/CTA post-steps.

**Next:** Pass B+ atom hydrate; shortcodes later; head_tags retest / dogfood when back.

**Files:** layouts split + loader, collection migrate surfaces, `.agents/boilerplate/*`, brand/CTA `process.html`, `fn_folder_process_basic`, AGENTS.md, `.agents/notes.md`

### 2026-08-08 (late) — `collection` noun migrate + row-contract doctrine

**Shipped:** `items` → `collection` everywhere a loopable row set is the contract — `fn_source_page_resolve`, `fn_list_000` + taxonomy/author/FAQ callers, og video/audio defaults/index, socials (CMS + fail-closed via `fn_collection_filter`), drop `items` hoist in `fn_folder_process_basic`, parked enqueue rename. Build + spot-check OK.

**Doctrine (working, not brittle):** same `collection` noun; **row semantics by source** — CMS catalogs use fail-closed row `enabled` + filter; page-param og slices use field defaults / presence; Hugo `GetTerms` lists stay synthetic (page draft/publish + layouts-node `enabled`). Future balloon-grabs / ah-has expected after more dogfood — flying forward, revisit with perspective.

**Next:** Pass B+ atom hydrate; shortcodes later.

**Files:** page resolve / list / og / socials / process_basic / enqueue, `cms/socials.yaml`, `.agents/notes.md`

### 2026-08-08 — collection filter Pass B

**Shipped:** Rename FAQ universe → `props.collection`. CMS yaml = rows only (attrs moved to layouts). New `fn_collection_filter`: always drop `enabled: false`; optional match (`prop`/`op`/`value`: eq|neq|in|nin); optional `order: random` (build-time); optional `limit`. Wired in `list_details_summary_000` before open/attrs gap-fill → `fn_list_000`. Demo: faq inst `filter.eq` `what_is`; headless `order: random`. Hoist top-level `collection` in `fn_folder_process_basic` (like `items`).

**Parked:** Pass B+ atom hydrate from collection; ~~socials/og `items` → `collection` migrate~~ **done same day**; shortcode/announcement random reuse.

**Next:** Atom hydrate when useful; otherwise dogfood filter / shortcodes later.

**Files:** `fn_collection_filter.html`, `list_details_summary_000/*`, `cms/faq.yaml`, headless FAQ bundle, `layouts.yaml`, `fn_folder_process_basic.html`, `preset_faq.yaml`, `.agents/notes.md`

### 2026-08-07 — FAQ dual-source POC; filter design parked

**Discussed / built:** `tag_details_summary` + `list_details_summary_000` + `section_header_000`; layouts owns section + list wrappers (no-cheating — enabled dual-source stack). `faq_list_sources_000` multiplier: `provider: faq` + `provider: headless` into one `haz_details_list`. Pack in `pre_footer` (sitewide). Sparse CMS; defaults gap-fill `open`/`enabled`. `fn_list_000`: `list_tag` replaces `format`.

**Filter (design only — plan `list_items_filter`):** later became `collection` + `filter` — see 2026-08-08.

**Files:** `tag_details_summary`, `list_details_summary_000`, `section_header_000`, `cms/faq.yaml`, headless FAQ bundle, `layouts.yaml` (pre_footer pack), `fn_list_000`, pico-override FAQ CSS, `.agents/notes.md`

### 2026-08-06 (late) — head_tags close + FAQ plan; shortcodes parked

**Shipped:** Brand SVGs into haz; **#10** `tag_white_list`; **#11** og video/audio list-of-maps; **#6** empty resolved base → skip `<title>` / `og:title` (no prefix/suffix-alone). Share PNG (#1) in tree. **#7** parked as v2.

**Head_tags stance:** Architecture **done** (migrate/mop/peel + contract debt). Leftover = retest, Twitter wire, description story, live debuggers — haz.com can be the docs. Small bugs expected; low redesign risk.

**FAQ plan (`faq_details_chrome`):** Ready aside from CF. Atom `tag_details_summary`; thin `list_details_summary_000` (CMS → `fn_list_000` + `row_partial`); `section_header_000` = generic 3-slot stack (defaults/presets; structure ≠ presentation). Layouts pack only — **no organism**.

**Shortcodes (later):** `shortcodes.yaml` like routes — flat name → layouts path/CMS; one dumb SC. POC + demo after FAQ Atomics exist.

**Next:** FAQ details/summary (2026-08-07).

### 2026-08-05 — brand SVG pass; stopped / regroup tomorrow

**Did:** Wired Affinity exports into `brand_on_load.html` (Hugo Agent Zero wordmark) and `brand_on_scroll.html` (HAZ monogram). Scrubbed Affinity XML/DOCTYPE/`fill`/width-height; restored `haz_svg` classes + chrome CSS fill. Share PNG already landed earlier (#1).

**Feeling:** Wordmark HAZ-emphasis sizing not convincing; day was “not bad but limping.” Chose **stop** rather than keep polishing brand. (Continued 2026-08-06 — see late meeting.)

**Left in tree:** Brand SVGs committed with 2026-08-06 wrap.

**Next:** ~~Fresh start~~ → see 2026-08-06 (late).

### 2026-08-04 — head_tags TODO triage (discussion only)

**Did:** Numbered leftover list **1–14** in Cursor plan `head_tags_todo_triage`. Triaged architecture items:

- **#9 drop** — keep one-line `process.html` (explicit/transparent MO).
- **#10 debt** — `tagList` is SOT blur; defaults should be The Contract; fold emit meta, kill tagList.
- **#11 sooner** — video/audio → list-of-maps now (avoid content debt; no dual map/slice forever).
- **#12 sooner** — brand/CTA already two post-step clones; thin to merge → post → render while in front of us.
- **#13** — strike stale “finish folder migrate” notes TODO.
- **#14 new** — expand `.agents/boilerplate/` (`_atomics.html`, `_page.md`, `_blog_single.md` with `_`-parked props) for agents + docs.
- **#1** PNG 1200×630 (not SVG); **#2** X handle after Cloudflare/mail. Bluesky uses OG we already have.

**Next (~90% HAZ):** re-org 1–14 → execute #10–14 (+ #1 if asset ready) → FAQ/`details`/`summary` + `section_header` chrome.

### 2026-08-03 (late) — head_tags manual peel + static defaults; pause

**Shipped:** Full reverse peel of parked settings `head_tags.meta` (emptied parent removed). Manual atom pass through title/favicon/apple/html/og/twitter/security. Media defaults → `static/defaults/meta_tag_default_{image,audio,video}.*`; `fn_get_meta_value_rules_media` resolve order updated. Favicon + apple-touch PNGs in `static/`. Defaults polish (`og:type: website`, robots `noindex,nofollow`, title delimiter, etc.). **`verification_000`:** folder contract didn’t fit — file Atomic again; layouts `file` = haz empty slot, `_file` = `child/atoms/head_tags/verification.html` (layouts key parks; no double `_` on filename).

**Parked for later triage:** ~~list/prioritize~~ → done 2026-08-04 (triage meeting).

**Next:** ~~list/prioritize head_tags TODOs~~ → see 2026-08-04 meeting.

### 2026-08-03 — head_tags mop (taglist + process_basic); pause for test

**Shipped:** (1) `head_tags_base.html` → `haz/helpers/fn/fn_head_tags_taglist.html`; meta index callers updated. (2) `fn_folder_process_basic.html` — defaults → preset → adapter → overrides → render (`skip_prep`). Thinned 15 head_tags `process.html` + `socials_000` + `cols_two_tag_wrapper_000`. Hugo build smoke OK.

**Left alone:** `brand_logo_dual_000` / `cta_simple_000` process (href / `a_href` post-steps). Optional later: call basic then post — not a second merge recipe yet.

**Locked:** process helpers live under `haz/helpers/fn/` (not parents). Organism process still merges *this node’s* shell props; children merge themselves. Not everything needs folders.

**Next:** ~~user manual test break~~ → done same day (late meeting).

### 2026-08-02 — head_tags migrate complete (A–F); mop tomorrow

**Shipped:** Full head_tags → folder contract blast. B (done prior) + C (`og_global`, `apple_global`, twitter, `og_video`, `html_global`) + D (critical, basic, `og_basic`, security) + E (`og_audio`, `apple_basic` — empty defaults, page FM works; about `og:audio` now emits) + F (`verification_000` haz folder; child `_verification.html` parked). Settings values migrated into defaults + child presets; settings keys `_` parked. Layouts `_preset` + comment scaffold throughout. Deleted legacy file atoms + `.bak`.

**Locked for mop (next session):** shared process util(s); `head_tags_base` → `fn_head_tags_taglist`. No heavy test pass until after mop.

**Then:** beta Atomics — `details`/`summary` + `section_header` / `site_header`.

**User:** notes + commit; knuckle down tomorrow on mop.

### 2026-08-01 — head_tags Bucket B + park section/chrome ideas

**Ideas parked (not built):** `site_header`/`site_footer` naming; `section_header` + `header_content_footer`/`titled_list` with FAQ; blog single subtitle/summary + meta placement.

**head_tags buckets plan:** A = golden shape (`document_title_000`); B = global link lists; C = standard tagList; D = specials; E = empty wired; F = verification child. Start B → graduate to A-shaped folders.

**Bucket B shipped:** `links_performance_000`, `favicon_000`, `links_apple_000` — folder contract, settings parked `_`, layouts `_preset` + comment as intentional docs/scaffold, child content presets ready. Performance: local Atkinson only (F Google CDN). Child merge = replace per rel key, not append. Deleted legacy file atoms.

**DRY lean:** wait until all head_tags folder-migrated; then util helpers per pattern; thin `process.html` callers. Don’t DRY mid-migrate.

**Next:** Bucket C. User committing after notes.

### 2026-07-30 (late) — FA masks, pre_footer, domain, boilerplate, document_title golden

**Socials / icons:** Moved socials from footer `col_other` to **`block_main_post.pre_footer`**. Footer back to brand + tertiary + copyright. **FA Free 7.3.1** vendored; display via **CSS masks** + `data-haz_icon` (no webfonts / no enqueue for icons). Enqueue MVP parked `_`. Native `<details>` a11y = no JS for MVP — FAQ Atomic planned but **parked**.

**Product:** Registered **HugoAgentZero.com** (practical `.com`; shorter names taken/$$$).

**Agent hygiene:** Moved Atomic render shell from `layouts/.../atoms/_boilerplate.html` → [`.agents/boilerplate/_boilerplate.html`](boilerplate/_boilerplate.html); AGENTS.md retargeted. Not exclusive to atoms; not a live layout.

**document_title_000 golden:** Reviewed folder contract — solid. Scrubbed layouts `cms` to `provider: page` only; added `fn_html_comment` to index. Build OK.

**Next session:** head_tags → folders — **easy first**, then discuss `head_tags_base` / page-local packs. Details/summary later.

**User:** updating notes; human will commit.

### 2026-07-30 — brand SVGs + socials CMS molecule

**Brand:** Replaced FPO wordmark/scroll mark with Agent Zero art (chrome `currentColor` / `--haz_chrome`); old art parked as `_brand_on_load_fpo.html` / `_brand_on_scroll_fpo.html`. Kept spelling **Agent Zero** (X energy in the mark, not the name).

**Socials (locked → shipped):**
- Not settings — CMS: `cms/socials.yaml` root `socials:` + `provider: socials`.
- Folder molecule `socials_000` (`defaults` + `process` + `index`); default wrapper **`nav`**; `ul`/`li`; `tag_a_href`.
- Item shape: `enabled`, `type` (`social`|`mail`|`phone`), `name`, `url`, `icon`, optional `target`/`rel`.
- A11y: icon-only + `aria-label`/`title` from `name`; `data-haz_icon`.
- First mount was footer `col_other`; later moved to **pre_footer** (see late entry).
- Hugo pitfall: dynamic close tags must be `printf "</%s>" $tag | safeHTML`.

**User:** notes + commit mid-session (phone break).

### 2026-07-29 — header≈footer organism; presets; routes body kinds; blog meta

**Headline win:** Header and footer are the **same organism** (`cols_two_tag_wrapper_000`) with different **presets** (`preset_header` / `preset_footer`) and fills — preset concept earning its keep.

**Chrome / layouts:**
- Shared folder organism + parent helper; slots `col_brand`, `col_other`, `row_below`.
- Footer: wordmark + `menus.tertiary` (Hugo — for `IsMenuCurrent`) + copyright; `nav_list_000` menu-name aware (`nav_main` / `nav_tertiary`).
- Routes `map_body_attrs`: `haz_single`/`haz_list` + `haz_blog`/`haz_page` on `<body>`; stripped `haz_single_wrapper` / `haz_*_wrapper` from `<article>`.
- AGENTS CSS naming locked (`haz_` / `--haz_*`, optional identity classes, page kind on body ≠ `haz_state__`).
- Atkinson Hyperlegible fonts restored under `static/haz/fonts/` and wired in `pico-x-agent-zero`.

**Blog meta:**
- Inline rows (bold `dt`, no colon, unstyled lists); Pico-ish margin-bottom stack.
- Split into `haz_blog_meta__tax` + `haz_blog_meta__byline` group wrappers with `content_required` so gap only when both render.
- Order: categories → tags → authors → dates.

**Agent / process win:** Standing Atomic shell **`_boilerplate.html`** — assistant can author HAZ-compliant partials and update layouts/routes from plain human wants. Human still points out misses; boilerplate is the shared contract so “stitch it together” gets real. Nav `haz_is_active` visual = bold+underline (clear over clever).

**Parked:** `part.decider` + children packs; layouts folder merge like `cms/`; boilerplate *namespace*; type scale / heading helpers; socials + mega-footer via `details`/`summary`; remaining head_tags → folders.

**Next session:** force brand SVG redo → socials → pre_footer/mega-footer ideas; debt: head_tags folders.

**User:** committing after notes; calling it a day.

### 2026-07-28 — header chrome shippable; Pico pink + data-theme

**Cadence:** debt ↔ new locked; header-first to ~90% before footer.

**Landed:** `--haz_measure` (override settings); dropped Pico `.container` on header rows; sticky header + opaque `--pico-background-color` fill. Theme **Pink** (`pico.pink.min.css`; vanilla kept for swap demo). Light/dark: generalized `script_color_scheme_000` (`mode: class|attr`) → Pico via `data-theme`; html_open SSR `data-theme: dark`; chrome CSS retargeted. Light primary darkened in override for link contrast (`--pico-primary` / `--haz_chrome`). Nav: 1.5rem links, gap 1rem, soft open/close, full-bleed pink separator when open (1.5rem pad/margin on header).

**Parked / later:** Agent Zero brand SVGs (FPO still; path surgery reverted — user will supply art). Footer → socials → FAQ when back. Fluid clamp, FOUC-in-head optional.

**User:** committing; stepping away to other work.

### 2026-07-27 — Pico landed; dogfood chrome next; ship path locked

**Landed:** Switched CSS to Pico — vendor only `pico.min.css`; `pico-x-agent-zero` + child `pico-override`; Simple parked `_framework_css_simple_css`. Restored header chrome after migrate; classless body measure grid (`min(45rem, 90%)`, header full-bleed). Customize via `--pico-*` / CSS-variables docs; CDN color themes & colors sheet for proto only; no utility-class religion. Flat font-size; fluid clamp deferred.

**Evaluate / park:** light-dark (`data-theme` vs `color-scheme-*`); header inner `.container` wider than measure.

**Next chrome:** footer organism; socials (HAZ data, not Hugo menus); CMS FAQ (`details`/`summary`).

**Ship path:** finish Agent Zero on monolith → parent/child module split → search module → ship. Grow Atomics into parent from real usage; don’t catalog everything up front.

**User:** committing separately.

### 2026-07-23 — outsmarted ourselves; organism was already header_000

- **Session arc:** Hardened `document_title_000` page-get (`get_page.yaml`, no `level/group/inst` for page provider), then explored organism-y composition (section header, card, CTA family). Spun on nesting cards→CTAs→args/props/full nodes; head hurt; then realized assembly already exists.
- **Validated answer:** Organism = HTML shell + named child slots; `layouts.yaml` fills slots (same family as multipliers, but structured). Reference: `organisms/headers/header_000`. Molecules stay contract + present; don’t push deep layout graphs into molecule defaults.
- **Also clarified:** Slot ≠ Atomic (announcement bar vs CTA thing); finite CTA layouts later; DOM logical order + flex sibling reorder as MO for header/card-like molecules.
- **Landed stubs (candidates to undo/trim tomorrow):** `section_header_000`, `card_000`, `cta_standard_000` (defaults+index only). Backlog notes: `authors.yaml`→cms?, molecules root hygiene.
- **Tomorrow:** Undo today’s speculative shite as needed; 3x-check `header_000`; if confirmed, great spot — nesting-from-hell isn’t the path.

### 2026-07-22 — head-tags pilot (document_title_000) implemented and validated

**Discussed/implemented:** Executed first migration slice from legacy head-tag file path to folder-contract model for `document_title_000`, while keeping all other head tags on legacy behavior.

**Shipped:**
- `document_title_000` converted to folder component with:
  - `defaults.yaml`
  - `process.html`
  - `index.html`
  - `preset_000.yaml` (parked-key starter template)
- `layouts.yaml` node switched from `part.file` to `part.folder` and wired with `cms.provider: page` + `level/group/inst`.
- Added new helper: `fn_source_page_resolve.html`.
- Extended `fn_source_adapter_resolve.html` to dispatch `provider: page`.

**Bug found + fixed during pilot:**
- Initial `provider: page` implementation still read `sysManifest.settings`, which overrode contract defaults for migrated node.
- Updated resolver so migrated page-provider flow now uses contract/preset/source/page-local/layout layers only (no settings pull for migrated node path).

**Validation:**
- `hugo` build passes.
- Front-end title output confirmed for `demo-post-2` using migrated flow (`document_title_000` defaults/pipeline active).
- Legacy head-tag partials remain unchanged and continue using existing `settings.yaml` behavior.

**Next:**
- Review pilot files together.
- Migrate one additional head-tag unit (likely `meta_html_basic_000`) to validate non-title behavior before broader rollout.

### 2026-07-22 — head-tags parity decision and atomic layering confidence

**Discussed:** Whether head tags should stay file-based settings-only or move into the newer CMS-era contract pattern. We reviewed deltas between current head-tag flow and folder-based Atomic flow, including defaults authority, merge consistency, provider semantics, and agent-first consistency expectations.

**Decided (directional, pre-implementation):**
- Head tags should align to the same architectural standard as folder-based Atomics rather than keep a parallel “legacy” pattern.
- `provider: page` is the correct source semantic for head tags (page/front matter/Hugo context derived values).
- If head tags need special handling (for media/meta edge cases), that logic belongs in `process.html` per component, not in a separate global exception model.
- Organisms are composition templates (primarily molecules + optional helper atoms), not standalone single-shape components.

**Confidence check:**
- Current CMS/folder-based Atomic model is considered conceptually strong and likely scalable.
- Remaining risk is expected edge-case hardening (especially with more complex organism compositions), not foundational architecture.

**Next (after fallback commit):**
- Start a staged head-tags refactor toward folder-based contracts and shared layering rules.
- Keep execution incremental (pilot first), but preserve one standard across component families.

**Execution note (added):**
- Initial migration should convert only 1–2 head-tag nodes while preserving legacy file-based behavior for remaining nodes.
- This allows side-by-side verification and reduces blast radius if merge/provider edge cases appear.

### 2026-07-22 — underscore standardization + provider rename to file_local

**Discussed:** Follow-up cleanup/consistency pass after yesterday’s architecture consolidation. User requested `_` as the explicit parked-key convention, then reviewed each lingering `x`/`X` case one-by-one before applying changes. Also finalized provider naming concern (`data` overload vs Hugo `data/`) and chose `file_local` as clearer canonical provider.

**Decided (locked):**
- `_` prefix is the accepted way to park/disable props/keys in YAML/front matter without deleting them.
- `provider: file_local` is canonical for local manifest-file-backed source data.
- `data` / `src_data` remain temporary compatibility aliases only.

**Implemented/verified:**
- Added `_` convention guidance to [`AGENTS.md`](../AGENTS.md) under edit conventions.
- Added carryover alignment note in current status for `_` semantics.
- Per-item cleanup completed:
  - `xtext_start` → `_text_start` in headless announcement bundle.
  - `XXhome_main_000` → `_home_main_000`.
  - `Xcontent` → `_content`.
  - `Xtaxonomy_000` → `_taxonomy_000`.
  - `Xterm_000` → `_term_000`.
  - Removed dead parked node block `X_brand_logo_primary_a_href_wrapper` from `layouts.yaml` (approved delete).
  - Deleted obsolete backup files `X_sysManifest.yaml` and `X_sysManifest.pre-yaml.bak`.
- Renamed local file-backed provider stack:
  - `layouts.yaml` node uses `cms.provider: file_local`.
  - Added [`cms/file_local.yaml`](../layouts/_partials/child/data/system_manifest/cms/file_local.yaml).
  - Removed `cms/data.yaml`.
  - Updated resolver logic in `fn_source_adapter_resolve` and `fn_source_payload_resolve` to treat `file_local` as canonical with alias fallbacks.
- Repeated `hugo` builds passed after each rename/migration step.

**Next:**
- Plan next implementation slice now that naming/pathing contracts are stable.
- Optional later: prune/refresh older note bullets that still mention pre-`file_local` wording for historical cleanup.

### 2026-07-21 — CMS/provider model finalized, config layering + path contracts hardened

**Discussed:** Long architecture consolidation pass to remove drift and lock naming/structure around folder-based Atomics. User drove consistency goals: keep patterns explicit, keep `defaults` as the contract authority, separate CMS payload storage from reusable configs, and reduce ambiguity in manifest keys.

**Decided (locked):**
- `part.cms.provider` is canonical; legacy `type` remains compatibility fallback only.
- `part.cms.level/group/inst` remain the canonical structural locator shape across providers.
- `process` stays in `layouts.yaml` / Atomic layer (controller/orchestration concern), not in provider data files.
- single-config resolution stays strict:
  1) `part.config` in layouts wins
  2) else provider entry `config`
  3) else none
  (no config merging)
- folder nodes may use short config refs; file nodes require explicit config paths.
- configs are not “cms-only”: child/global reusable presets live under `content/configs/...`; CMS payloads live under `content/cms/...`.
- `data` provider uses consistent entry shape with `props` wrapper (plus optional `config`), matching headless mental model.

**Implemented/verified:**
- Migrated announcement pilot to folder-based molecule flow with process/defaults/config layering fully active.
- Added provider dispatch hardening in resolver stack:
  - canonical provider key support
  - legacy `type` fallback with warnings
  - `src_data` alias compatibility toward canonical `data`.
- Renamed/normalized CMS source namespace:
  - `cms/src_data.yaml` → `cms/data.yaml`
  - resolver lookup supports canonical `data` and legacy fallback.
- Moved/normalized content paths:
  - headless payloads under `content/cms/headless/...`
  - child configs under `content/configs/child/atomic/...`
- Hardened merge-path contract enforcement:
  - added helper [`fn_dict_without_key`](../layouts/_partials/haz/helpers/fn/fn_dict_without_key.html)
  - stripped `merge_paths` from non-contract layers before/after merges
  - adapter payload merges no longer honor external merge path declarations.
- Removed legacy announcement wrapper artifacts and validated current pathing/render flow.
- Repeated `hugo` builds passed during each migration/hardening step.

**Deferred / next:**
- Add 2-3 more folder-based Atomic pilots before extracting a shared generic process orchestrator.
- Optional notes cleanup pass for older historical references (`src_data` / pre-provider wording) once the migration dust settles.

### 2026-06-26 — dispatcher + preps realignment (baseline set)

**Discussed:** Re-grounded architecture around one consistent node shape and clear ownership boundaries. Confirmed helpers/preps are dedicated infrastructure (not optional feature fallback handlers), and that `fn_partial` should stay a semi-dumb dispatcher with a small prep redirect branch.

**Implemented/verified:**
- Reshaped announcement node in [`layouts.yaml`](../layouts/_partials/child/data/system_manifest/layouts.yaml):
  - `part.file` points to pure presentation atom
  - orchestration key moved to `part.prep` (final naming; `adapter` retired)
  - data contract moved to top-level sibling `source`
  - `props` remains presentation overrides
- Refactored [`fn_partial.html`](../layouts/_partials/haz/helpers/fn/fn_partial.html):
  - dispatches to `part.prep` (with legacy `part.adapter` alias support)
  - supports prep re-entry render path via `skip_prep` + `resolved_props`
  - retains direct render behavior for non-prep nodes
- Converted announcement orchestration to dedicated prep:
  - new [`helpers/preps/atomic/atoms/announcement_000.html`](../layouts/_partials/haz/helpers/preps/atomic/atoms/announcement_000.html)
  - removed `enabled_false` behavior from prep (helpers are not optional fallback surfaces)
  - prep resolves source + merges props + re-enters `fn_partial` for final render
- Housekeeping:
  - removed old [`helpers/adapters/atomic/atoms/announcement_000.html`](../layouts/_partials/haz/helpers/adapters/atomic/atoms/announcement_000.html)
  - no remaining `helpers/adapters` / `adapter:` references in repo search
  - `hugo` build clean after each major step

**Decided/clarified:**
- Framing shifted from “exception” to “enhanced part path”: standard `part.file`, optionally enhanced by `part.prep` + optional `source`.
- Source backends (`map_headless`, `src_data`) are datastore concerns; prep/controller owns source resolution and merge orchestration.
- Keep Atomic FE purity: atoms present; preps/helpers orchestrate.

**Next:** Implement universal prep boilerplate (shared source getter dispatch + shared render handoff + shared merge reuse) so one prep contract can handle multiple source types (`headless`, `src_data`) with minimal duplication.

### 2026-06-26 — headless source live, naming/structure recalibration

**Discussed:** Validated the new headless-backed announcement path and then stepped back to review architecture boundaries. User emphasized Atomic should remain FE-focused, with non-presentation logic in a separate layer. Discussed naming options (`adapter`, `preprocessor`) and settled on **`preps`** as the most audience-friendly, low-baggage term.

**Implemented/verified:**
- Wired announcement to headless source path:
  - new atom [`announcement_000.html`](../layouts/_partials/haz/atomic/atoms/announcement_000.html)
  - new helpers: `fn_source_headless_entry_resolve`, `fn_source_headless_bundle_resolve`, `fn_source_props_merge`
  - manifest repointed to `level: map_headless`
  - `map_headless` shape includes `src` + optional `props`
  - bundle defaults in `content/headless/.../announcement_000/index.md`
- Verified parity and build (`hugo --gc` clean; rendered announcement output preserved with instance override behavior).

**Decided/clarified:**
- Keep `src_data` in architecture for now as an alternate source backend.
- Treat headless and src_data as different source backends behind one contract.
- Keep DRY render parent pattern, but re-org is needed so FE atoms stay FE and orchestration lives in its own layer.
- Add lightweight compatibility/invariant checks later (renderer <-> bundle/map expectations), not immediately.

**Next:** User will revisit re-org after Cursor update; then walk through folder/name cleanup once more and execute.

### 2026-06-25 — headless bundle pivot exploration + scaffolding

**Discussed:** Whether `src_data.yaml` should remain the primary source store versus using headless bundles as CMS-like “rows” with colocated defaults/resources. Confirmed this looks like a major DX/AIX win: stronger decoupling, less template cloning, cleaner reuse/share model (“drop atom + bundle folder”), and better long-term shortcode/map indirection patterns.

**Decided:**
- Keep `src_data` in place for now; do not migrate rendering logic yet.
- Add bookkeeping scaffolding first (`map_headless`, headless content tree, first bundle contract) and review before wiring resolver changes.
- Bundle front matter uses `params.props` (not `default_props`) and explicit `merge_paths` list-of-paths shape.

**Implemented/verified:**
- Added [`map_headless.yaml`](../layouts/_partials/child/data/system_manifest/map_headless.yaml) and merged it in [`fn_get_sys_manifest`](../layouts/_partials/haz/helpers/fn/fn_get_sys_manifest.html).
- Added [`content/headless/_index.md`](../content/headless/_index.md) with cascade build options for headless behavior (`render: never`, `publishResources: false`, `list: local`).
- Added first bundle [`content/headless/atomic/atoms/announcements/announcement_000/index.md`](../content/headless/atomic/atoms/announcements/announcement_000/index.md) with `params.props` + `params.merge_paths`.
- Confirmed `hugo --gc` clean with render path unchanged.

**Next:** Sleep/review, then decide whether to wire resolver lookup from `map_headless.src` + bundle front matter into the active announcement pipeline.

### 2026-06-24 — announcement wrapper-parent + generic resolver pass

**Discussed:** Tightening the announcement POC toward a reusable pattern while keeping DX high and naming aligned (`src_data`, `props.source`, props-first language). Confirmed MVC is a heuristic, not a strict framework contract.

**Decided:**
- Defaults should live in the wrapper/controller (`defaultProps`) and be merged with `src_data` then instance overrides.
- Keep fake deep merge explicit via merge-path arrays; pair `mergePaths` near defaults for readability.
- Use props terminology consistently (`default_props`, `source_props`, `resolvedProps`) instead of payload wording.

**Implemented/verified:**
- Added `fn_source_payload_resolve` (generic precedence resolver) and `fn_merge_fake_deep` (explicit nested path merge helper).
- Moved announcement render markup into `helpers/parents/atoms/announcement_parent.html`.
- Refactored `announcement_000_src_data.html` into wrapper/controller role; source contract now `props.source.*` only.
- Removed POC-specific resolver `fn_announcement_payload_resolve.html`; `hugo --gc` clean; output parity spot-check passed.
- Readability cleanup: multiline defaults dict + local `mergePaths` declared beside defaults.

**Next:** User will review/commit; then continue deconstruct/reconstruct on announcement and consider extending the generic resolver to a second component for validation.

### 2026-06-22 — quick refactor pass (props shape + component prefix)

**Discussed:** User confirmed preference to keep component identity explicit and asked to proceed while they stepped away briefly.

**Decided:**
- Lock usage override shape to `props.component.props`.
- Use filename prefixes for component type clarity (starting with `component_data_*`) instead of creating multiple type folders now.

**Implemented/verified:**
- `layouts.yaml` updated from `component_overrides` to `component.props`.
- `announcement_000.html` renamed/wired to `component_data_announcement_000.html`.
- Resolver updated to read overrides from `props.component.props`.
- Build and lint checks passed.

**Next:** continue POC stabilization, then extract generic resolver once a second component adopts the pattern.

### 2026-06-22 — fake merge pilot + naming/folder notes

**Discussed:** Ran a KISS POC for fake deep merge using `announcement_000` as the text pilot. User flagged two important follow-ups: override key shape should align with component mental model, and component file naming/folder conventions may need a clearer split for data/content-oriented variants.

**Decided:**
- Keep current resolver narrow (`fn_announcement_payload_resolve`) for POC speed.
- Keep `/content/` out of scope for now.
- Prefer future override shape as `props.component.props` (instead of `props.component_overrides`).

**Implemented/verified:**
- POC helper wired and build checks passed.
- Nested usage override proof confirmed (usage `a.text_anchor` overriding component payload while preserving other `a.*` fields).

**Deferred:** abstract generic resolver, move override key to `props.component.props`, and settle naming/folder convention (`data_` / `content_` prefix and/or `atoms/components/` pattern).

**Next:** resume with cleanup refactor from POC-specific helper to reusable component payload resolver once back from billable work.

### 2026-06-22 — layouts namespace normalization

**Discussed:** `layouts.yaml` was the odd file out after manifest split because its domains were not wrapped under one parent key, creating potential root-key collision risk during sysManifest merge.

**Decided:**
- Standardize on `layouts_root` as the inner key for the root entry map.
- Normalize shape to `sysManifest.layouts.{layouts_root,atoms,molecules,organisms,multipliers}`.
- Keep this strict as the canonical schema.

**Implemented/verified:**
- Updated `layouts.yaml` on disk to wrapped shape.
- Updated runtime lookups (`baseof`, root stubs, partial resolvers, manifest loader).
- Ran build + diff checks; everything rendered as expected.

**Next:** return to component override design and selective “fake deep merge” by declared key paths.

### 2026-06-19 — data components POC (announcement) + override direction

**Discussed:** Component-source naming and architecture framing. Locked vocabulary to **data components**, **content components**, **hybrid components**. Clarified that rendering remains Atomic; source/model layer is what changes. Evaluated merge constraints in Hugo (`merge` not deep) and discussed options for overrides.

**Decided:**
- Run a no-override POC on `announcement_000` first (component-only source) to prove flow.
- Keep resolver atom-local for POC speed/safety; avoid lifting to shared helper until a second component adopts the pattern.
- Keep future override design explicit/non-recursive by default (no automatic deep merge magic).

**Implemented/verified:**
- Added `components.yaml` and merged into `fn_get_sys_manifest`.
- Moved announcement payload out of `layouts.yaml` node props to `components.announcements.announcement_bar_000`.
- Added pointer contract in `layouts.yaml`: `props.component.level/group/inst`.
- Updated `announcement_000.html` to resolve component data from pointer (lookup only when enabled).
- `hugo --gc` clean; rendered announcement output parity confirmed (`startA`, link text, `endZ`).

**Deferred:** shared `fn_get_component_data`; formal override policy and merge modes (`replace` baseline, selective/manual merge if needed).

**Files:** `layouts/_partials/child/data/system_manifest/components.yaml`, `layouts/_partials/haz/helpers/fn/fn_get_sys_manifest.html`, `layouts/_partials/child/data/system_manifest/layouts.yaml`, `layouts/_partials/haz/atomic/atoms/announcement_000.html`, `.agents/notes.md`

**Next:** convert a second component using same pointer contract, then extract common resolver fn.

---

### 2026-06-18 — routes-first hardening, branch schema finalized

**Discussed:** Whether `layouts|all` should still own route fallback semantics after moving to `all.html` as the single Hugo bottleneck. Confirmed desire for explicit naming and low ambiguity, then iterated route schema naming from flat `*_enabled_true/*_enabled_false` keys to branch objects for readability and lower repetition.

**Decided:**
- Treat `all.html` as infrastructure adapter (entrypoint), not a manifest node; route policy belongs in `routes.yaml`.
- Keep `map_layouts_entry.enabled` as hard on/off for route targets.
- Use branch objects in `map_child` and `defaults`: `enabled_true` / `enabled_false` with `key_layouts_entry` and `key_html_attrs`.
- Keep trail in notes using strike-through for superseded items rather than deleting.

**Verified:** `hugo --gc` clean after decoupling `all.html` from `layouts|all` and after routes schema refactor; repo reached clean state and user committed.

**Deferred:** `home` cleanup + sub-partials/sub-components pass; docs sync for final routes schema and updated mental model text.

**Files:** `layouts/all.html`, `layouts/_partials/haz/helpers/parents/default_router_parent.html`, `layouts/_partials/haz/helpers/fn/fn_router_processor.html`, `layouts/_partials/haz/helpers/fn/fn_router_processor_html_attrs.html`, `layouts/_partials/child/data/system_manifest/routes.yaml`, `layouts/_partials/child/data/system_manifest/layouts.yaml`, `.agents/notes.md`

**Next:** Resume with narrow scope: home cleanup first, then sub-components pass.

---

### 2026-06-17 — all.html source split, cleanup, route-entry direction

**Discussed:** Consolidation after `all.html` proof. Clarified that with `all.html` default, manifest source should be fixed (`layouts|all`) and not derived from `route_type`. `route_type` remains policy-only (routes defaults + html attrs). Reviewed cleanup and naming consistency (`templates` → `multipliers`) and debated multiplier placement; preference moved back to explicit top-level `multipliers` plus readable `_multiplier` naming. Explored next-step architecture: routes as “start child” selector (`children`-like but singular), with potential explicit entry object key (`layout_entry` / `layouts_entry`).

**Decided:**
- Keep `all.html` as main entry path; retain optional per-kind stubs only as escape hatches.
- Keep cleanup incremental; leave `x_*` roots until confidence is high.
- Keep backlog note for `default_allow_false` semantics and remove unused `allow_default_true` only after explicit review.
- Track route-entry schema option; no implementation decision yet.

**Verified:** Build passes after `layouts.yaml` rename from `templates` to `multipliers` and `level: templates` to `level: multipliers`.

**Deferred:** Final route-entry schema (`layouts_entry` naming + shape), identity classes/data attrs strategy, home wrapper parity, components layer (`components.yaml` + optional headless sources), docs updates.

**Files:** `layouts/all.html`, `layouts/_partials/child/data/system_manifest/layouts.yaml`, `layouts/_partials/child/data/system_manifest/routes.yaml`, `.agents/notes.md`

**Next:** Continue cleanup pass; commit; revisit route-entry schema tomorrow.

---

### 2026-06-16 — all.html single entrypoint validated

**Discussed:** Move from many Hugo root wrappers (`single`, `section`, `taxonomy`, `term`, `home`) to one `all.html` while preserving routes/sysManifest as the policy layer. Confirmed `fn_get_route_type` should mirror Hugo signals (`.Layout` first, then `.Kind`) and that custom FM layouts remain dev-discretionary and require matching routes keys. Added optional WP-style child hook pattern for route type overrides, matching existing manifest filter approach.

**Decided:**
- Add `layouts/all.html` using `default_router_parent` and dynamic `thisSource = layouts|{route}` from `fn_get_route_type`.
- Keep `home.html` and other root stubs as `x_*` during short soak testing (no hard delete yet).
- Add optional child hook `fn_filter_get_route_type.html` with graceful no-op default.

**Verified:** `ALL` marker in `all.html` appears across pages, including home when `home.html` is prefixed; `hugo --gc` clean.

**Deferred:** Remove `x_*` stubs after final confidence pass; decide whether to keep/merge `layouts|home` manifest branch; follow-on docs for routes + custom layout caveat.

**Files:** `layouts/all.html`, `layouts/_partials/haz/helpers/fn/fn_get_route_type.html`, `layouts/_partials/child/utils/fn_filter_get_route_type.html`, root `layouts/x_*.html` (temporary test state), `.agents/notes.md`

**Next:** Final smoke pass, remove marker/debug artifacts, then commit.

---

### 2026-05-31 — routes html attrs wired end-to-end

**Discussed:** Stepwise routes work — extract shared resolution, refactor child router, then html attrs stack. **`parents/`** = abstracted base (`route_resolve_parent`); not layout entry points only. **`settings.html_attrs_key`** required (not optional). **`fn_get_route_type`** centralizes Hugo `.Kind` → routes defaults key (`page` → `single`) for shared `baseof` shell vs layout-specific `$route` stubs. Dynamic html attrs: rule → `map_child` (enabled) → `defaults`; map miss falls through; **`class`** concat on merge. User first Hugo project — architecture/user-driven; AI implementation. **`home.html`** deferred — html attrs for home work via rule `""`; main content still hardcodes `home_main`.

**Decided:**
- Ship html attrs processors + wire `tag_html_open`; remove duplicate attrs from manifest.
- Keep TODO1/2/3 as proof keys until real body/layout classes.
- `home.html` revisit later (may not need stub); no change this session.

**Verified:** `hugo --gc` clean; spot-check `/`, `/blog/`, `/about/`, `/about/team/`, taxonomy/term pages — base + dynamic classes on `<html>`.

**Deferred:** Real `map_html_attrs` keys; DRY `$route` in layout stubs; **`fn_get_route_type`** vs **`layout: single`** on section indexes (about); `home.html` through router; body classes; footer; AZ CSS.

**Files:** `routes.yaml`, `route_resolve_parent.html`, `fn_router_processor.html`, `fn_get_route_type.html`, `fn_get_routes_html_attrs_default.html`, `fn_router_processor_html_attrs.html`, `fn_merge_attrs_dict.html`, `fn_html_attrs.html`, `tag_html_open.html`, `layouts.yaml`

**Next:** User commit; then body classes / footer / CSS — or routes polish + `home.html` decision.

---

### 2026-05-28 — routes clarity, content/meta model, CSS direction

**Discussed:** Router confusion — debug third field is **`.Section`** (content folder), not map key or `single`/`section`. `"page"` came from **`content/page/`** test bucket (+ `url:` hide segment); rename to **`content/pages/`**. Routes POC verified working. Q&A: taxonomy term meta via **`content/{taxonomy}/{term}/_index.md`** (author head_tags works); any Hugo `.Page` URL enrichable from content; paginated lists → canonical parent. Body classes (WP-style) next — move blog/page styling context from `<article>` to `<body>`. Missing chrome: **footer** (slot wired, `inst: todo`), CSS polish. Search: static (Pagefind/Lunr), **after** parent/child module split; header search slot placeholder.

**Decided:**
- Mental model: `/content/` = pages; taxonomies = Hugo wrapper + optional content overlay.
- Next session: body classes → footer → `simple-x-agent-zero.css`; strip redundant article wrapper classes when body classes land.
- Search deferred until module split; Pagefind vs Lunr spike later.

**Deferred:** Footer atom; body class fn; AZ CSS file; `content/pages/` rename + `map.pages`; blog index; module split; search.

**Files:** `.agents/notes.md` (notes only — user committing session work separately)

**Next:** Body classes + footer + CSS layer.

---

### 2026-05-30 — haz reorg complete; routes reg pages next

**Discussed:** Folder reorg execution — `haz/atomic/` + `haz/helpers/` (`fn/`, `fn/page/`, `multipliers/`, `parents/`); `helpers/` over `ops`/`engine`; atomic tiers 4–5 as README stubs under `atomic/templates/` + `atomic/pages/`. Copy-first, then manifest flip. User prefixed legacy trees `xxx_*`, verified build, deleted in follow-up commit.

**Decided:**
- Live paths: `haz/*` in `layouts.yaml`, `settings.yaml`, layout stubs, all `partial` calls inside `haz/`.
- Reorg complete; not blocking on AGENTS.md update yet.

**Issues (not reorg):** `/about/`, test/page paths missing — [`routes.yaml`](../layouts/_partials/child/data/system_manifest/routes.yaml) WIP: `about/*` → `about_000` but no enabled `map.about_000` (only `Xabout_000`). Routes POC never fully executed; resume tomorrow.

**Deferred:** Routes + regular pages; blog index; CSS; AGENTS.md haz map; purge `X_sysManifest.yaml` backups.

**Files:** `layouts/_partials/haz/**`, `layouts.yaml`, `settings.yaml`, `layouts/*.html`, `routes.yaml`, `.agents/notes.md`

**Next:** Fix routes `map` for about + generic pages; blog listing.

---

### 2026-05-29 — blog meta wired, haz reorg shape, meta CSS

**Discussed:** Roll individual dt/dd atoms into prod blog meta. CSS: icon swap via `nth-child` on `dl > div` — yes for base model; row classes later when rows conditionally omit (lastmod, empty taxonomies). **`haz/`** as core vs **`child/`** as site layer (child = own repo, must live under `_partials`). Atomic belongs under haz (presentation + utilities). Target tree: `haz/atomic/`, `haz/utils/fn/` (+ `page/`), `haz/multipliers/` (not `templates/`), `haz/parents/`. `fn_s` = function plural; prefer **`utils/fn/`** in folder names.

**Decided:**
- Ship prod meta: div wrapper → [`tag_dl_list_wrapper_000`](../layouts/_partials/atoms/tag_dl_list_wrapper_000.html) → multiplier rows (`meta_authors`, dates, categories, tags).
- Unique wrapper insts per path (single vs index); index meta placeholder for now.
- **`multipliers/`** folder name over `containers/` or cryptic `fn_s`.
- Two-root partials model: **`haz/`** + **`child/`**; document in AGENTS when migrating.

**Deferred:** Blog listing page; routes work; `haz/` file migration; `simple-x-agent-zero.css`; meta row classes / dl aria; layouts.yaml inventory.

**Files:** `tag_dl_list_wrapper_000.html`, `layouts.yaml`, `.agents/notes.md`

**Next:** Blog index + routes; then `haz/` migration when ready.

---

### 2026-05-29 — meta wrapper plan, CSS layers, multi-author

**Discussed:** Wiring prod blog meta — three dt/dd atoms (date, taxonomy, author); shell = `tag_tag_wrapper` (div) + new **dl wrapper** (optional `aria-label`, minimal props) + multiplier rows. Inline dt/dd styling → parent CSS not child. [Simple.css](https://simplecss.org) stays default; **don’t fork**; add **`simple-x-agent-zero.css`** as AZ-universal layer between vendor min + child override. Taxonomy + `content/{taxonomy}/{term}/` merge for per-term copy/head tags. Routes/sysManifest as DX normalization over Hugo quirks.

**Decided:**
- Keep Simple.min vendored; AZ overrides in `simple-x-agent-zero.css` (rename/migrate from `simple-extended.css` when implemented).
- Blog meta: no second full `tag_tag_wrapper` for dl — dedicated dl partial.
- `dl_aria_label` optional but recommended (settings + props override).
- Multi-author list verified; yaml name lookup via term `.Name`.
- `x_blog_meta_wrapper` static HTML = reference only; `/authors/jane-doe/` in mock was not atom output.

**Deferred:** Implement dl wrapper + prod meta multiplier; `simple-x-agent-zero.css` file + manifest; inline `.blog_meta__list` rules; author term custom layout; DRY author/taxonomy fns.

**Files:** `hugo_page_author_dt_dd_000.html`, `fn_page_author_terms.html`, `layouts.yaml`, demo posts, `x_blog_meta_wrapper_000.html`, `.agents/notes.md`

**Next:** Commit; billable break; then meta wrapper + CSS layer when back.

---

### 2026-05-29 — author POC, taxonomy + content merge

**Discussed:** Author design — `author_id` in FM + `authors.yaml` in sysManifest; taxonomy for filtering posts; stable term id (`author_0001`) vs display name in yaml. Taxonomy vs `content/authors/` — same URL, Hugo merges term + bundle (title, `.Content`, `params` e.g. head tags). Categories/tags can use same `content/{taxonomy}/{term}/_index.md` pattern. Why not reuse `fn_page_taxonomy_terms` alone — need id→name map from yaml (`.Name` not `.LinkTitle`). Keep two fns for now; DRY later (backlog).

**Decided:**
- POC: `authors.yaml` merge, `fn_page_author_resolve`, `fn_page_author_terms`, `hugo_page_author_dt_dd_000` (meta links), then `hugo_page_author_bio` in test inst.
- `author: authors` in `hugo.yaml`; `settings.taxonomies.authors` (not separate `settings.authors.meta`).
- Multi-author list on demo-post-2; fix display names with `.Name` for yaml lookup.
- Test `content/authors/author_0001/_index.md` — confirmed merged term page.

**Deferred:** Multi-author bio; wire `x_blog_meta_wrapper_000`; author term layout with yaml names; DRY author/taxonomy term fns.

**Files:** `authors.yaml`, `fn_page_author_resolve.html`, `fn_page_author_terms.html`, `hugo_page_author_dt_dd_000.html`, `hugo_page_author_bio.html`, `hugo.yaml`, `settings.yaml`, `layouts.yaml`, demo posts, `content/authors/author_0001/_index.md`

**Next:** Commit; then meta wrapper multiplier or author term layout.

---

### 2026-05-28 — date atom cleanup, lastmod compare

**Discussed:** Date atom had sprawled (~35 lines lastmod guards); raw `$context.Date` / `PublishDate` vs `fn_get` pattern drift. Hugo date cascade — `.Lastmod` / `.PublishDate` return synthesized values, not empty; only `isset Params` tells explicit FM. Whether compare baseline should be configurable (not hardcoded publishdate-with-date-fallback). Fixed time unit vs `*_unit` compensation — **seconds** (Unix/WP-style).

**Decided:**
- Extract `fn_page_date_resolve` (method + profile via `settings.dates.default` → hardcoded `publishdate` fallback; typo in `props.method` uses resolved key for fn_get too).
- Extract `fn_page_date_lastmod_show` + `fn_page_date_compare` (`a`, `b`, `min_after_seconds`: `<0` valid-only, `0` strictly after, `>0` min gap).
- Lastmod settings: `require_explicit`, `must_be_after: publishdate` (fn_get key), `must_be_after_seconds: 0`. One baseline at a time — “Updated” hidden if lastmod before baseline (e.g. published today, mod yesterday).
- Atom = resolve → get → show? → render; same convention as taxonomy/list fns.

**Deferred:** Wire `x_blog_meta_wrapper_000`; optional `must_be_after_require_explicit` on baseline; prop-merge DRY helper; `fn_get` rename.

**Files:** `hugo_page_date_dt_dd_000.html`, `fn_page_date_resolve.html`, `fn_page_date_lastmod_show.html`, `fn_page_date_compare.html`, `settings.yaml`

**Next:** Wire blog meta wrapper (publishdate + lastmod + categories + tags).

---

### 2026-05-28 — blog meta taxonomies, list-fn design

**Discussed:** Taxonomy atom mirroring date `<dl>` pattern. **`props.taxonomy`** (singular keys per Hugo `hugo.yaml` model); **`settings.taxonomy_names`** maps to plural for `.GetTerms`; display labels in `term`. `fn_page_taxonomy_terms`: `format: list|inline`, delimiter as design separator inside `<ul><li>` (a11y list + readable commas). DRY single loop via `$tagOpen`/`$tagClose`. Abstract generic **`fn_list_*`** + **`fn_list_row_*`** row partials (delegate row markup per partial; e.g. `rel="tag"` only in tag row) vs `printf` injection — **KISS, row partial wins**. Nav / `default_000` as future consumers.

**Decided:**
- Ship taxonomy atom + fn as-is for now; extract list fn when implementing next session.
- Hugo naming convention documented in AGENTS.md + notes.
- Date atom cleanup/hardening + list refactor = **first priority tomorrow**.

**Deferred:** Wire `x_blog_meta_wrapper_000`; generic `fn_list_*` + row partials; refactor `default_000` / `hugo_pages_list_item_000`; author meta.

**Files:** `hugo_page_taxonomy_dt_dd_000.html`, `fn_page_taxonomy_terms.html`, `settings.yaml`, `layouts.yaml` (user test wiring), `AGENTS.md`, `.agents/notes.md`

**Next:** Generic list fn + row partials; `hugo_page_date_dt_dd_000` cleanup; then wire blog meta wrapper.

---

### 2026-05-27 — sysManifest direction, home_main, multipliers, routes

**Discussed:** Lost chat / Cursor mitigations. **Stick with sysManifest** for POC — LLM-first, optimize later (refs, blueprints, rename `templates/` → containers/multipliers). Multiplier parent pattern (`parents/multiplier_parent` + `templates/multiplier_*`). **home.html** should use manifest multiplier not five inline `fn_partial`s → `home_main_000`. **single/section** use `default_router_parent` + `routes.yaml`; whether `default_allow_false` is needed (rare: deny `routes.defaults` but still show a stub layout). **page.*** vs **blog.*** (meta = blog-only). Blog meta HTML: **`<dl>`** with visible `<dt>`; skip wrapping title+meta in `<header>`; AT understands dl/dt/dd without extra aria unless grouping label wanted. Informal **layouts.yaml** outline scan (not saved to file). YAML folding: `editor.showFoldingControls: always`.

**Decided:**
- KISS on sysManifest; defer optimization pass.
- `home_main_000` + `templates/home_main_000` multiplier pattern for home.
- Universal page nodes; blog meta separate; `<dl>` for author / dates / categories / tags.
- Keep `default_allow_false` in manifest for now (disabled); router parent still references it — user reverted partial yaml/router edits during session; confirm cleanup later.
- Git init + first commit baseline before further layout work.

**Deferred:** Wire/test routes on all kinds; implement blog meta atoms; save layouts inventory doc; router debug line removal; optional rename `home` child key to `home_main_000`.

**Files:** `home.html`, `layouts.yaml`, `parents/multiplier_parent.html`, `templates/multiplier*.html`, `.gitignore`, `.gitattributes`, `.agents/notes.md`

**Next:** Resume single/section + routes; blog meta `<dl>` atom(s); layouts.yaml inventory if wanted.

---

### 2026-05-26 — `.agents/notes.md` session carryover (this chat)

**Discussed:** Cursor updates / new threads losing chat context. Mitigations: export chats, backup `%AppData%\Roaming\Cursor\`, repo-backed notes. Rejected separate `MEETING_NOTES.md` — one file with **Current status** (top) and **Meetings** (bottom, newest first).

**Decided:**
- **Start of session:** Agent reads `.agents/notes.md` (Current status + latest Meeting if needed); one-line focus ack, no dump.
- **End of session:** Explicit “wrap up” → update notes. Implicit goodbye (“good night”, “done for today”) → ask *Do you want me to update `.agents/notes.md`?* — only write if yes.
- **Stale notes on new session:** If Meetings looks behind recent work → ask *I sense we're about to start a new session, but we never updated `.agents/notes.md` from the last session — would you like me to do the last session now?*
- Documented in `AGENTS.md` + `.cursor/rules/session-carryover.mdc`.

**Deferred:** Routes resolver work (carried from prior thread; see meeting below).

**Files:** `.agents/notes.md`, `AGENTS.md`, `.cursor/rules/session-carryover.mdc`

**Next:** User on other work; resume routes / `fn_get_section_route_child` when back.

---

### 2026-05-26 — routes, whitelist (prior thread, backfilled)

**Discussed:** Whitelist maps path → type key; no match → use `$Section` (not full URL path); returns key for `type.*`. Blog single path issue; `/about/` vs `/about/team/`; `layout: single` on section-like pages.

**Decided:** Routes as optional bottleneck for custom layout children; path-level overrides for about/services-style pages.

**Deferred:** Wire resolver into `single.html` / `section.html`. About + `layout: single` vs child pages. Layout explicit vs default without new front matter params.

**Next:** Implement resolver aligned with `routes.yaml` `rules` / `map` / `defaults`.
