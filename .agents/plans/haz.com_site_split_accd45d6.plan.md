---
name: HAZ.com site split
session: 2026-09-23
status: in_progress
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/63
related:
  - staging-content https://github.com/hugo-agent-zero/hugo-agent-zero-env-staging-content/pull/21
  - child import https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/68
  - HQ README https://github.com/hugo-agent-zero/hugo-agent-zero/pull/64
  - HQ README org links https://github.com/hugo-agent-zero/hugo-agent-zero/pull/65
  - haz-com-content pages https://github.com/hugoagentzero-com/haz-com-content/pull/1
  - haz-com-child import https://github.com/hugoagentzero-com/haz-com-child/pull/1
overview: "Split kit (modules + staging content) from HAZ.com (website org). Copy child + child-content templates on GitHub into the website org, then clone those into local project-website/. Rename hugoagentzero_com-content to a staging/env repo — HAZ.com uses the kit at pins; staging proves modules before other sites bump."
todos:
  - id: update-agent-map
    content: "Public HQ README: kit-org repo list + why HAZ.com lives in another org. Agent-only local map in AGENTS.md / notes (no local paths in README)."
    status: completed
  - id: rename-staging-content
    content: "Rename hugoagentzero_com-content → hugo-agent-zero-env-staging-content (kit org + local folder + go.mod + child import + Pages baseURL)."
    status: completed
  - id: website-org-from-templates
    content: "Create HAZ-website org; Use-this-template (or equivalent) for child + child-content from kit org; clone into project-website/."
    status: completed
  - id: stub-haz-img-howto
    content: "Add first How To stub (haz_img / #13) in HAZ.com content; Home/About may stay TODO."
    status: pending
  - id: optional-custom-domain
    content: Point HugoAgentZero.com at the website-org Pages (apex baseURL). Do not point it at kit staging.
    status: pending
isProject: false
---

# HAZ.com vs kit staging

## Two jobs (do not collapse)

**HAZ.com uses the project.** That is required. The product site is a first-party *consumer*: it copies child + child-content, imports **core**, and lives in a **website org**. Same motion as any third party. If the public site never runs on HAZ modules, we are not dogfooding.

That does **not** mean HAZ.com replaces the kit live preview.

- **HAZ.com** pins released / agreed core (same as other sites). Real How Tos. Apex `https://hugoagentzero.com/`. Home/About can stay TODO.
- **Kit staging content** is the crash dummy for new module ideas *before* HAZ.com and third parties bump pins. Local `hugo server` is already “dev.” This remote repo is **staging**.

If we dump unreleased `haz_img` / graph experiments straight onto HAZ.com, we have no site that looks like a consumer and no place to break things on purpose. Keep both until staging is unused in practice; then delete it.

[#21](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21) writing shape unchanged: blog as FAQ / How To. [#13](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/13) stays the kit ticket; the How To lives on HAZ.com.

## Rename (kit org)

`hugoagentzero_com-content` names the product site. It is not that.

Working slug: **`hugo-agent-zero-env-staging-content`**

- `env-dev` is the weaker name: anything local is already dev.
- `staging` matches the job: prove modules before other sites consume them.

GitHub rename + local folder rename. GitHub redirects the old repo URL; **Pages URL and Go module path do not**. Must update together:

- [`project-modules/hugoagentzero_com-content/go.mod`](project-modules/hugoagentzero_com-content/go.mod) `module` path
- [`project-modules/hugo-agent-zero-child/hugo.yaml`](project-modules/hugo-agent-zero-child/hugo.yaml) + [`go.mod`](project-modules/hugo-agent-zero-child/go.mod) import
- [`.github/workflows/pages.yml`](project-modules/hugoagentzero_com-content/.github/workflows/pages.yml) `hugo mod get` + `--baseURL` (will become `https://hugo-agent-zero.github.io/hugo-agent-zero-env-staging-content/`)
- HQ README (see below) and notes that still call this “HAZ.com”

Kit child stays pointed at **staging** content, not HAZ.com content.

## Public HQ README (no local layout)

[`hugo-agent-zero/README.md`](hugo-agent-zero/README.md) is for humans on GitHub. Briefly list **this org’s** repos and point at the other org. Do **not** document `project-modules/`, `project-website/`, or Windows paths.

Rewrite the current table (it still calls `hugoagentzero_com-content` “HAZ-owned content” and sends “docs for humans” to kit Pages). Shape:

- **This org (HAZ / kit):** HQ (Issues), core (shared module), child (build-root template), child-content (content template), env-staging-content (kit staging Pages — prove modules before other sites bump).
- **Other org (HAZ.com / website):** copies of child + child-content; consumes core. Not in this org because it is a *site*, not the kit — same as any other consumer. Docs for humans live there (HugoAgentZero.com once the domain is on). Staging Pages is not HAZ.com.

Local clone layout stays in org [`AGENTS.md`](AGENTS.md) and HQ notes only.

## `project-website/` folder

Do **not** create it yet. It is only useful once the website-org repos exist to clone into. An empty folder is noise. When those remotes are up, clone into `project-website/` (or create the folder as part of that clone).

## Website org: copy on GitHub, then clone (same as anyone else)

Do **not** `cp` templates on disk and invent remotes later.

1. Create the **HAZ-website** GitHub org.
2. In that org, **Use this template** (or generate from template) for:
   - kit `hugo-agent-zero-child`
   - kit `hugo-agent-zero-child-content`
   
   Today only **child-content** is marked a GitHub template. Mark **child** a template too, or use the equivalent “generate repo from this one” so the path matches third parties.
3. Clone those **website-org** repos into `project-website/`.
4. They import kit **core** (module pin). Local replacements = abs paths to `project-modules/hugo-agent-zero-core`. `baseURL` = apex.

Other HAZ sites stay **outside** `C:\_au\work\haz`.

```mermaid
flowchart LR
  core[kit_core]
  childTpl[kit_child_template]
  contentTpl[kit_child_content_template]
  staging[kit_staging_content]
  webChild[website_org_child]
  webContent[website_org_content]
  third[other_sites_outside_haz]

  core --> childTpl
  core --> webChild
  core --> third
  childTpl --> staging
  staging --> childTpl
  childTpl -.->|Use_this_template| webChild
  contentTpl -.->|Use_this_template| webContent
  webChild --> webContent
```

## Local map

| Path | Role |
|------|------|
| [`hugo-agent-zero/`](hugo-agent-zero/) | HQ |
| `project-modules/hugo-agent-zero-core/` | Shared kit (ship) |
| `project-modules/hugo-agent-zero-child/` | Child **template** (kit; Pages build root for staging) |
| `project-modules/hugo-agent-zero-child-content/` | Content **template** |
| `project-modules/hugo-agent-zero-env-staging-content/` | Kit staging content + Pages CI (renamed) |
| `project-website/<website-child>/` | HAZ.com build root (clone of website-org repo) |
| `project-website/<website-content>/` | HAZ.com content (clone of website-org repo) |

## First How To

After the website clones exist: stub `content/blog/how-to-haz-img/` on **HAZ.com content** (knobs, `65ch` → px, band ladder, no `content_inset` subtract). Fill during the #13 review. Not in staging, not in the template.

## Custom domain

Point **HugoAgentZero.com** at website-org Pages. Never at kit staging.

## Out of scope

- #13 eyes-on / image exports (after this map).
- Cloudflare origin.
- Vanilla-demo cleanup of the public templates.
- Deleting staging in this sitting (revisit if unused).
