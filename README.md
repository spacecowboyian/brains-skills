# brains-skills

> A community library of domain-specific knowledge base skills for [Brains](https://usebrains.app).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Each skill is a self-contained folder: a `skill.md` you point your AI at, a page template to drop into your knowledge base, and a manifest. Five minutes from zero to a fully wired knowledge domain.

---

## Skills

| Skill | Description | `skill.md` |
|-------|-------------|------------|
| [book-notes](skills/book-notes/) | Capture and query book insights, quotes, and takeaways | [→ raw](https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/book-notes/skill.md) |
| [weekly-review](skills/weekly-review/) | Reflect on each week and synthesize into next actions | [→ raw](https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/weekly-review/skill.md) |
| [meeting-notes](skills/meeting-notes/) | Structured meeting records with decisions and action items | [→ raw](https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/meeting-notes/skill.md) |
| [project-tracker](skills/project-tracker/) | Track project status, blockers, risks, and team | [→ raw](https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/project-tracker/skill.md) |
| [recipes](skills/recipes/) | Personal recipe database with meal planning support | [→ raw](https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/recipes/skill.md) |

---

## Quick install

Paste into your AI chat — replace `<skill-id>` with the skill name:

```
Read https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/<skill-id>/skill.md
then set up a new project in my Brains knowledge base using this skill.
```

**Example — recipes:**

```
Read https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/recipes/skill.md
then set up a new project in my Brains knowledge base using this skill.
```

That's it. The `skill.md` file contains everything the AI needs: agent instructions and the page template.

> **Note:** Use the `raw.githubusercontent.com` URL, not the GitHub browse URL. Raw URLs fetch directly without search indexing or scraping.

---

## How it works

Each skill folder contains:

```
skills/<skill-id>/
  skill.md          ← The install file. Agent instructions + page template, combined.
  skill.json        ← Machine-readable manifest (name, version, fields, tags).
  template.md       ← Page template only (frontmatter + sections).
  instructions.md   ← Agent instructions only.
  README.md         ← Human docs, capabilities, example queries.
```

`skill.md` is the primary artifact. Share it with your AI and it knows how to set up the project, create pages, and answer queries in that domain.

`template.md` and `instructions.md` exist as standalone files for users who want to copy-paste them individually or use them outside a Brains workflow.

---

## Manual install (copy-paste)

If you'd rather not use the AI prompt:

1. Copy `template.md` from the skill folder into your Brains pages folder
2. Copy `instructions.md` into your AI's instructions file (e.g. `brainsapp-claude.md`)
3. Start creating pages using the template

No CLI, no build step.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the skill structure spec and submission process.

---

## License

[MIT](LICENSE)
