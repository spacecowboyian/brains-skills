# Meeting Notes Skill

**Skill ID:** meeting-notes  
**Version:** 1.0.0  
**Domains:** work, productivity  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then set up a meeting notes project in the user's Brains knowledge base using the template and instructions below. Create the project structure, initialize the instructions page, and offer to log the next meeting.

**Filing — important:** This lobe is a *note template only*; it does not choose a folder. Before creating pages, check whether a hippocampus skill (PARA, Johnny.Decimal, Zettelkasten, or Mind Palace) is active. If one is, ask it where each page belongs and record that path in the page's `filed_at` field. If no structure is active, fall back to a flat `meeting-notes/` folder. Never hardcode a location here.

---

## Agent Instructions

You help the user get more value from their meeting notes knowledge base. Pages in this domain follow the Meeting Notes template below: each page covers one meeting, with frontmatter (date, meeting_type, attendees, status) and sections for agenda, decisions, action items, notes, and open questions.

### Core capabilities

**Decision retrieval**
- When asked "what did we decide about X?", search the `decisions` section across all relevant pages and return the decision with date and meeting name.
- When multiple decisions on the same topic exist, surface them chronologically and flag if they appear to contradict each other.

**Action item tracking**
- When asked "what are my open action items?", return all rows from action_items tables where the owner matches the user and the due date has not passed (or is not set). Group by due date.
- When asked about a specific person's action items, filter by owner field in the action_items table.
- Flag action items that are overdue (due date is past) without being cleared.

**Meeting summaries**
- When asked to summarize a meeting, prioritize `decisions` and `action_items` — those are the durable outputs. `notes` is context.
- When asked what happened in a set of meetings (e.g. "last month's planning meetings"), give a single narrative summary grouped by theme, not a per-meeting list.

**Follow-up generation**
- When asked to draft a follow-up email or message from a meeting, use `decisions` + `action_items`. Format: brief recap of decisions made, bulleted action items with owners and deadlines.
- Don't include `notes` in follow-up drafts unless explicitly asked.

**Cross-meeting analysis**
- When asked about recurring topics or themes, look for the same keywords appearing across `agenda`, `decisions`, and `notes` over time.
- When asked "what keeps coming up in standups?" or similar, cluster by topic, not by date.

### Handling incomplete data

- If `decisions` is empty, say so explicitly when answering decision-retrieval queries — don't infer decisions from the `notes` section.
- If `action_items` has no due dates, surface the item without a deadline estimate. Don't guess dates.
- If `attendees` is missing, omit it from summaries rather than guessing.

### Output format

- Action item lists: table format (owner, action, due date).
- Decision lists: plain sentences with date attribution.
- Meeting summaries: short prose, 3–5 sentences max unless asked for detail.

---

## Page Template

Use this template when creating a new meeting notes page. This lobe defines the note shape only — it does not pick a folder. The active hippocampus skill decides where it is filed (recorded in `filed_at`); with no structure active, default to `meeting-notes/<YYYY-MM-DD>-<meeting-name>.md`.

```markdown
---
file_type: meeting-notes
filed_at: ""
# filed_at: path set by the active hippocampus skill — flat `meeting-notes/` folder if no structure active
date: ""
meeting_type: ""
# meeting_type: standup | 1:1 | planning | retrospective | decision | external | other
attendees: []
# attendees: list of names or handles
facilitator: ""
status: complete
# status: scheduled | in-progress | complete | cancelled
tags: []
---

## Agenda

<!-- What was the meeting supposed to cover? List items or paste the invite description. -->

-
-

## Decisions

<!-- The most important section. Every decision made, stated plainly. -->

<!-- Format: "We decided to [action]." Include rationale in brackets if non-obvious. -->

-
-

## Action items

<!-- Who is doing what, by when? -->

| Owner | Action | Due |
|-------|--------|-----|
|  |  |  |
|  |  |  |

## Notes

<!-- Anything else worth capturing: context, discussion highlights, open questions raised. -->

## Open questions

<!-- Questions that came up but weren't resolved. Follow up needed? -->

-
```
