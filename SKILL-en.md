---
name: deck-lens
description: Use this skill to choose the right narrative lens for a presentation based on audience, context, and goal, then generate the matching slide structure, PPTX, or speech script. Triggers include "make me a slide deck", "prepare a pitch", "help me present X", "write a speech script", "build a presentation", "I need to present this". Also triggers when the user describes a product, feature, or project they want to present — even without saying "PPT". Always run this skill before generating any presentation content.
---

# Deck Lens

Deck Lens decides **how a presentation should be told** before producing anything. 

It is not a generic slide generator — it first picks the right narrative *lens* for the audience, context, and goal, then generates the matching structure, PPTX, or speech script.

The same project told through the wrong lens fails. A budget request told as a competition pitch feels like a performance; a competition pitch told as a government submission feels lifeless. Choosing the lens is the job.

---

## Step 1 — Read the Situation

Before anything else, understand **who** the deck is for and **why** it exists. Ask the user, or infer from what they've already said:

- **Audience** — Who is in the room? Investors, judges, clients, internal leadership, a government review panel, engineers?
- **Context** — What's the occasion? Competition, funding round, internal review, formal submission, technical handoff?
- **Goal** — What outcome do you want? Win, get funded, get approval, get sign-off, transfer knowledge?

If the user already made this clear, don't re-ask — move to Step 2.

---

## Step 2 — Recommend a Lens (auto-detect, then confirm)

Deck Lens has four lenses. Match the situation to one:

| Lens | Use for | Core logic |
|------|---------|------------|
| **Pitch** | Competition, fundraising, client demo, product launch | Win attention → feel the pain → solution → pricing → call to action |
| **Internal Report** | Leadership / management / cross-department reporting | Conclusion first, then evidence (pyramid principle) |
| **Government / Institution** | Government bodies, public institutions, regulators | Legitimacy → objective evidence → reliability → verifiable outcomes → risk control |
| **Technical Handoff** | Developers, architects, technical client stakeholders | Requirement discovery → design → logic → implementation → testing → delivery |

**Auto-detection signals:**
- "for leadership / management / report to my boss" → **Internal Report**
- "competition / judges / investors / clients / pitch" → **Pitch**
- "government / public institution / regulator / formal submission" → **Government / Institution**
- "technical lead / architecture review / handoff / developers" → **Technical Handoff**

**Always confirm before proceeding.** State your pick and the reasoning, then ask. Example:

> This looks like **Internal Report** mode — the audience is internal leadership, so they'll want the conclusion up front, then the supporting evidence. Shall I proceed with this lens?

Do not skip confirmation even when the signal is strong. The user may know something about the room that you don't.

**Hybrid situations:** If a deck genuinely spans two lenses (e.g. a technical pitch, or an internal report that also requests budget), pick **one primary lens** and borrow at most **one beat** from the other. Name the borrowed beat explicitly. Do not blend all four — a four-way hybrid has no shape.

---

## Step 3 — Ask for Output Format

Once the lens is confirmed:

> What output format do you need?
> 1. **PPTX file** — A ready-to-open slide deck
> 2. **Speech script** — A detailed written script for speaking or memorizing
> 3. **Both** — PPTX + matching speech script

---

## Step 4 — Gather Content

Ask the user to describe (skip any they've already provided):
1. **Topic** — What is this about?
2. **Pain points** — What problem does it solve? What's broken today?
3. **Solution** — What does your product, feature, or approach do?
4. **Key highlights** — The top 3–5 things the audience should remember
5. **Future value** — Any roadmap, potential, or scalability worth mentioning?

Default content depth is **non-technical** (no code, no architecture, no implementation detail) for every lens except Technical Handoff, which has its own depth rules.

---

## Step 5 — Generate

1. Load the confirmed lens file from `modes/` and follow its structure beat by beat.
2. **If PPTX or Both:** apply a design template. Default is `templates/design-default.md`. If the user has their own template, use theirs instead.
3. **If Speech script or Both:** write natural spoken language per section, with transition lines and estimated speaking time (~150 words/min).
4. **If Both:** generate the PPTX first, then derive the script from the slide content.
5. For PPTX generation, read `/mnt/skills/public/pptx/SKILL.md` first and follow its instructions.

---

## Lens Files
- `modes/pitch.md` — Pitch
- `modes/internal.md` — Internal Report
- `modes/government.md` — Government / Institution
- `modes/technical.md` — Technical Handoff

## Design Templates
- `templates/design-default.md` — Default lens (Royal Blue, bright background). Replaceable — copy it, change the values, and point the skill at the new file.

## Reference Example
- `examples/spectrum-analyzer.md` — A worked example using the Pitch lens.
