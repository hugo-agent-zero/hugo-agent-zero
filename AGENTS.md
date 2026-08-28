# hugo-agent-zero (HQ) — context for assistants

This repository is **project HQ**: Issues, session notes, and a signpost README. It is **not** a Hugo module and does not build a site.

Kit conventions (Atomics, sysMan, CSS naming, Hugo-first) live in **core** and the local monorepo. Do not copy those here.

## Communication

Follow **Assistant style (default)** in [.agents/notes.md](.agents/notes.md).

## Session carryover

[.agents/notes.md](.agents/notes.md) is the cliff notes: **Current status** (snapshot) + **Meetings** (session minutes, newest first). Issues and PRs are the work record; notes are the overlay so you do not reconstruct the day from the forge.

**Start of session:** Read **Current status**; skim the latest **Meeting** if needed. One-line focus ack when relevant.

**Wrap-up:** On **wrap up** / **meeting notes** / **end session** → update notes on a **branch** and open a **PR**. Do not push straight to `main`. Mark skims; the agent does not merge `main`.

Implicit session end (good night, done for today, etc.): ask once whether to update notes; only then.

## Git

- Branch + PR for README, notes, and AGENTS.md.
- Issues here. PRs for kit code stay on core / child / content.
- Human-facing docs go on HAZ.com, not a Wiki.
