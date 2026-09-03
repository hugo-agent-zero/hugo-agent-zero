---
name: Core versioning v1 branch
overview: "HX-first versioning + how sites get started. Branch v1.x.x + tags; templates not forks; core upstream. Also: clean child/content into a vanilla out-of-box demo (not the current sandbox). HQ #19."
todos:
  - id: branch-v1
    content: Create branch v1.x.x from current core main; merge policy = compatible 1.x only
    status: pending
  - id: tag-v1.0.0
    content: Tag v1.0.0 on that branch — baseline snapshot (optional lock point)
    status: pending
  - id: child-and-pages
    content: Child go.mod + pages.yml both use hugo mod get core@v1.x.x — same path for live site and site copies
    status: pending
  - id: child-template-flag
    content: "Mark hugo-agent-zero-child as a GitHub template (content starter already is)"
    status: pending
  - id: vanilla-demo
    content: "Intentional cleanup — child + content starter as vanilla out-of-box demo (Lorem, thin menus); separate from HAZ.com product content"
    status: pending
  - id: doc-hx
    content: "HQ #19 + READMEs — versioning + template-not-fork + do-not-copy-core (plain English)"
    status: pending
  - id: verify
    content: Pages build + close #19
    status: pending
isProject: false
session: 2026-09-02
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/19
status: parked
---

# Versioning + GitHub HX (HQ #19)

Versioning, Go modules, and GitHub “how do I start a site?” overlap. Solve them together so mum doesn’t touch pins or open PRs nobody wants.

---

## Problem (plain English)

Go does **not** have npm-style ranges (`^1.0.0`). A pin is exact: tag, branch tip, or ugly hash.

**Optimize for:** merge core → site still builds → humans don’t babysit `go.mod`. Not for HackerNews DX.

**Also:** “fork” on GitHub implies PRs back. That is **wrong** for a unique site. Sites need an **independent copy**, not a fork network.

---

## Who owns what

| Org (names TBD) | Owns | Role |
|-----------------|------|------|
| **Kit** (`hugo-agent-zero`) | core, child *starter*, content *starter*, HQ | Shared kit |
| **Site** (e.g. `haz-com`) | that site’s child + content copies | One unique site |

**Default path to start a site:** copy **child** + **content** only. **Do not copy core** — pull it as a module (`@v1.x.x` or a lock tag).

We use the live demo the same way first (true dogfood), then the site org follows the same rules.

---

## Template, not fork

| Mechanism | Meaning | For HAZ sites? |
|-----------|---------|----------------|
| **Fork** | Linked copy; GitHub expects PRs upstream | **No** — we won’t take site PRs into kit child/content |
| **Use this template** | New independent repo; no fork link | **Yes** — mum-proof |

**Today on GitHub:**

| Repo | Template? |
|------|-----------|
| `hugo-agent-zero-child` | **No** — turn on |
| `hugo-agent-zero-child-content` | **Yes** |
| `hugoagentzero_com-content` | **No** — live demo content; not the starter |

Docs / Getting Started should say **template**, never “fork,” unless someone is contributing to core.

---

## Sandbox vs vanilla demo (intentional cleanup)

**Today:** kit **child** and **content** have been a **dev sandbox** — experiments, demo posts, half-baked pages (content more than child). Fine for building the kit.

**They are not a “Start here” handoff**, even if GitHub marks them as templates. A template flag only means “Use this template” creates a copy — it does **not** mean the copy is fit for someone else.

**Gate:** do **not** tell people to start from these until the build reads as a **vanilla out-of-the-box demo** — clear structure, Lorem / light placeholder copy, thin menus, no sandbox clutter.

| Repo | Intent |
|------|--------|
| **Child starter** | Clean sysMan / chrome defaults — product-ready, not a junk drawer |
| **Content starter** (`hugo-agent-zero-child-content`) | Placeholder pages/posts that show shapes (home, about, blog) without kit-dev noise |
| **Live HAZ.com content** (`hugoagentzero_com-content`) | Real product/docs site — **not** the same job as the starter; may stay richer |

Order of operations: versioning can land first; **public “Start here” waits on vanilla cleanup** (and then template flag on child if not already).

Related: HQ [#21](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/21) is HAZ.com *product* content — separate from “vanilla starter demo.”

---

## Core versioning (Go’s limitation → our workaround)

| Want | Go / Git | What it means |
|------|----------|---------------|
| **Latest 1.x (default)** | Branch named **`v1.x.x`** → `hugo mod get …-core@v1.x.x` | Moves when we merge compatible work |
| **Frozen** | Tag **`v1.2.3`** → `@v1.2.3` | Never moves |
| **Breaking (rare)** | Branch **`v2.x.x`** + tag `v2.0.0` | New major line; update default once |

`v1.x.x` is a **branch name**, not a Go range. Same job for HX: “always latest compatible 1.x” without hash babysitting.

- **`main`** — day-to-day kit work (can lead briefly)
- **`v1.x.x`** — what sites and the live demo use; compatible merges only
- Tags — optional lock points; **never move** an old tag
- Skip a branch named `v1.0.0` — fights `v1.0.1` / `v1.2.3` tags

---

## Same rule for live demo and site copies

**Child starter** (what people template):

```bash
hugo mod get github.com/hugo-agent-zero/hugo-agent-zero-core@v1.x.x
```

Commit `go.mod` + `go.sum`.

**Live Pages** — same line before build so each run refreshes the branch tip:

```yaml
- name: Use latest 1.x core
  working-directory: site
  env:
    GOPROXY: direct
  run: hugo mod get github.com/hugo-agent-zero/hugo-agent-zero-core@v1.x.x
```

Content step unchanged: `content@${{ github.sha }}`.

No special CI-only path. We eat what we ship.

---

## Day-to-day (humans)

| You did | What happens |
|---------|----------------|
| Compatible core change | Merge `main` → update **`v1.x.x`** → optional tag → next Pages / site build |
| Child sysMan change | Merge child → next Pages run |
| Breaking kit change | **`v2.x.x`** + `v2.0.0`; change default pin docs once |

**No** child pin PR after every core merge if `v1.x.x` moved.

Early on: keep `main` and `v1.x.x` in sync (fast-forward) until a staging gap is useful.

---

## Mum story (README)

> **Start a site:** Use the **child** and **content** GitHub **templates** (not forks). Do not copy core.  
> **Default:** kit follows the **`v1.x.x`** line — you don’t manage version numbers.  
> **Want frozen:** pin core to a tag like **`v1.2.3`** once.  
> **Big break:** rare; kit moves to **`v2.x.x`**.

---

## Honest limits

- `@v1.x.x` = tip of that **branch**, not “highest semver tag”
- Local `hugo` matches CI if you run the same `mod get`
- Site org creation (`haz-com` etc.) is a **follow-on** — versioning + template flags should land first so the org copies the right story

---

## Not doing

- npm-style ranges (Go can’t)
- Moving tags to mean new code
- Different version rules for live demo vs templates
- Recommending forks of child/content for new sites
- Copying / forking core for a normal site
- Treating current sandbox content as the public starter forever

---

## Test plan

- [ ] Branch `v1.x.x` + tag `v1.0.0` on core
- [ ] Child + pages both `@v1.x.x`; build OK
- [ ] Merge to `v1.x.x` → next Pages uses new core without pin PR
- [ ] Child repo marked as GitHub template
- [ ] Starter child/content read as vanilla demo (not sandbox shit-show)
- [ ] HQ #19 / READMEs say template + versioning in plain English
- [ ] Close #19
