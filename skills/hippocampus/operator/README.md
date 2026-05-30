# Operator Skill

The second brain of an **operator** running many concurrent ventures. Where PARA sorts by actionability and Zettelkasten links atomic notes, Operator is **project-scoped and operational**: everything about a project lives under `projects/<slug>/`, each project carries living state pages, open loops follow a hub-and-spoke trail, and raw input is synthesized down into durable facts and decisions at write time.

Use this when you juggle several projects at once (a startup, side businesses, hobbies, personal life) and need to walk into any one of them and instantly see *where it is*, *what's next*, and *what's unresolved*.

## Install

Paste into your AI chat:

```
Read https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/hippocampus/operator/skill.md
then set up my Brains knowledge base using this skill.
```

## The method

- **Project-scoping** — `projects/<slug>/` holds that project's `canonical/`, `decisions/`, `data/`, `history/`, `state/`. Brain root is cross-cutting only.
- **State pages** — `state/current-state.md`, `state/next-actions.md`, `state/priorities.md` per project.
- **Hub-and-spoke open loops** — root `open-loops.md` (project rollups) → `projects/<slug>/open-loops.md` (loop rollup) → `open-loop-<slug>.md` (detail). Resolve = archive to `history/`.
- **Write-time synthesis** — `data/` (raw) → `canonical/` (distilled) → `decisions/` (committed, with `decisions-log.md`).
- **Cross-cutting root** — `people/<name>/` (bios + personal), `dumps/` (raw multi-domain memos), root `canonical/`/`data/` (shared), `instructions/` (operating rules).

## Capabilities

The agent can:
- Scaffold a new project (`readme.md`, `open-loops.md`, `state/next-actions.md`) and register it in the root index.
- Route incoming content to the right project (or to `people/`/`dumps/`/root for cross-cutting).
- Maintain the open-loop hub-and-spoke and archive resolved loops.
- Keep `state/` pages terse and current; surface stale projects.
- Synthesize raw `data/` into `canonical/` facts and `decisions/` records.

## Example queries

- "What's on my plate across all projects?"
- "Set up a new project for <thing>."
- "What's open in <project>?"
- "Ingest this dump and distribute it into the right projects."
- "Which projects have gone stale?"
- "Close the loop on <X> and archive it."

## Distinct from

- **PARA** — sorts everything by actionability into 4 life-buckets; Operator is project-centric with per-project operational state.
- **Johnny.Decimal** — numeric addressing; Operator uses semantic project slugs.
- **Zettelkasten** — atomic interlinked notes; Operator is structured project workspaces.
- **project-tracker** — a single-project status *page template*; Operator is the *whole-brain layout* for many projects.
