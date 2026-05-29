# brains-skills

A community library of domain-specific knowledge base skills for [Brains](https://brainsapp.com). Each skill is a folder with a template, agent instructions, and a manifest — everything you need to start collecting and querying knowledge in a specific domain.

## What is a skill?

A skill is a self-contained unit for a knowledge domain. It includes:

- **`skill.json`** — machine-readable metadata (name, version, fields, tags)
- **`template.md`** — a ready-to-use page template with frontmatter and sections
- **`instructions.md`** — agent instructions that tell your AI how to work with this type of page
- **`README.md`** — human-readable description, use cases, and tips

## Available skills

| Skill | Description |
|-------|-------------|
| [book-notes](skills/book-notes/) | Capture and query book insights, quotes, and takeaways |
| [weekly-review](skills/weekly-review/) | Reflect on each week and synthesize into next actions |
| [meeting-notes](skills/meeting-notes/) | Structured meeting records with decisions and action items |
| [project-tracker](skills/project-tracker/) | Track project objectives, status, team, and risks |
| [recipes](skills/recipes/) | Build a personal recipe database with meal planning support |

## How to install a skill

### Copy-paste (recommended for now)

1. Browse to the skill folder you want (e.g. `skills/book-notes/`)
2. Copy `template.md` into your Brains pages folder as a new page type
3. Copy `instructions.md` into your Brains instructions (typically `brainsapp-claude.md` or equivalent)
4. Start creating pages using the template

That's it. No CLI, no build step.

### What to do with `skill.json`

`skill.json` is metadata for tooling. You don't need it to use a skill today — it's used by future CLI and gallery features.

## Structure

```
skills/
  <skill-id>/
    skill.json         # metadata
    template.md        # page template (copy this into your brain)
    instructions.md    # agent instructions (append to your AI instructions)
    README.md          # description and usage tips
```

## Contributing

Want to add a skill? See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT
