# Circular Progress Bar

A lightweight, neumorphic-styled circular progress bar built with pure HTML, CSS, and JavaScript. No libraries, no dependencies.

---

## Preview

- Animated SVG ring with a pink-to-purple gradient stroke
- Neumorphic soft-UI design (extruded outer shell + inset inner core)
- Live counter ticking up to the target percentage
- Replay and Reset controls

---

## Project Structure

```
project/
├── index.html
└── style.css
```

---

## Getting Started

No build tools or installs needed.

1. Clone or download the project folder
2. Open `index.html` in any modern browser

```bash
git clone https://github.com/your-username/circular-progress-bar.git
cd circular-progress-bar
open index.html
```

---

## How It Works

### SVG Ring

The progress ring is drawn using an SVG `<circle>` element. Animation is handled by manipulating `stroke-dashoffset`:

- `stroke-dasharray: 515` — full circumference of the circle (`2 * π * r ≈ 2 * 3.14 * 82`)
- `stroke-dashoffset` starts at `515` (empty) and decreases as the counter climbs
- A faint gray circle underneath acts as the background track

### Counter

A `setInterval` ticks every `30ms`, incrementing the count by 1 until it hits the target value. Each tick updates both the displayed number and the ring offset.

### Neumorphic Effect

Achieved purely with layered `box-shadow`:

- **Outer shell** — soft raised shadow (light top-left, dark bottom-right)
- **Inner core** — inset shadow to create a pressed-in recess
- **Buttons** — same raised shadow, inverts to inset on `:active`

---

## Customization

| What            | Where in code                        | How                                      |
|-----------------|--------------------------------------|------------------------------------------|
| Target value    | `const TARGET = 65`                 | Change `65` to any number up to `100`   |
| Speed           | `setInterval(..., 30)`              | Lower = faster, higher = slower          |
| Gradient colors | `stop-color` in `<linearGradient>`  | Replace hex values with any color        |
| Ring thickness  | `stroke-width="10"` on SVG circle   | Increase for a thicker ring              |
| Skill label     | `<p class="skill-name">javascript</p>` | Replace text with your skill name     |

---

## Browser Support

Works in all modern browsers. No polyfills required.

| Browser | Support |
|---------|---------|
| Chrome  | ✓       |
| Firefox | ✓       |
| Safari  | ✓       |
| Edge    | ✓       |

---

## Fonts Used

Loaded via Google Fonts — requires an internet connection on first load.

- [Syne](https://fonts.google.com/specimen/Syne) — percentage number
- [DM Mono](https://fonts.google.com/specimen/DM+Mono) — labels and buttons

---

## License

MIT — free to use, modify, and distribute.