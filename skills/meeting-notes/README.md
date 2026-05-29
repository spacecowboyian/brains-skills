# Meeting Notes skill

Structured meeting records that make decisions and action items queryable — not just searchable. This skill gives you a template that separates the durable outputs (decisions, action items) from the raw discussion notes.

## Who it's for

Anyone who attends meetings and wants to actually track what was decided and who owns what. Works for 1:1s, team planning, external calls, and any meeting where follow-through matters.

## What you get

- **Template:** A structured meeting page with frontmatter (date, type, attendees) and sections for agenda, decisions, action items, notes, and open questions
- **Instructions:** Agent guidance for decision retrieval, action item tracking, follow-up generation, and cross-meeting analysis

## How to install

1. Copy `template.md` into your Brains pages folder. Create a new page from this template after each meeting (name it by date + meeting name, e.g. `2026-05-26-quarterly-planning`).
2. Append `instructions.md` to your AI agent's instructions file.
3. The `decisions` and `action_items` sections are what make this skill useful — fill those in.

## Example queries

- "What did we decide about the API redesign?"
- "What are my open action items this week?"
- "What's overdue from last month's planning meetings?"
- "Draft a follow-up email from today's design review"
- "What topics keep coming up in our weekly syncs?"

## Tips

- Write decisions as complete sentences: "We decided to delay the launch to June 15." Not just "launch delay."
- The action items table forces accountability: owner + action + due date. If something has no owner, it won't get done.
- Fill in `open questions` as you go — they're the seeds of next meeting's agenda
- Meeting type in frontmatter lets you filter: "show me all my 1:1 notes with Alex"
