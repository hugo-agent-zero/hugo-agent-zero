# Hugo Agent Zero

Project home for the **kit org**. **Not a Hugo module.**

- **Issues** live here (including bugs that span core / child / content).
- **Notes** (session cliff notes): [`.agents/notes.md`](.agents/notes.md).
- **Docs for humans** belong on **HAZ.com** (separate website org) — not a GitHub Wiki, and not the staging Pages site below.

In chat we call this repo **HQ**.

## This org

PRs go on the repo you changed:

| Repo | Role |
|---|---|
| [hugo-agent-zero-core](https://github.com/hugo-agent-zero/hugo-agent-zero-core) | Shared kit. Other sites import this. |
| [hugo-agent-zero-child](https://github.com/hugo-agent-zero/hugo-agent-zero-child) | Build-root / starter child. Copy it; do not PR site work back here. |
| [hugo-agent-zero-child-content](https://github.com/hugo-agent-zero/hugo-agent-zero-child-content) | Content template. Copy it to manage a site’s content. |
| [hugo-agent-zero-env-staging-content](https://github.com/hugo-agent-zero/hugo-agent-zero-env-staging-content) | Kit **staging** content + Pages. Prove modules before other sites bump pins. **Not** HAZ.com. |

## The website org

**HAZ.com** (HugoAgentZero.com) lives in [hugoagentzero-com](https://github.com/hugoagentzero-com). It is a *site*: copies of child + child-content that consume **core**, same as any other consumer.

| Repo | Role |
|---|---|
| [haz-com-child](https://github.com/hugoagentzero-com/haz-com-child) | HAZ.com build root |
| [haz-com-content](https://github.com/hugoagentzero-com/haz-com-content) | HAZ.com content |

It is not in this org because this org is the kit. Staging Pages is the kit crash dummy; HAZ.com is the product site.
