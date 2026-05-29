# Project Tracker Skill

**Skill ID:** project-tracker  
**Version:** 1.0.0  
**Domains:** work, productivity  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then set up a project tracker in the user's Brains knowledge base using the template and instructions below. Create the project structure, initialize the instructions page, and offer to create the first project page.

---

## Agent Instructions

You help the user manage and query their project knowledge base. Pages in this domain follow the Project Tracker template below: each page covers one project, with frontmatter (project_name, status, owner, start_date, target_date, priority) and sections for objectives, deliverables, team, timeline, blockers, risks, status updates, and notes.

### Core capabilities

**Status rollups**
- When asked for a project status overview, return: project name, status, owner, target date, and one-sentence summary from the most recent status update. Group by status (in-progress first, then at-risk, then on-hold, then planning).
- When asked "what's at risk?", filter by `status: at-risk` and surface the blockers and risks sections for each.
- When asked about a specific project's status, give the most recent status update entry plus current deliverable statuses.

**Blocker and risk analysis**
- When asked "what's blocking us?", aggregate blockers across all active projects. Group by unblock owner if available.
- When asked for a risk summary, return all non-empty risks tables. Flag anything rated High likelihood + High impact.
- Distinguish between `blockers` (active, already impacting) and `risks` (potential, not yet impacting).

**Timeline forecasting**
- When asked if a project will hit its target date, look at: milestone statuses, number of remaining deliverables, and whether any blockers are unresolved. Give a probability assessment with reasoning, not just a yes/no.
- When asked for an at-risk timeline, flag projects where `target_date` is within 2 weeks and there are unresolved blockers or deliverables still not started.

**Team and ownership**
- When asked who owns what, aggregate the owner fields from deliverables tables across relevant projects.
- When asked about a specific person's workload, find all deliverables assigned to them across all projects.

**Retrospective**
- When asked how a completed project went, pull objectives, deliverables (final statuses), and status updates. Identify what shipped, what was cut, and what the timeline looked like vs. plan.

### Handling incomplete data

- If `status_updates` is empty, say so and fall back to deliverable statuses for current state.
- If `target_date` is missing, don't forecast or flag timeline risk — note the missing field instead.
- If `blockers` is empty, treat the project as unblocked. Don't infer blockers from notes.

### Output format

- Status rollups: table format (name, status, owner, target date, latest update).
- Blocker lists: grouped by project, owner, and resolution timeline.
- Risk summaries: table with likelihood and impact ratings.
- Keep status summaries to one sentence per project unless asked for detail.

---

## Page Template

Use this template when creating a new project tracker page. File name: `projects/<project-name>.md`

```markdown
---
project_name: ""
status: planning
# status: planning | in-progress | on-hold | at-risk | complete | cancelled
owner: ""
start_date: ""
target_date: ""
priority: medium
# priority: critical | high | medium | low
tags: []
---

## Objectives

<!-- What does success look like? 2–4 concrete outcomes. -->

-
-

## Deliverables

<!-- What will actually ship? List the concrete outputs. -->

| Deliverable | Owner | Due | Status |
|-------------|-------|-----|--------|
|  |  |  | not started |
|  |  |  | not started |

## Team

| Name | Role |
|------|------|
|  |  |
|  |  |

## Timeline

<!-- Key milestones and dates. -->

| Milestone | Target date | Status |
|-----------|-------------|--------|
|  |  | not started |
|  |  | not started |

## Blockers

<!-- What is actively preventing progress? List with owner of unblocking action. -->

<!-- Format: "Blocked on [thing]. Owner: [name]. Expected resolution: [date or event]." -->

## Risks

<!-- What could go wrong? Rate each: Low / Medium / High. -->

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
|  | Medium | Medium |  |

## Status updates

<!-- Running log of updates. Add newest at the top. -->

<!-- YYYY-MM-DD: [one-sentence status] -->

## Notes

<!-- Background context, decisions made, links to relevant docs. -->
```
