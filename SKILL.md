---
name: presentation-builder
description: Use this skill whenever the user asks to create a PPT, presentation, slide deck, pitch, demo script, or any kind of reporting/汇报/演讲稿/presentation material. Triggers include: "帮我做个PPT", "帮我写汇报", "做个presentation", "写个演讲稿", "make me a slide deck", "prepare a pitch", "help me present X", "我要汇报", "比赛要交PPT". Also triggers when the user describes a product, feature, or project they want to present — even if they don't say "PPT" explicitly. Always use this skill before generating any presentation content.
---

# Presentation Builder Skill

A skill for building polished, persuasive presentations and presentation materials.

## Step 0 — Ask for Output Format

Before doing anything else, ask the user:

> 你需要哪种输出格式？/ What output format do you need?
> 1. **PPTX 文件** — 可直接打开的幻灯片文件
> 2. **演讲稿** — 详细的逐页文字稿，适合背稿或朗读
> 3. **两者都要** — PPTX + 配套演讲稿

Then proceed based on their answer.

---

## Step 1 — Clarify Audience & Tone

Ask (or infer from context):
- **技术受众还是非技术受众？** Unless the user explicitly says the audience is technical (engineers, developers, etc.), default to **non-technical mode**: no implementation details, no code, no architecture diagrams. Focus on features, benefits, and impact.
- **语言** — Chinese, English, or bilingual? Default to the language the user is writing in.
- **场景** — Competition pitch? Internal report? Client demo? Adjust formality accordingly.

---

## Step 2 — Gather Content

Ask the user to describe:
1. **主题 / Topic** — What is this about?
2. **痛点 / Pain points** — What problem does it solve? What's broken today?
3. **解决方案 / Solution** — What does your product/feature/approach do?
4. **亮点 / Key highlights** — Top 3–5 things you want the audience to remember
5. **延伸价值 / Future value** — Any roadmap, potential, or scalability to mention?

If the user already gave this in their initial message, skip asking and proceed directly.

---

## Step 3 — Apply the Narrative Structure

All presentations follow this 9-beat structure. Adapt the content to fit; do not skip beats.

| # | Beat | Purpose |
|---|------|---------|
| 1 | **引入 / Hook** | Open with a trend, stat, or observation that makes the audience lean in. ("近年来…越来越…") |
| 2 | **主题 + 口号 / Theme & Slogan** | State what this is about. Land a punchy tagline: innovation, practicality, convenience. |
| 3 | **痛点 / Pain Points** | Make the audience feel the problem. Be specific and relatable. Use numbers if possible. |
| 4 | **现状对比 / Status Quo Gap** | Show that existing approaches fall short. Adapt the framing to context: competitor products (commercial), other teams/departments (internal), or industry-wide practices. If Beat 1 was too broad or didn't fully land the industry backdrop, weave in additional context here. Position your solution as the clear gap-filler. |
| 5 | **我司做法 / Our Approach** | Introduce your solution feature by feature. Order: most fundamental → most impressive. Keep it benefit-led, not implementation-led (unless technical audience). |
| 6 | **直观展示 / Visual Demo** | Screenshots, photos, or live demo. Show, don't just tell. |
| 7 | **总结对应图 / Summary Map** | One slide that maps each pain point → your solution. Audience sees the complete picture. |
| 8 | **上价值 / Future Value** | What's the potential? What's reserved for future? Signals vision and scalability. |
| 9 | **回归主题 / Closing Slogan** | Echo beat 2. End on the same energy you opened with. Leave them with the tagline. |

---

## Step 4 — Design Rules (Always Apply)

### Color Palette
Use **only** these colors. No exceptions unless the user explicitly overrides.

| Role | Color |
|------|-------|
| Primary accent | 宝蓝色 Royal Blue `#4169E1` |
| Deep background / headings | 深蓝色 Navy `#003399` |
| Background / text on dark | 白色 White `#FFFFFF` |
| Body text | 黑色 Black `#1A1A1A` |
| Highlight / premium touch | 金色 Gold `#C9A84C` *(use sparingly)* |

**Rules:**
- Max 3 colors per slide
- Gold only for key callouts, titles of milestone slides, or award-context presentations
- Never use gradients with more than 2 of these colors
- No random accent colors (no red, green, purple, orange, teal, etc.)

### Typography & Layout
- One idea per slide
- Headlines ≤ 10 words
- Bullet points ≤ 6 per slide, ≤ 12 words each
- Use icons or visuals instead of long text wherever possible
- Consistent font: suggest **思源黑体 / Source Han Sans** (Chinese) or **Inter / Helvetica** (English)

### Content Depth (Default: Non-Technical)
- ✅ Feature names, user benefits, before/after comparisons, metrics
- ❌ Code snippets, API details, database schemas, implementation architecture
- If technical mode is requested, add a dedicated "Technical Deep Dive" section at the end, keeping the main flow clean

---

## Step 5 — Generate Output

### If PPTX:
Read `/mnt/skills/public/pptx/SKILL.md` before generating. Follow all instructions there.
Structure slides according to the 9-beat narrative. Each beat = 1–2 slides max (except Visual Demo, which can expand).

### If 演讲稿 (Speech Script):
Generate a structured script with:
- **Slide title** for each section
- **Speaker notes** in natural spoken language (not bullet points)
- **Transition lines** between sections
- Match the language the user requested (Chinese / English / bilingual)
- Estimated speaking time per section (assume ~120 words/min Chinese, ~150 words/min English)

### If Both:
Generate PPTX first, then derive the speech script from the slide content.

---

## Reference Example

See `examples/spectrum-analyzer.md` for a fully worked example of this skill applied to a spectrum analyzer software enhancement pitch. Use it as a reference for tone, depth, and how to apply the 9-beat structure to a real product.
