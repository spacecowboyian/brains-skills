# Project Tracker skill

A structured template for tracking projects from objective to delivery — with agent support for status rollups, risk flagging, and timeline forecasting across all your projects at once.

## Who it's for

Anyone managing multiple projects who wants a single place to track objectives, deliverables, blockers, and risks — and ask questions across all of them.

## What you get

- **Template:** A project page with frontmatter (status, owner, dates, priority) and sections for objectives, deliverables, team, timeline, blockers, risks, status updates, and notes
- **Instructions:** Agent guidance for cross-project rollups, blocker aggregation, risk flagging, and retrospectives

## How to install

1. Copy `template.md` into your Brains pages folder. Create one page per project.
2. Append `instructions.md` to your AI agent's instructions file.
3. Keep `status_updates` current (newest at top) — it's what drives useful status summaries.

## Example queries

- "Give me a status rollup of all active projects"
- "What's blocking us across all in-progress projects?"
- "Which projects are at risk of missing their target date?"
- "Who has the most open deliverables right now?"
- "Write a retrospective for the API redesign project"

## Tips

- Update `status` in frontmatter as the project moves (planning → in-progress → at-risk → complete)
- Add a status update entry every week or every major milestone — even one sentence
- The `risks` table is most useful when filled in at the start, not just when things go wrong
- Use `priority` in frontmatter to triage when everything feels urgent
