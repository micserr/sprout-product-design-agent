# Bridge Layer & Dark Mode

## What the Bridge Is

The bridge layer maps primitive CSS vars to semantic meaning. It lives in `style.css` under:
```css
@layer base {
  :root { /* light mode values */ }
  .dark { /* dark mode overrides */ }
}
```

Light mode references primitives via `var()`. Dark mode overrides with direct hex/oklch values — no `var()` chaining.

## Enabling Dark Mode

Toggle the `.dark` class on `<html>`. CSS cascade handles everything.

```html
<!-- Light mode (default) -->
<html>...</html>

<!-- Dark mode -->
<html class="dark">...</html>
```

**Never use `@media (prefers-color-scheme: dark)`** — the system uses class-based toggling only.
**Never hardcode dark-mode hex values in component code** — tokens adapt automatically.

## Surface Token Light/Dark Values

These are the actual resolved values from the YAML source:

| Token | Light value | Dark value |
|---|---|---|
| `surface-white` | `#fff` | `#262b2b` (mushroom-950) — darkest layer |
| `surface-gray` | `mushroom-50` | `#394141` (mushroom-900) — main dark canvas |
| `surface` | `mushroom-50` (same as surface-gray) | `#394141` (mushroom-900) |
| `surface-adaptive` | `color-mix(in srgb, mushroom-950 6%, transparent)` — translucent overlay | `color-mix(in srgb, #eff1f1 6%, transparent)` — translucent white overlay |

### Key distinction

- `surface-white` in dark mode is `mushroom-950` (`#262b2b`) — the **darkest** layer, not white
- `surface-gray` / `surface` in dark mode is `mushroom-900` (`#394141`) — the main gray canvas
- `surface-adaptive` uses `color-mix` to create a translucent elevation overlay on any background

## How Other Tokens Adapt

All semantic families (brand, success, danger, etc.) and component-only tokens (text, border) have their own bridge mappings. The full values live in `style.css`. As a component author, you don't need to know the hex values — just use the semantic class and it adapts.

## Other Root Vars

These are defined in `:root` only (no dark override):

| Var | Purpose |
|---|---|
| `--page-gradient` | Background gradient for page canvas |
| `--font-heading` | Font family for headings |
| `--font-body` | Font family for body text |
