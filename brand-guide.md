# Brand Guide

A set of design principles and defaults for clean, simple interfaces.

---

## Philosophy

Prefer restraint over decoration. Every visual element should either aid comprehension or get out of the way. When in doubt, remove rather than add.

---

## Typography

**Serif body text** for long-form reading. Lora is the current default — warm, literary, and designed for sustained reading on screen.

```
font-family: 'Lora', Georgia, serif;
```

Load via Google Fonts:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet">
```

Alternatives in the same spirit: EB Garamond, Merriweather, Playfair Display.

---

## Color

Keep the palette minimal. Avoid strong accent colors in navigation and UI chrome — gray communicates structure without competing with content.

| Role              | Value   | Notes                          |
|-------------------|---------|--------------------------------|
| Body text         | `#222`  | Near-black, softer than pure black |
| Secondary / muted | `#888`  | Subtitles, metadata            |
| UI links (rest)   | `#555`  | Navigation, TOC                |
| UI links (hover)  | `#222`  | Pulls toward body text         |
| Disabled / coming | `#aaa`  | Placeholder items              |

Reserve blue (or any hue) for inline content links where it aids scanning — not for structural chrome.

---

## Layout

- Center content as a unit; align text within it to the left.
- Use whitespace generously — padding and breathing room signal confidence.
- Hide structural UI (sidebars, menus) on landing/cover pages where they distract from the first impression.
- Cap content width around 640px for comfortable line lengths.

---

## Voice (for titles and subtitles)

- Titles: direct and concrete — say what the thing *is*
- Subtitles: one plain sentence that earns the reader's next click

*Example:* "Computing from the Ground Up" / "How a wire became a computer"

---

## What to avoid

- Decorative borders, shadows, or gradients unless they solve a specific problem
- Multiple font families — one serif handles most cases
- Saturated accent colors in navigation or chrome
- Bullet points and headers in prose — write in sentences
