---
name: HAZ.com content stubs
session: 2026-09-24
status: in_progress
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21
related:
  - haz-com-content #2
  - haz-com-child #2
---

# HAZ.com starter pages (Lorem, start over)

HQ [#21](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21). Status: **in_progress** (PRs open; dispatch after merge).

Strip HAZ.com down to Home, About, Getting Started, Blog, and Contact with Lorem stubs. Menus and FAQ yaml door live in `haz-com-child`; pages and the one How To post live in `haz-com-content`. Kit templates stay untouched.

## Where things live

- **Pages + blog** — `project-website/haz-com-content/content/`
- **Nav** — `project-website/haz-com-child/hugo.yaml` `menus.main` and `menus.tertiary`
- **FAQ (yaml door)** — `haz-com-child` `layouts/_partials/child/data/system_manifest/cms/faq.yaml`
- **FAQ (headless door)** — `haz-com-content` `content/cms/headless/atomic/molecules/details/list_details_summary_000/index.md`

`content/pages/` is organization-only and must not publish `/pages/`. New pages are top-level sections, same as About.

## Content

- Home / About — keep titles; Lorem body. Drop Team, Page Test, demo shortcodes.
- Getting Started + Contact — new `_index.md` each, `layout: single`.
- Blog — delete demo posts; add **Shortcode: haz_img Explained** (`categories: [How To]`), Lorem only.

## Nav

Main and tertiary, same set, weights 10–50: Home, About, Getting Started, Blog, Contact.

## Ship

- [haz-com-content #2](https://github.com/hugoagentzero-com/haz-com-content/pull/2)
- [haz-com-child #2](https://github.com/hugoagentzero-com/haz-com-child/pull/2)

Merge, then dispatch **build-pages**. Apex `https://hugoagentzero.com/`.
