# Primitive Palettes

Primitives are CSS custom properties defined in `@theme {}` as `--color-{palette}-{shade}`.

**Rule: Never use primitives directly in component code.** They exist only in `style.css` to feed the bridge layer.

## Palettes

| Palette | CSS prefix | Shades | Intent |
|---|---|---|---|
| `white` | `--color-white` | default | Context-aware: light = `#fff`, dark = `mushroom-50`. Use `bg-surface-white` — not the primitive. |
| `neutral` | `--color-neutral` | 50–950 | Disabled states, overlays, on-fill text. **Do not use for primary UI** — use mushroom instead. |
| `mushroom` | `--color-mushroom` | 50–950 | Primary UI gray — surfaces, text, borders. Most-used palette. |
| `tomato` | `--color-tomato` | 50–950 | Danger / semantic red. |
| `carrot` | `--color-carrot` | 50–950 | Caution / warnings. |
| `mango` | `--color-mango` | 50–950 | Pending / in-progress. |
| `kangkong` | `--color-kangkong` | 50–950 | Brand / success (green). |
| `wintermelon` | `--color-wintermelon` | 50–950 | Accent (teal). |
| `blueberry` | `--color-blueberry` | 50–950 | Information. |
| `ubas` | `--color-ubas` | 50–950 | **Charts / data-viz only.** No semantic mapping — use directly (e.g. `bg-ubas-500`). The only palette where primitives are allowed in component code. |

## Shade Scale

All palettes except `white` follow this shade scale:
`50 · 100 · 200 · 300 · 400 · 500 · 600 · 700 · 800 · 900 · 950`

- **50** = lightest (near-white tint)
- **500** = mid-tone
- **950** = darkest (near-black shade)

## When Primitives Are Acceptable

Only two cases:

1. **`ubas` palette** — no semantic tokens exist for data-viz colors, so use primitives directly: `bg-ubas-400`, `bg-ubas-600`, etc.
2. **`style.css` bridge layer** — when defining CSS custom properties in `@layer base :root` or `.dark`.

In all other cases, use semantic tokens (see `color-tokens.md`).
