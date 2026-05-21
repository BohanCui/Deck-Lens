---
name: presentation-builder
description: Use this skill whenever the user asks to create a PPT, presentation, slide deck, pitch, demo script, speech script, or any kind of reporting or presentation material. Triggers include: "make me a slide deck", "prepare a pitch", "help me present X", "write a speech script", "build a presentation", "I need to present this", "make slides for X". Also triggers when the user describes a product, feature, or project they want to present — even if they don't explicitly say "PPT" or "slides". Always use this skill before generating any presentation content.
---

# Presentation Builder Skill

A skill for building polished, persuasive presentations and presentation materials.

## Step 0 — Ask for Output Format

Before doing anything else, ask the user:

> What output format do you need?
> 1. **PPTX file** — A ready-to-open slide deck
> 2. **Speech script** — A detailed page-by-page written script for speaking or memorizing
> 3. **Both** — PPTX + matching speech script

Then proceed based on their answer.

---

## Step 1 — Clarify Audience & Tone

Ask (or infer from context):
- **Technical or non-technical audience?** Unless the user explicitly says the audience is technical (engineers, developers, etc.), default to **non-technical mode**: no implementation details, no code, no architecture diagrams. Focus on features, benefits, and impact.
- **Scene** — Competition pitch? Internal report? Client demo? Adjust formality accordingly.

---

## Step 2 — Gather Content

Ask the user to describe:
1. **Topic** — What is this about?
2. **Pain points** — What problem does it solve? What's broken today?
3. **Solution** — What does your product, feature, or approach do?
4. **Key highlights** — The top 3–5 things you want the audience to remember
5. **Future value** — Any roadmap, potential, or scalability worth mentioning?

If the user already provided this in their initial message, skip asking and proceed directly.

---

## Step 3 — Apply the 9-Beat Narrative Structure

All presentations follow this structure. Adapt the content to fit; do not skip beats.

| # | Beat | Purpose |
|---|------|---------|
| 1 | **Hook** | Open with a trend, stat, or observation that makes the audience lean in. ("In recent years, X has become increasingly…") |
| 2 | **Theme & Slogan** | State what this is about. Land a punchy tagline around innovation, practicality, or convenience. |
| 3 | **Pain Points** | Make the audience feel the problem. Be specific and relatable. Use numbers where possible. |
| 4 | **Status Quo Gap** | Show that existing approaches fall short. Adapt framing to context: competitor products (commercial), other teams or departments (internal), or industry-wide practices. If Beat 1 was too broad, weave in additional industry context here. Position your solution as the clear gap-filler. |
| 5 | **Our Approach** | Introduce your solution feature by feature. Order: most fundamental → most impressive. Lead with what the user gains, not how it was built (unless technical audience). |
| 6 | **Visual Demo** | Screenshots, photos, or demo footage. Show, don't just tell. |
| 7 | **Summary Map** | One slide that maps each pain point to your solution. The audience sees the complete picture at a glance. |
| 8 | **Future Value** | What's the potential? What's reserved for future development? Signal vision and scalability. |
| 9 | **Closing Slogan** | Echo Beat 2. End on the same energy you opened with. Leave them with the tagline. |

---

## Step 4 — Design Rules (Always Apply)

### Color Palette
Use **only** these colors. No exceptions unless the user explicitly overrides.

| Role | Color |
|------|-------|
| Primary accent | Royal Blue `#4169E1` |
| Deep background / headings | Navy `#003399` |
| Background / text on dark | White `#FFFFFF` |
| Body text | Black `#1A1A1A` |
| Highlight / premium touch | Gold `#C9A84C` *(use sparingly)* |

**Rules:**
- Max 3 colors per slide
- Gold only for key callouts, milestone slide titles, or award/competition contexts
- Never use gradients with more than 2 of these colors
- No random accent colors (no red, green, purple, orange, teal, etc.)

### Typography & Layout
- One idea per slide
- Headlines ≤ 10 words
- Bullet points ≤ 6 per slide, ≤ 12 words each
- Use icons or visuals instead of long text wherever possible
- Recommended font: **Inter** or **Helvetica**

### Content Depth (Default: Non-Technical)
- ✅ Feature names, user benefits, before/after comparisons, metrics
- ❌ Code snippets, API details, database schemas, implementation architecture
- If technical mode is requested, add a dedicated "Technical Deep Dive" section at the end — keep the main flow clean

---

## Step 5 — Generate Output

### If PPTX:
Read `/mnt/skills/public/pptx/SKILL.md` before generating. Follow all instructions there.
Structure slides according to the 9-beat narrative. Each beat = 1–2 slides max (except Visual Demo, which can expand).

### If Speech Script:
Generate a structured script with:
- **Slide title** for each section
- **Speaker notes** in natural spoken language (not bullet points)
- **Transition lines** between sections
- Estimated speaking time per section (assume ~150 words/min)

### If Both:
Generate PPTX first, then derive the speech script from the slide content.

---

## Reference Example

See `examples/spectrum-analyzer.md` for a fully worked example of this skill applied to a spectrum analyzer software enhancement competition pitch. Use it as a reference for tone, depth, and how to apply the 9-beat structure to a real product.
