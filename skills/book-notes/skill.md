# Book Notes Skill

**Skill ID:** book-notes  
**Version:** 1.0.0  
**Domains:** personal, learning  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then set up a book notes project in the user's Brains knowledge base using the template and instructions below. Create the project structure, initialize the instructions page, and offer to add the first book.

---

## Agent Instructions

You help the user get value from their book notes knowledge base. Pages in this domain follow the Book Notes template below: each page covers one book, with frontmatter fields (title, author, year, genre, date_read, rating) and structured sections (summary, key ideas, key quotes, how it changed me).

### Core capabilities

**Retrieval and recommendation**
- When asked for book recommendations on a theme, search across `summary`, `key ideas`, and `tags` fields. Return title, author, and one sentence on why it fits the theme.
- When asked "what have I read about X?", pull relevant key ideas and quotes across all matching pages, not just titles.
- When asked for top-rated books, filter by `rating: 5` or `rating: 4` — treat 5 as life-changing, 4 as highly recommended.

**Synthesis**
- When asked "what have I learned about X?", synthesize key ideas across all relevant books, not per-book summaries. Group by theme, not by title.
- When asked to compare books on a topic, pull the relevant sections from each and compare directly.
- Surface connections between books the user may not have noticed (same idea appearing in multiple books, contradictory takes on the same topic).

**Insight extraction**
- When asked for your "best quotes on X," search the `key_quotes` section across all pages and return the most relevant ones with attribution.
- When asked what books changed you the most, use the `how_it_changed_me` field and `rating`.

### Handling incomplete data

- If `rating` is missing, don't assume — ask or omit it from ranked results.
- If `how_it_changed_me` is empty, skip that field in synthesis. Don't paraphrase the summary as a substitute.
- If `date_read` is missing, don't guess recency.

### Output format

- For book lists: title + author + one-sentence hook. Keep it scannable.
- For synthesis: prose paragraphs with inline citations (book title in parentheses).
- For quotes: blockquote format with attribution.
- Avoid long per-book summaries unless explicitly asked. Prioritize synthesis over repetition.

---

## Page Template

Use this template when creating a new book note page. File name: `books/<title-author>.md`

```markdown
---
title: ""
author: ""
year: 
genre: ""
date_read: ""
rating: 
# rating: 1–5 (1 = wouldn't recommend, 5 = life-changing)
pages: 
status: read
# status: reading | read | abandoned | want-to-read
tags: []
---

## Summary

<!-- 3–5 sentences. What is the book about? What is its central argument or story? -->

## Key ideas

<!-- 3–7 bullet points. The ideas you'd explain to a friend. -->

-
-
-

## Key quotes

<!-- Copy the lines you underlined. Include page numbers if possible. -->

> "Quote here." (p. XX)

> "Quote here." (p. XX)

## How it changed me

<!-- What shifted in how you think, act, or see the world? Be specific. -->

## Who should read this

<!-- 1–2 sentences. What kind of person gets the most out of this book? -->

## Related books

<!-- Books this one reminded you of, or that make a good pair read. -->

-
```
