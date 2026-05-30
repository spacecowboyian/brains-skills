# Contributing to brains-skills

## Skill structure

Every skill is one of two kinds, which sets its folder group:

- **hippocampus** — a whole-vault filing system that decides *where* pages go (PARA, Johnny.Decimal, …). Lives in `skills/hippocampus/<skill-id>/`.
- **lobe** — a note template for one record type that decides *what* a page contains (book-notes, recipes, …). Lives in `skills/lobes/<skill-id>/`.

A lobe never hardcodes a folder. It declares `file_type` + `filed_at` in its template and, at create time, asks the active hippocampus skill where to file each page (falling back to a flat `<skill-id>/` folder if none is active). Each hippocampus skill includes a "Routing notes from lobes" section describing how it answers that.

Every skill lives in `skills/<group>/<skill-id>/` with exactly five files:

```
skills/<group>/<skill-id>/      ← group is `hippocampus` or `lobes`
  skill.md          ← Required. Agent instructions + page template combined. This is the install file.
  skill.json        ← Required. Machine-readable manifest.
  template.md       ← Required. Page template only (standalone).
  instructions.md   ← Required. Agent instructions only (standalone).
  README.md         ← Required. Human docs: install prompt, capabilities, example queries.
```

`skill.md` is the primary artifact. It must contain both the agent instructions and the page template so a user can share one URL with their AI and have everything needed. Keep it in sync with `template.md` and `instructions.md`.

---

## File specs

### `skill.md`

Structure:

```markdown
# <Skill Name> Skill

**Skill ID:** <id>
**Version:** 1.0.0
**Domains:** <domains>
**Install:** fetch this file and follow the "How to use" section

## How to use

[One paragraph: what the AI should do after reading this file — set up project, create pages, offer first entry]

---

## Agent Instructions

[Contents of instructions.md]

---

## Page Template

[Fenced markdown block containing contents of template.md]
```

### `skill.json`

```json
{
  "name": "Human-Readable Name",
  "id": "kebab-case-id",
  "type": "lobe",
  "version": "1.0.0",
  "description": "One-line description",
  "domains": ["personal", "work"],
  "fields": ["field1", "field2"],
  "author": "Your Name or Handle",
  "license": "MIT"
}
```

- `id` must match the folder name exactly
- `type` must be `"hippocampus"` or `"lobe"`, and match the folder group (`skills/hippocampus/…` or `skills/lobes/…`)
- `domains`: use existing tags where possible — `personal`, `work`, `productivity`, `health`, `finance`, `food`, `learning`, `automotive`
- `fields`: key frontmatter fields in the template

### `template.md`

Lead with YAML frontmatter. Every required field in frontmatter. Section headings that guide the user. Brief inline comments (`<!-- like this -->`) where a section's purpose isn't obvious.

### `instructions.md`

Agent-facing instructions. Be concrete:
- What queries should the agent answer well?
- What cross-page patterns should it surface?
- How should it handle missing data?
- What output format works best?

Keep under ~400 words. No AI model names — these instructions must work with any LLM.

### `README.md`

Structure:

```markdown
# <Skill Name>

> One-line description.

## Install

[The one-URL install prompt, with the raw.githubusercontent.com URL]

## What this skill does

[Capabilities — what queries work, what the agent can do]

## Example queries

[3–5 concrete queries the user can try]

## Files

[Table of files in this skill folder]

## License

MIT
```

---

## Submission

1. Fork this repo
2. Decide the kind: a filing system (hippocampus) or a note template (lobe)
3. Create `skills/<group>/<your-skill-id>/` with all five files
4. Open a PR: title `feat: add <skill-name> skill`

### Review checklist

- [ ] All five files present
- [ ] `skill.md` contains both agent instructions and page template
- [ ] `skill.json` valid, `id` matches folder name, `type` matches folder group
- [ ] Lobe: no hardcoded folder path; declares `file_type` + `filed_at` and defers filing to the active hippocampus
- [ ] Hippocampus: includes a "Routing notes from lobes" section
- [ ] Template has real frontmatter fields (not placeholder names like `field1`)
- [ ] Template sections are specific to the domain (not generic `## Section 1`)
- [ ] Instructions are actionable and domain-specific
- [ ] README leads with the install prompt and includes example queries
- [ ] No AI model names in `skill.md` or `instructions.md`
- [ ] MIT license in `skill.json`

## Questions

Open an issue and label it `question`.
