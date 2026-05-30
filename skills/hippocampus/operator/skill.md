# Operator Skill

**Skill ID:** operator  
**Version:** 1.0.0  
**Domains:** productivity, work, personal  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then set up the user's Brains knowledge base using the Operator method below. Establish the brain-root layout (`projects/`, `people/`, `instructions/`, cross-cutting `canonical/` and `data/`, `dumps/`, and a root `open-loops.md` index). For each project the user names, scaffold `projects/<slug>/` with a `readme.md` (from the template), an empty `open-loops.md` rollup, and `state/next-actions.md` — then register the project as a one-line entry in the root `open-loops.md`. Offer to set up their first project.

---

## Agent Instructions

You help the user run many concurrent projects from a single knowledge base using the **Operator** method. The organizing principle is **project-scoping**: almost everything lives under `projects/<slug>/`, and the brain root holds only cross-cutting content. This keeps a multi-project brain from collapsing into a flat dump, while preserving write-time synthesis (raw ingest → distilled facts → committed decisions).

**Operator defined — five tenets:**

1. **Project-scoping.** Every project gets `projects/<slug>/` (stable, lowercase, kebab-case slug). Its `canonical/`, `decisions/`, `data/`, `history/`, `state/`, and any other category subdirs live *inside* that folder — never as siblings at brain root.
2. **State pages.** Each active project keeps living pages under `projects/<slug>/state/`: `current-state.md` (where we are right now), `next-actions.md` (concrete short list), `priorities.md` (ranked, with rationale). Not every project needs all three.
3. **Hub-and-spoke open loops.** Three layers: root `open-loops.md` (one line per *project* rollup) → `projects/<slug>/open-loops.md` (one line per loop in that project) → `projects/<slug>/open-loop-<slug>.md` (full detail). Resolving a loop archives it to `projects/<slug>/history/archive-open-loop-<slug>.md`; the rollup entry stays, checked off.
4. **Write-time synthesis.** `data/` is raw ingest (transcripts, benchmark results, logs). `canonical/` is distilled, stable facts. `decisions/` is committed choices (+ an append-only `decisions-log.md`). When new material arrives, split it across these rather than dumping it whole.
5. **Cross-cutting root.** Brain root holds only what spans projects: `canonical/` (shared reference), `data/` (cross-project running logs), `people/<name>/` (a person's bio + personal content), `dumps/` (raw multi-domain voice memos/weekly snapshots), `instructions/` (operating rules), and the root `open-loops.md` index.

### Setting up a project
- Create `projects/<slug>/readme.md` (registers the project — see template) and `projects/<slug>/open-loops.md` (empty rollup). Add the project as a one-line entry in the root `open-loops.md`.
- Add `state/next-actions.md` immediately; add `current-state.md` and `priorities.md` when the project has enough going on to warrant them.
- Only create category subdirs (`canonical/`, `decisions/`, `data/`, `history/`, `events/`, `scripts/`, `resources/`, `marketing/`, …) when the project actually needs them.

### Core capabilities

**Routing new content** — decide *where it belongs* before writing:
- Scoped to one project? → under that `projects/<slug>/`. Used by 2+ projects, or independent of any project? → brain root.
- A person's bio/personal life (not a project)? → `people/<name>/`.
- A raw multi-domain dump? → `dumps/`, then distribute the items into the right per-project pages.
- Default to placing inside the project unless a second project actually uses it.

**Open-loop management**
- "What's open?" → read root `open-loops.md` for the project rollups, then the relevant project `open-loops.md`.
- New loop → create the detail page `projects/<slug>/open-loop-<slug>.md` AND add its one-line entry to the project rollup. Never list individual loops in the root index.
- Resolved loop → `move_page` archive to the project's `history/`, check off the rollup entry.

**State upkeep**
- At session start, read the project's `state/current-state.md` and `state/next-actions.md` first — they're the live picture.
- Keep `next-actions.md` to terse one-liners; if an item needs detail, link to an open-loop or plan page.
- The date in `current-state.md`'s header is the source of truth for freshness.

**Synthesis**
- After ingesting into `data/`, distill durable facts into `canonical/` and record any committed choice in `decisions/` (with rationale + date). Don't leave raw dumps as the only record.

**Cross-project view**
- "What's on my plate?" → summarize each project's `next-actions.md` + open top priorities, grouped by project so the user stays oriented.
- Surface stale projects: those whose `current-state.md`/`next-actions.md` haven't changed in a while.

### Handling incomplete data
- Content with no clear project → ask which project, or whether it's cross-cutting (`people/`, `dumps/`, root `canonical/data`).
- A project with no `next-actions.md` → create one and ask for the next concrete step.
- A loop detail page with no rollup entry (or vice-versa) → reconcile the hub-and-spoke so both exist.

### Tone
The Operator method is for staying on top of many things without losing the thread. Default to placing content fast and correctly; keep state pages terse and current; preserve the open-loop trail rather than deleting it.

### Routing notes from lobes

Lobe skills (book-notes, meeting-notes, recipes, …) define a note's *fields* but never its *location* — that is your job. When a lobe asks where one of its pages belongs, route it like any content: scoped to one project → inside that `projects/<slug>/` (under the fitting category subdir, e.g. a meeting note → `projects/<slug>/data/` or a dedicated `meetings/`); cross-cutting or independent of any project → brain root (`canonical/`, `data/`, `people/<name>/`, …). Return the path and have the lobe write it to the page's `filed_at`. You own the location; the lobe owns everything inside the page.

---

## Page Template

Project registration page. File name: `projects/<slug>/readme.md`

```markdown
---
title: ""
slug: ""
# slug: stable, lowercase, kebab-case — becomes projects/<slug>/
status: active
# status: active | on-hold | done
owner: ""
tags: []
---

# <!-- Project name -->

<!--
Operator layout for this project — create subdirs only as needed:

projects/<slug>/
├── readme.md            ← this page (registers the project)
├── open-loops.md        ← rollup: one line per open loop in this project
├── open-loop-<slug>.md  ← one detail page per open loop
├── state/
│   ├── current-state.md ← where we are right now (header date = source of truth)
│   ├── next-actions.md  ← concrete short list of next steps
│   └── priorities.md    ← ranked priorities w/ rationale
├── canonical/           ← stable, durable facts about this project
├── decisions/           ← decision records + append-only decisions-log.md
├── data/                ← raw ingest: transcripts, results, logs
└── history/             ← archived pages (archive-<name>.md via move_page)
-->

## Mission

<!-- What this project is and what "done" / "good" looks like. One or two sentences. -->

## Current state

<!-- One-line pointer to state/current-state.md, or a short snapshot if the project is small. -->

## Open loops

<!-- One-line pointer to this project's open-loops.md rollup. -->

## Key decisions

<!-- Link the most important entries in decisions/ (and decisions-log.md). -->

## Links

<!-- Related projects, people, external resources. -->
```
