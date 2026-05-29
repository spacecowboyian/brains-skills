# Recipes skill

Build a personal recipe database that your AI agent can query for meal ideas, dietary filtering, and shopping list generation.

## Who it's for

Anyone who wants to organize their recipes in a personal knowledge base and use an AI assistant for meal planning.

## What you get

- **Template:** A recipe page with frontmatter (cuisine, meal type, prep/cook time, servings, dietary tags, rating) and sections for ingredients, instructions, notes, variations, and pairings
- **Instructions:** Agent guidance for recipe discovery, meal planning, shopping list generation, and recipe scaling

## How to install

1. Copy `template.md` into your Brains pages folder. Create one page per recipe.
2. Append `instructions.md` to your AI agent's instructions file.
3. Start adding recipes. After 15–20, the meal planning queries become genuinely useful.

## Example queries

- "What can I make for dinner tonight that's under 30 minutes?"
- "Plan meals for next week — no gluten, mostly vegetarian"
- "Generate a shopping list for Tuesday's dinner and Saturday's dinner"
- "What Italian recipes do I have?"
- "I want to make something similar to the Thai green curry — what else do I have?"
- "Scale the banana bread recipe for 16 servings instead of 8"

## Tips

- Fill in `dietary_tags` carefully — it's what makes filtering reliable
- Add a `rating` after you make the recipe, not when you add it
- The `notes` section is where recipes get better over time: what substitutions worked, what to skip
- Use `source` to credit the original cookbook or website
- `variations` is useful for "same technique, different protein" adaptations
