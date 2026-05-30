# Meeting Notes

> Structured meeting records that make decisions and action items queryable — not just searchable.

## Install

Paste into your AI chat:

```
Read https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/lobes/meeting-notes/skill.md
then set up a new project in my Brains knowledge base using this skill.
```

## What this skill does

Sets up a meeting notes knowledge base with a structured page template and an AI agent configured to work with it. Once you have pages, the agent can:

- Retrieve decisions by topic across any set of meetings
- Surface open and overdue action items by owner or due date
- Draft follow-up emails from a meeting's decisions and action items
- Summarize what happened across a set of meetings by theme
- Flag topics that keep recurring across standups or planning sessions

## Example queries

- `What did we decide about the API redesign?`
- `What are my open action items this week?`
- `Draft a follow-up email from today's planning meeting`
- `What topics keep coming up in our weekly syncs?`
- `What's overdue from last month?`

## Files

| File | Purpose |
|------|---------|
| [`skill.md`](skill.md) | Install file — agent instructions + template combined |
| [`skill.json`](skill.json) | Metadata manifest |
| [`template.md`](template.md) | Page template (standalone) |
| [`instructions.md`](instructions.md) | Agent instructions (standalone) |

## License

[MIT](../../LICENSE)
