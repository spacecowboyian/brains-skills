# Recipes

> Personal recipe database with meal planning, dietary filtering, and shopping list generation.

## Install

Paste into your AI chat:

```
Read https://raw.githubusercontent.com/spacecowboyian/brains-skills/main/skills/lobes/recipes/skill.md
then set up a new project in my Brains knowledge base using this skill.
```

## What this skill does

Sets up a recipe knowledge base with a structured page template and an AI agent configured to work with it. Once you have pages, the agent can:

- Find recipes by cuisine, meal type, dietary tags, or prep time
- Plan meals for a week around your dietary constraints
- Generate consolidated shopping lists across multiple recipes
- Scale recipe quantities for different serving sizes
- Recommend what to make based on what's quick, what you haven't made recently, or similar dishes

## Example queries

- `What can I make for dinner under 30 minutes?`
- `Plan meals for next week — vegetarian, no gluten`
- `Generate a shopping list for Tuesday and Saturday dinners`
- `Scale the banana bread to 16 servings`
- `What Italian recipes do I have with a rating of 4 or higher?`

## Files

| File | Purpose |
|------|---------|
| [`skill.md`](skill.md) | Install file — agent instructions + template combined |
| [`skill.json`](skill.json) | Metadata manifest |
| [`template.md`](template.md) | Page template (standalone) |
| [`instructions.md`](instructions.md) | Agent instructions (standalone) |

## License

[MIT](../../LICENSE)
