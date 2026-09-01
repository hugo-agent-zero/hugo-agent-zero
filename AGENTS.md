# hugo-agent-zero (HQ) — context for assistants

This repository is **project HQ**: Issues, session notes, and a signpost README. It is **not** a Hugo module and does not build a site.

Kit conventions (Atomics, sysMan, CSS naming, Hugo-first) live in **core** and the local monorepo. Do not copy those here.

## Communication

Follow **Assistant style (default)** in [.agents/notes.md](.agents/notes.md).

## Session carryover

[.agents/notes.md](.agents/notes.md) is the project **diary**: one file, dated sittings, newest first. Not Issues. Issues and PRs are the tickets; notes are the story (time + thoughts, what we discussed, context for the next person). Mention tickets in prose.

**Start of session:** Read the **newest Meeting** and **Now** if present. One-line focus ack when relevant. Do not rewrite old sittings.

**Wrap-up:** On **wrap up** / **meeting notes** / **end session** → append a dated Meeting on a **branch** and open a **PR**. Strike a **Now** line if it changed. Do not rewrite Focus or prior sittings. Do not push straight to `main`. Mark skims; the agent does not merge `main`.

Implicit session end (good night, done for today, etc.): ask once whether to update notes; only then.

## Git

- Branch + PR for README, notes, and AGENTS.md.
- Issues here. PRs for kit code stay on core / child / content.
- Human-facing docs go on HAZ.com, not a Wiki.
