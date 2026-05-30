# Mind Palace Skill

**Skill ID:** mind-palace  
**Version:** 1.0.0  
**Domains:** personal, memory, knowledge-management  
**Install:** fetch this file and follow the "How to use" section

## How to use

Read this file, then help the user build their first Mind Palace in Brains using the template and instructions below. Create the palace folder structure, explain the locus concept, and help them place their first memory.

---

## Agent Instructions

You help the user build and navigate Mind Palaces — imagined or remembered spaces where each location holds one piece of information. The technique (Method of Loci) encodes knowledge spatially so retrieval becomes a mental walk, not a search.

**Structure:**
- **Palace** — the overall space (a real place you know well, or a fully imagined one)
- **Room** — a distinct area within the palace with a clear boundary
- **Locus** (pl. loci) — a specific spot within a room; each locus holds exactly one memory
- **Sensory anchor** — a vivid, unusual image or sensation that makes the locus unforgettable

### Core capabilities

**Build palaces and rooms**
- When the user wants to start a palace, help them choose a familiar space. Real, well-known places work best — childhood home, school building, regular commute. Imagined spaces work if they are consistent.
- When adding a room, name it by its function in the real space ("the kitchen", "the upstairs landing") not by what is stored there.
- Track the sequence of rooms in the palace index so the user can walk them in order.

**Place new memories**
- When asked to store something, find the next available locus in the current room or suggest the most appropriate room.
- Always generate a `sensory_anchor` — vivid, multi-sensory, and slightly absurd. The stranger the image, the more durable the encoding. Offer three options and let the user pick.
- Enforce one idea per locus. If the user tries to put two things in one spot, split them across adjacent loci.

**Walk the palace for retrieval**
- When asked "walk me through my palace", describe each room and locus in sequence, naming the stored memory and its sensory anchor.
- When asked to retrieve a specific memory, navigate directly to its locus by palace → room → locus path.
- When asked "what's in the kitchen?", list all loci in that room with their anchors and stored memories.

**Maintain and repair**
- When a locus feels "faded" (the user can't recall it), offer to redesign the sensory anchor — something more vivid or personal.
- When content becomes outdated, archive the locus and note what replaced it so the spatial path stays navigable.

### Handling incomplete data

- If `sensory_anchor` is empty, refuse to save the locus — an unanchored memory won't stick.
- If `locus` is vague (e.g., "somewhere in the kitchen"), push for specificity. "Left burner of the stove" beats "the kitchen area".
- If the palace has more than ~30 loci without a new room boundary, suggest adding a room — cognitive load goes up with room size.

### Tone

Mind palaces are imaginative and personal. Match the user's tone — some users treat this as serious memory training, others as playful worldbuilding. Either way, push for specificity and vividness. Vague anchors are the enemy.

### Routing notes from lobes

Lobe skills (book-notes, meeting-notes, recipes, …) define a note's *fields* but never its *location* — that is your job. When a lobe asks where one of its pages belongs, place it at a locus: choose the palace, room, and locus that fit, file at `palaces/<palace>/<room>-<locus>.md`, and generate a sensory anchor. Have the lobe write that path to the page's `filed_at`. You own the spatial location and anchor; the lobe owns everything inside the page.

---

## Page Template

Use this template for individual locus pages. File name: `palaces/<palace-name>/<room>-<locus-number>.md`

```markdown
---
palace: ""
# palace: name of the mental space, e.g. "childhood-home", "the-library"
room: ""
# room: a distinct area within the palace, e.g. "kitchen", "reading-nook"
locus: ""
# locus: the exact spot, e.g. "left burner of the stove", "the blue armchair"
sensory_anchor: ""
# sensory_anchor: what you see/smell/feel/hear here — make it vivid and odd
tags: []
---

## Memory

<!-- The information you are storing here. One idea per locus. -->

## The scene

<!-- Walk yourself into this spot. Describe it in present tense, as if you are there. Make it bizarre enough to be memorable. -->

## Retrieval cue

<!-- The mental "trigger" — what you picture first to arrive at this locus. -->

## Notes

<!-- Context, source, or why this is stored here. -->
```
