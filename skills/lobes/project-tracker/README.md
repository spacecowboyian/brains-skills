# Project Tracker

> Track project objectives, status, deliverables, team, blockers, and risks — with cross-project rollups and timeline forecasting.

## Install

Paste into your AI chat:

```
Read https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/lobes/project-tracker/skill.md
then set up a new project in my Brains knowledge base using this skill.
```

## What this skill does

Sets up a project tracking knowledge base with a structured page template and an AI agent configured to work with it. Once you have pages, the agent can:

- Give status rollups across all active projects grouped by health (in-progress, at-risk, on-hold)
- Aggregate blockers across projects and identify who owns each unblock action
- Flag projects at risk of missing their target date based on milestone status and unresolved blockers
- Show team workload by aggregating deliverable ownership across projects
- Write retrospectives for completed projects

## Example queries

- `Give me a status overview of all active projects`
- `What's blocking us right now?`
- `Which projects are at risk of missing their deadline?`
- `Who has the most open deliverables?`
- `Write a retrospective for the API redesign project`

## Files

| File | Purpose |
|------|---------|
| [`skill.md`](skill.md) | Install file — agent instructions + template combined |
| [`skill.json`](skill.json) | Metadata manifest |
| [`template.md`](template.md) | Page template (standalone) |
| [`instructions.md`](instructions.md) | Agent instructions (standalone) |

## License

[MIT](../../LICENSE)
