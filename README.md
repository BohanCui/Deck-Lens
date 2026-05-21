# Deck Lens

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

> 📖 中文版请见 [README-zh.md](./README-zh.md)

**Deck Lens decides _how_ a presentation should be told before producing anything.**

It is not a generic slide generator. It first picks the right narrative _lens_ for the audience, context, and goal — then generates the matching structure, PPTX, or speech script.

The same project told through the wrong lens fails. A budget request told as a competition pitch feels like a performance. A competition pitch told as a government submission feels lifeless. **Choosing the lens is the job.**

Deck Lens is a [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview).

---

## The Four Lenses

|Lens|Use for|Core logic|
|---|---|---|
|**Pitch**|Competition, fundraising, client demo, product launch|Win attention → feel the pain → solution → pricing → call to action|
|**Internal Report**|Leadership / management / cross-department reporting|Conclusion first, then evidence (pyramid principle)|
|**Government / Institution**|Government bodies, public institutions, regulators|Legitimacy → objective evidence → reliability → verifiable outcomes → risk control|
|**Technical Handoff**|Developers, architects, data scientists, researchers — any domain expert|Core principles + domain routing (software / data / hardware / research, or a general structure)|

Each lens is a separate file with its own beat-by-beat structure, slide-count guidance, and tone notes.

---

## How It Works

When triggered, Deck Lens runs five steps:

1. **Read the situation** — who is the deck for, and why does it exist?
2. **Recommend a lens** — auto-detects the best fit, then _always asks you to confirm_ before proceeding.
3. **Ask for output format** — PPTX, speech script, or both.
4. **Gather content** — topic, pain points, solution, highlights, future value.
5. **Generate** — builds the deck using the confirmed lens, applying a design template if a PPTX is requested.

Narrative comes first; design is the last layer.

---

## Repository Structure

```
Deck-Lens/
├── SKILL.md              # Main skill file (installable; English body, bilingual triggers)
├── SKILL-en.md           # Pure English version
├── SKILL-zh.md           # Pure Chinese version
├── modes/                # The four lenses (English + Chinese)
│   ├── pitch.md          / pitch-zh.md
│   ├── internal.md       / internal-zh.md
│   ├── government.md     / government-zh.md
│   └── technical.md      / technical-zh.md
├── templates/            # Replaceable design templates
│   └── design-default.md / design-default-zh.md

```

> **Note:** Only `SKILL.md` is read when the skill is installed. `SKILL-en.md` and `SKILL-zh.md` are human-readable language variants — to switch language, copy the one you want into `SKILL.md`.

---

## Design Templates

The look of the deck is separated from its narrative. The default template — `templates/design-default.md` — uses a Royal Blue palette on a **bright background** (white slides; navy reserved for titles, accent blocks, and dividers, never as a full-bleed background).

To use your own look:

1. Copy `templates/design-default.md` to `templates/design-<yourname>.md`
2. Change the palette, rules, and fonts
3. Tell Deck Lens to use your template

Any template pairs with any lens — the narrative structure is unaffected.

---

## Installation

Deck Lens is a Claude Skill. To use it:

1. Download or clone this repository
2. Add it to your Claude environment as a skill (see [Claude Skills documentation](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview))
3. Ask Claude to create a presentation, pitch, report, or speech script — Deck Lens triggers automatically


---

## Roadmap

### Near-term polish

- **Working examples are missing** — currently adding example folder and examples for all four lenses  since i belive these will be helpful and useful.

### Possible future additions

- **Additional lenses** — only if a real gap appears; a teaching/educational lens or a conference-talk lens are candidates, and also considering adding sub-lenses to the big ones
- **A visual lens-selection flowchart** in the docs, for people who want to pick a lens without running the skill
- **More design templates** — the default is a single Royal Blue / bright theme; presets such as a dark theme or a minimal academic theme could live alongside it
- **A hybrid worked example** — e.g. a technical pitch, to show in practice how borrowing one beat from a second lens works



## Contributions and suggestions are always welcomed!
Please open an issue or a pull request.

---

## License

This project is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) — free to share and adapt with attribution, but no commercial use.
