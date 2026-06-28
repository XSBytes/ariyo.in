# Personal Design Theme — Warm Minimal

> This file describes the visual design language used in my personal projects.
> When I share this file, apply this theme to whatever I am building — no need to ask about colors, fonts, or feel.

---

## Personality

Quiet, editorial, journal-like. The aesthetic is that of a well-worn notebook sitting on a wooden desk — warm, unhurried, and intentional. Nothing decorative that isn't also structural. No gradients, no drop shadows, no card borders. Space does the heavy lifting.

---

## Palette

| Role       | Value               | Usage                                              |
|------------|---------------------|----------------------------------------------------|
| Background | `#EDE8DF`           | Warm beige. The only background. No dark mode.     |
| Text       | `#1C1714`           | Warm near-black (not cool gray). All primary text. |
| Muted      | `#7A6F62`           | Labels, meta info, captions, footer.               |
| Divider    | `rgba(28,23,20,0.12)` | Hairline rules between sections.                 |
| Ghost      | `rgba(28,23,20,0.06)` | Decorative large background elements.            |
| Remark     | `rgba(28,23,20,0.65)` | Secondary body text, italicised descriptions.    |

**Rules:**
- Always dark ink on beige. Never white text on beige — it fails contrast.
- No pure black (`#000`), no pure white (`#FFF`) anywhere.
- No accent colors. The warmth of the beige and ink is the personality.

---

## Typography

### Typefaces
| Role          | Family                  | Google Fonts import                                                                 |
|---------------|-------------------------|-------------------------------------------------------------------------------------|
| Display       | `Cormorant Garamond`    | `family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300`                            |
| Body          | `Lora`                  | `family=Lora:ital,wght@0,400;0,500;1,400`                                          |

**Cormorant Garamond** is used for: titles, headings, ordinal labels, taglines, footer — anything with personality.  
**Lora** is used for: body copy, remarks, meta tags — anything meant to be read at length.

### Scale & Behaviour
- Titles: `clamp(3.8rem, 9vw, 7rem)`, weight 300, letter-spacing `0.18em`, uppercase
- Taglines: italic, weight 300, `clamp(0.95rem, 2vw, 1.2rem)`, letter-spacing `0.22em`, lowercase
- Section headings (h2): `clamp(1.65rem, 4vw, 2.3rem)`, weight 400, letter-spacing `0.01em`
- Body / remarks: `clamp(1rem, 2.2vw, 1.15rem)`, line-height `1.75`, italic, color `--remark`
- Labels / ordinals: `0.78rem`, letter-spacing `0.28em`, uppercase, color `--muted`
- Meta / dates: `0.78rem`, letter-spacing `0.2em`, uppercase, Lora, color `--muted`

**Rule:** Type is larger than you think you need. This is intentional — there is nothing else competing for space.

---

## Layout

- Single centered column. Max content width: `680px`. Auto margins.
- Generous vertical padding. Sections breathe — never cramped.
- Horizontal padding on body: `1.5rem` (mobile-safe).
- Dividers: `1px solid var(--divider)` — hairline only, no thick borders.
- No cards, no boxes, no backgrounds-within-backgrounds.
- Lists: no bullets. Items separated by divider lines.

---

## Signature Element

Each list item has a **ghost number** — the item's ordinal rendered at ~`11rem` in `Cormorant Garamond` weight 300, absolutely positioned to the right, color `rgba(28,23,20,0.07)`. On hover it lightens to `0.12` opacity. It gives depth without clutter and is the single decorative move in the entire design.

---

## Animation

All motion is **slow, subtle, and purposeful**. Nothing bounces, pops, or draws attention to itself.

| Animation     | Behaviour                                                                 |
|---------------|---------------------------------------------------------------------------|
| Page load     | Header fades + rises in: `opacity 0→1, translateY(20px→0)`, 1.2s, ease-out cubic-bezier(.22,.61,.36,1), 0.1s delay |
| Logo breathe  | Infinite slow opacity pulse: `1→0.72→1`, 6s ease-in-out, starts at 1.4s  |
| Scroll reveal | List items: `opacity 0→1, translateY(28px→0)`, 0.75s ease, triggered by IntersectionObserver at `threshold: 0.12`, staggered by `80ms` per item |
| Ghost hover   | `color` transition on `.ghost-num`: 0.4s ease                             |

**`prefers-reduced-motion` must be respected** — all animations disabled when set.

---

## Voice & Copy

- Lowercase where possible (taglines, footer). Feels personal, not corporate.
- Italic for anything reflective or explanatory — remarks, descriptions.
- Sparse punctuation. An em dash (`—`) instead of a colon for meta.
- Footer copy is poetic and brief, not utilitarian.

---

## What This Theme Is NOT

- Not a dark theme. Not adaptable to dark mode by default.
- Not colorful. Do not introduce accent colors.
- Not playful or rounded. No border-radius on anything meaningful.
- Not dense. Do not compress spacing to fit more content.
- Not loud. If an animation feels noticeable, it is too much.

---

## Quick CSS Variables Reference

```css
:root {
  --bg:      #EDE8DF;
  --text:    #1C1714;
  --muted:   #7A6F62;
  --ghost:   rgba(28,23,20,0.06);
  --divider: rgba(28,23,20,0.12);
  --num:     rgba(28,23,20,0.07);
  --remark:  rgba(28,23,20,0.65);
}
```

## Quick Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Lora:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet" />
```
