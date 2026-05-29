# Contributing to brains-skills

Thanks for wanting to add a skill. Here's how.

## What makes a good skill

A skill should be:

- **Domain-specific** — scoped to one type of knowledge (books, meetings, recipes, etc.)
- **Template-first** — the `template.md` should be immediately useful without reading the README
- **Agent-aware** — `instructions.md` should give an AI agent real, actionable guidance, not generic platitudes
- **Model-agnostic** — instructions should work with any LLM, not reference Claude/GPT/Copilot by name

## Skill structure

Every skill lives in `skills/<skill-id>/` and contains exactly these five files:

```
skills/<skill-id>/
  skill.json       # machine-readable metadata
  skill.md         # combined agent instructions + template (the install file)
  template.md      # page template only
  instructions.md  # agent instructions only
  README.md        # human description and usage tips
```

`skill.md` = `instructions.md` + `template.md` combined. It's the single URL users share with their AI to install the skill. Keep it in sync with the separate files.

### skill.json

```json
{
  "name": "Human-Readable Name",
  "id": "kebab-case-id",
  "version": "1.0.0",
  "description": "One-line description of what this skill covers",
  "domains": ["personal", "work"],
  "fields": ["field1", "field2", "field3"],
  "author": "Your Name or Handle",
  "license": "MIT"
}
```

- `id` must match the folder name exactly
- `domains` should use existing tags where possible: `personal`, `work`, `productivity`, `health`, `finance`, `food`, `learning`, `automotive`
- `fields` are the key frontmatter fields in the template (not an exhaustive list)

### template.md

Lead with YAML frontmatter. Every required field should be in frontmatter. Optional fields can live in the body. Add section headings that guide the user. Include brief inline comments (`<!-- like this -->`) where the purpose of a section isn't obvious.

### instructions.md

Write these for the AI agent that will work with pages using this template. Be concrete:

- What kinds of queries should the agent answer well?
- What patterns across pages are useful to surface?
- How should the agent handle missing or incomplete data?
- What output formats work best for this domain?

Keep instructions under ~400 words. Model-agnostic language only.

### README.md

- What is this skill for?
- Who is it for?
- How do you use it? (copy-paste flow)
- 2–3 example queries you can ask your agent once you have data

## Submission process

1. Fork this repo
2. Create your skill folder in `skills/<your-skill-id>/`
3. Add all four files
4. Open a pull request with:
   - PR title: `feat: add <skill-name> skill`
   - A brief description of the domain and why it's worth adding
5. A maintainer will review for completeness and quality

## Quality bar

PRs will be reviewed for:

- [ ] All four files present
- [ ] `skill.json` valid, `id` matches folder name
- [ ] Template has real frontmatter fields (not placeholder names)
- [ ] Template sections are useful, not just `## Section 1`
- [ ] Instructions are actionable and specific to the domain
- [ ] README explains use case and gives example queries
- [ ] No AI model names in instructions
- [ ] MIT license

## Questions

Open an issue. Label it `question`.
