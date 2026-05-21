# Design Template: Default (Royal Blue, Bright)

This is the **default design template** for Deck Lens. It applies only when generating a PPTX (or Both). Narrative/lens choice happens before this — design is the last layer.

To use a different look, copy this file, change the values below, and tell Deck Lens to use your file instead.

---

## Color Palette

| Role | Color | Hex |
|------|-------|-----|
| Slide background | White / very light | `#FFFFFF` |
| Primary accent | Royal Blue | `#4169E1` |
| Headings, accent blocks, dividers | Navy | `#003399` |
| Body text | Black | `#1A1A1A` |
| Highlight / premium touch | Gold | `#C9A84C` |

## Color Rules

- **Backgrounds stay bright.** Slide backgrounds are white or very light. This is a light theme, not a dark one. Navy is for title bars, accent blocks, section dividers, and sidebars — **never the dominant full-bleed background**. A single dark section-divider slide between major parts is fine; consecutive dark slides are not.
- **Max 3 colors per slide.**
- **Gold is sparing** — key callouts, milestone slide titles, or award/competition contexts only. If gold appears on every slide, it has stopped meaning anything.
- **No gradients with more than 2 of these colors.**
- **No other accent colors** — no red, green, purple, orange, teal, etc.

## Typography & Layout

- One idea per slide
- Headlines ≤ 10 words
- Bullet points ≤ 6 per slide, ≤ 12 words each
- Use icons or visuals instead of long text wherever possible
- Recommended fonts: **Inter** or **Helvetica** (English), **Source Han Sans / 思源黑体** (Chinese)
- Generous whitespace — a bright theme reads as clean only when it isn't crowded

---

## Making Your Own Template

1. Copy this file to `templates/design-<yourname>.md`
2. Change the palette, rules, and fonts to taste
3. Tell Deck Lens: "use the design template at templates/design-<yourname>.md"

The narrative structure (the lens) is unaffected by the design template — you can pair any template with any lens.
