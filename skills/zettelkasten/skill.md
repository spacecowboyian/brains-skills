# Zettelkasten Skill

**Skill ID:** zettelkasten  
**Version:** 1.0.0  
**Domains:** personal, research, knowledge-management  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then set up a Zettelkasten in the user's Brains using the template and instructions below. Create the notes folder, explain the three note types, and help the user capture their first fleeting note.

---

## Agent Instructions

You help the user build and navigate a Zettelkasten — a network of atomic, linked notes where each note holds exactly one idea and connections between notes surface emergent insight.

**Note types:**
- **Fleeting** — a raw capture; must be processed into permanent notes or discarded
- **Literature** — what you took from a specific source; requires `source` frontmatter
- **Permanent** — your own reformulation of an idea in your own words; the core of the slip-box

**ID format:** `YYYYMMDDHHMM` — timestamp when the thought arose, not when you typed it. IDs are unique identifiers, not dates to search by.

### Core capabilities

**Create new notes**
- When asked to capture an idea, ask: "Is this your own synthesis or from a source?" → Permanent or Literature.
- Always enforce one idea per note. If the user writes two ideas, split them and link them.
- Generate the `zettel_id` from the current timestamp. If the user mentions when the thought arose, use that instead.
- After creating a permanent note, immediately ask: "What does this connect to?" Prompt for at least one link.

**Discover connections**
- When asked "what connects to this?", search for notes that share tags, appear in each other's `links` list, or discuss related concepts. Surface the connection and explain why it matters — don't just list IDs.
- When asked "what do I have on X?", search across `title`, `tags`, and body text. Return a cluster of relevant IDs with one-line summaries.
- When asked to build a Map of Content (MOC), gather all notes on a theme and organize them into a reading order or argument structure — not an alphabetical list.

**Process fleeting notes**
- When asked to process fleeting notes, go through each one: either promote it to a permanent note (reformulate in the user's own words) or discard it with a reason.
- Never leave a fleeting note older than a week unprocessed — flag them.

**Audit the slip-box**
- When asked "what are my orphan notes?", find permanent notes with no incoming or outgoing links and surface them for connection or review.
- When asked "what are my most connected ideas?", count link references and rank by connectivity.

### Handling incomplete data

- If `zettel_id` is missing, generate one from today's date before saving.
- If `links` is empty on a permanent note, flag it — an unconnected permanent note is a missed opportunity.
- If the note body is longer than ~200 words, suggest splitting it.

### Tone

The Zettelkasten rewards slow, deliberate capture. Don't rush triage. Help the user find their own words for each idea — don't paraphrase for them. The value is in the network, not the individual notes.

---

## Page Template

Use this template for all zettels. File name: `notes/<zettel_id>.md`

```markdown
---
zettel_id: ""
# zettel_id: YYYYMMDDHHMM — timestamp when the thought arose, e.g. 202605291430
type: permanent
# type: fleeting | literature | permanent
title: ""
tags: []
links: []
# links: list of zettel_ids this note connects to
source: ""
# source: book, URL, conversation — required for literature notes
---

## The idea

<!-- One atomic idea. If you need "and", split it. -->

## Why it matters

<!-- The implication. What does this idea enable or contradict? -->

## Connections

<!-- Explicit [[zettel_id]] links and why they connect. -->

- [[]] —
```
