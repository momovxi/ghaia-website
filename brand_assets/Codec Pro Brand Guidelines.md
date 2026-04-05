# Brand Guidelines — Codec Pro

---

## Brand Identity

**Brand Name:** Codec Pro  
**Tone:** Technical, modern, precise — built for professionals who value clarity and performance.  
**Aesthetic Direction:** Clean, bold, electric. Dark surfaces with vibrant accent colors that signal speed and intelligence.

---

## Typography

**Primary Font:** [Codec Pro](https://fonts.google.com/) *(or nearest match: `Space Mono`, `JetBrains Mono`, or a licensed Codec Pro typeface)*

### Usage
| Role | Font | Weight | Size (Base) |
|---|---|---|---|
| Display / Hero | Codec Pro | 800 (ExtraBold) | 56–96px |
| Headings (H1–H3) | Codec Pro | 700 (Bold) | 32–48px |
| Subheadings (H4–H6) | Codec Pro | 500 (Medium) | 20–28px |
| Body Copy | Codec Pro | 400 (Regular) | 16–18px |
| Labels / Captions | Codec Pro | 300 (Light) | 12–14px |
| Code / Monospace | `JetBrains Mono` | 400 | 14px |

### Rules
- **Never** use decorative or serif fonts — the brand is purely sans-serif.
- Letter-spacing on headings: `-0.02em` to `-0.04em` for a tight, modern feel.
- Line-height: `1.1–1.2` for headings, `1.6–1.7` for body.
- **All caps** permitted for labels and UI tags only.

---

## Color Palette

### Core Colors

| Name | Hex | Usage |
|---|---|---|
| **Background** | `#ffffff` | Main page background, cards, surfaces |
| **Electric Violet** | `#5800ff` | Primary CTA buttons, active states, key highlights |
| **Digital Blue** | `#009bdd` | Secondary accents, links, icons, hover states |
| **Cyan Spark** | `#04d7ff` | Tertiary highlights, gradients, glows, tags |

### CSS Variables
```css
:root {
  --color-bg:         #ffffff;
  --color-primary:    #5800ff;
  --color-secondary:  #009bdd;
  --color-accent:     #04d7ff;

  /* Derived tones */
  --color-primary-dark:    #3d00b3;
  --color-primary-light:   #8a4dff;
  --color-text:            #0a0a0a;
  --color-text-muted:      #5a5a72;
  --color-border:          #e0e0f0;
  --color-surface:         #f5f5ff;
}
```

### Color Roles
- **`#5800ff` Electric Violet** — The brand's signature. Use for primary buttons, active navigation, key icons, and bold section accents. Never dilute it — use sparingly for maximum impact.
- **`#009bdd` Digital Blue** — Supporting color. Works well for links, secondary buttons, feature icons, and informational UI elements.
- **`#04d7ff` Cyan Spark** — Energetic highlight. Use for tags, progress indicators, gradient endpoints, and glowing effects on dark surfaces.
- **`#ffffff` White** — The dominant surface. Keep large sections white to let the accent colors breathe and pop.

### Gradient
```css
/* Brand gradient (use sparingly for hero sections, CTAs, or dividers) */
--gradient-brand: linear-gradient(135deg, #5800ff 0%, #009bdd 60%, #04d7ff 100%);

/* Subtle background tint */
--gradient-surface: linear-gradient(180deg, #f5f5ff 0%, #ffffff 100%);
```

### Forbidden Combinations
- ❌ `#04d7ff` on `#ffffff` — insufficient contrast; use only on dark or colored backgrounds.
- ❌ All three accent colors used equally in one component — pick one as dominant.
- ❌ Warm-toned colors (orange, red, yellow) — not part of this palette.

---

## Spacing & Layout

### Spacing Scale (8px base grid)
```css
--space-1:   4px;
--space-2:   8px;
--space-3:   12px;
--space-4:   16px;
--space-5:   24px;
--space-6:   32px;
--space-7:   48px;
--space-8:   64px;
--space-9:   96px;
--space-10:  128px;
```

### Layout
- **Max content width:** `1280px`
- **Section padding (vertical):** `80px–128px`
- **Grid:** 12-column, `24px` gutters
- **Border radius:**
  - Buttons / Tags: `6px`
  - Cards: `12px`
  - Modals / Panels: `16px`
  - Pill badges: `999px`

---

## Components

### Buttons

```css
/* Primary */
background: var(--color-primary);   /* #5800ff */
color: #ffffff;
border-radius: 6px;
padding: 12px 24px;
font-weight: 600;
letter-spacing: 0.01em;
transition: background 0.2s ease;

/* Hover */
background: #3d00b3;

/* Secondary */
background: transparent;
border: 1.5px solid var(--color-primary);
color: var(--color-primary);

/* Ghost / Tertiary */
background: transparent;
color: var(--color-secondary);
text-decoration: underline;
```

### Cards
```css
background: #ffffff;
border: 1px solid var(--color-border);   /* #e0e0f0 */
border-radius: 12px;
box-shadow: 0 2px 16px rgba(88, 0, 255, 0.06);
padding: 32px;
```

### Accent Bar / Divider
```css
height: 3px;
background: var(--gradient-brand);
border-radius: 999px;
```

---

## Iconography

- Style: **Line icons**, 2px stroke weight, rounded caps.
- Size: `20px` (inline), `24px` (feature), `40px` (hero/section).
- Color: Match to context — use `--color-primary` for key actions, `--color-secondary` for supporting UI.
- Recommended libraries: [Phosphor Icons](https://phosphoricons.com/), [Lucide](https://lucide.dev/)

---

## Imagery & Illustration

- **Photography:** High-contrast, desaturated with a cool blue/violet tint overlay (`mix-blend-mode: multiply` with brand gradient).
- **Illustrations:** Flat geometric, vector-based. Accent colors only. No gradients inside illustrations unless intentional.
- **Avoid:** Stock photo clichés (handshakes, laptops on white backgrounds), warm color photography.

---

## Motion & Animation

- **Easing:** `cubic-bezier(0.16, 1, 0.3, 1)` — fast-in, smooth-out
- **Duration:** 
  - Micro-interactions (hover, click): `150–200ms`
  - Element reveals: `400–600ms`
  - Page transitions: `300ms`
- **Principles:** Purposeful only. Motion should communicate state changes, not decorate. Reduce motion for users who prefer it (`@media (prefers-reduced-motion)`).

---

## Accessibility

- Minimum contrast ratio: **4.5:1** for body text, **3:1** for large text/UI components.
- `#5800ff` on `#ffffff`: ✅ passes AA (ratio ~8:1)
- `#009bdd` on `#ffffff`: ✅ passes AA (ratio ~4.6:1)
- `#04d7ff` on `#ffffff`: ❌ fails — use on dark backgrounds only
- Focus states: Visible `2px` outline in `#5800ff` with `2px` offset.
- All interactive elements must have `:focus-visible` styles.

---

## Voice & Tone

| Context | Tone |
|---|---|
| Headlines | Bold, declarative, confident |
| Body copy | Clear, direct, no fluff |
| CTAs | Action-oriented: "Get started", "Build now", "Explore" |
| Error messages | Helpful, specific, never blame the user |
| Empty states | Encouraging, with a clear next action |

---

## Don'ts

- ❌ Don't use gradients on body text.
- ❌ Don't mix font families — Codec Pro only.
- ❌ Don't use more than 2 accent colors in a single UI section.
- ❌ Don't use pure black (`#000000`) — use `#0a0a0a` or `#111118` instead.
- ❌ Don't add drop shadows to text.
- ❌ Don't use `#04d7ff` on white backgrounds for text or small UI.

---

*Last updated: March 2026*
