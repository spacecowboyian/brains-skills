# Johnny.Decimal Skill

**Skill ID:** johnny-decimal  
**Version:** 1.0.0  
**Domains:** personal, productivity, knowledge-management  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then help the user design their Johnny.Decimal system in Brains using the template and instructions below. Start by defining their areas, then create the index page, and assign the first ID together.

---

## Agent Instructions

You help the user build and navigate a Johnny.Decimal system — a strict numeric hierarchy that gives every piece of knowledge a unique, memorable address so anything can be found in seconds without search.

**Structure rules (non-negotiable):**
- Maximum **10 areas** per system, numbered in decades: 10-19, 20-29, … 90-99
- Maximum **10 categories** per area, numbered sequentially: 10.01, 10.02, … 10.09, 10.10
- Items within a category get a two-digit suffix: 10.01.01 through 10.01.99
- Every file's name starts with its ID: `22.04 Checking account.md`

**ID anatomy:** `AC.ID` where `A` is the area decade, `C` is the category number, `.ID` is the optional item suffix.

### Core capabilities

**Assign IDs to new content**
- When the user wants to file something, identify the right area first, then the right category. Only create a new category if no existing one fits — categories are meant to be reused.
- Return the exact ID and proposed filename before creating the page.
- If the system has no areas yet, help the user design their top-level areas before assigning any IDs. Areas should reflect the user's actual life domains, not generic categories.

**Maintain the index**
- Keep an index page at `00.00 Index.md` listing all areas and categories with their IDs and one-line descriptions.
- When a new category is created, update the index immediately.
- When asked "what's in area 20?", return all categories and item counts for that decade.

**Search and navigate**
- When asked "where is X?", return the exact JD ID and filename — not a search result list.
- When asked "what ID should I use for X?", walk through the area → category → item reasoning and propose the next available ID.
- When asked for a full system map, render the hierarchy as a nested list grouped by area.

**Enforce the rules**
- Never allow more than 10 areas (10-99 = 9 possible decades).
- Never allow a category outside its area decade (e.g., 12.05 cannot live in the 20s area).
- If the user tries to nest deeper than three levels (area > category > item), push back — Johnny.Decimal is intentionally flat. Use tags or links for cross-references instead.

### Handling incomplete data

- If `jd_id` is missing, do not save the page — the whole system depends on IDs being present.
- If the proposed content doesn't fit any existing category cleanly, surface that explicitly before creating a new category — the user may have a naming mismatch rather than a gap.
- If the system has more than 9 area decades already, surface the constraint and help the user consolidate before adding more.

### Tone

Johnny.Decimal is about decisiveness. The system only works if every filing decision is fast and final. Don't dwell on edge cases — make a call, assign the ID, move on. Correctness beats perfection.

### Routing notes from lobes

Lobe skills (book-notes, meeting-notes, recipes, …) define a note's *fields* but never its *location* — that is your job. When a lobe asks where one of its pages belongs, assign it a JD address: pick the right area and category for that note type (e.g. meeting-notes under a "Work / Meetings" category), return the `AC.ID` and filename `<jd_id> <title>.md`, and update the index. Have the lobe write that path to the page's `filed_at`. You own the ID and location; the lobe owns everything inside the page.

---

## Page Template

Use this template for category and item pages. File name: `<jd_id> <title>.md`

```markdown
---
jd_id: ""
# jd_id: AC.ID format — area (10-99), category (.01-.09), optional item (.01-.99)
# Example: 22.04 for a category page, 22.04.03 for a specific item
area: ""
# area: e.g. "20-29 Finance"
category: ""
# category: e.g. "22 Banking"
title: ""
tags: []
---

## Content

<!-- The actual information for this item. -->

## Notes

<!-- Context, links, history. -->

## Related

<!-- Other JD IDs that connect to this one. -->

- [[]]
```
