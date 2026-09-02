# Plans (project archive)

Cursor Plan mode writes to `~/.cursor/plans/` by default (outside the repo). **This folder** is the git-tracked copy — project DNA alongside [.agents/notes.md](../notes.md).

**Home:** [hugo-agent-zero/hugo-agent-zero](https://github.com/hugo-agent-zero/hugo-agent-zero) (HQ). SOT copy may lag.

## Filenames

Keep the **same basename** Cursor generated (slug + hash), e.g. `41_dialog_+_enqueue_note_af4fe94a.plan.md`. Do not rename to date-only names.

## Frontmatter (traceability)

When copying or authoring a plan here, extend YAML frontmatter so slices tie together:

```yaml
---
name: Short title
session: YYYY-MM-DD
status: parked | in_progress | shipped
hq_issue: https://github.com/hugo-agent-zero/hugo-agent-zero/issues/N
child_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-child/pull/N
core_pr: https://github.com/hugo-agent-zero/hugo-agent-zero-core/pull/N
related:
  - HQ #34 — design comment only
---
```

Omit keys that do not apply. Mention issues/PRs in prose inside the plan when helpful.

## Wrap-up

On **wrap up** / **meeting notes** / **end session**, if Plan mode was used this session:

1. Copy each session plan from `~/.cursor/plans/` → `.agents/plans/` (skip if unchanged).
2. Update frontmatter (`status`, PR URLs).
3. In the Meeting entry in `notes.md`, add **Plans:** bullets linking to files here.

See **Plans** in root [AGENTS.md](../../AGENTS.md) and `.cursor/rules/session-carryover.mdc`.
