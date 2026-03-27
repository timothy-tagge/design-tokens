# design-tokens

Shared CSS design tokens consumed by all Tagge apps.
Install in an app with: `npm install github:timothy-tagge/design-tokens`
Import as the first line of `main.jsx`: `import "design-tokens/tokens.css"`

## What lives here
- `tokens.css` — All CSS custom properties (design tokens) + dark mode overrides + global resets

## What does NOT live here
- React components (each app owns its own components)
- App-specific business logic
- Firebase config

## Dark mode
Automatic via `@media (prefers-color-scheme: dark)`. No JS required.
Surfaces, borders, and text flip automatically.
Green palette lightens for readability on dark backgrounds.
Buttons use `--btn-primary-bg` / `--btn-primary-text` semantic tokens — use these
on all primary CTAs so dark mode renders correctly without additional overrides.

## Updating tokens
1. Edit `tokens.css`
2. `git commit -m "describe change"` + `git push`
3. In each app: `npm update design-tokens && npm run build && firebase deploy`

## Token naming conventions
- Surface tokens: `--bg`, `--surface`, `--surface-2`
- Border tokens: `--border`, `--border-strong`
- Text tokens: `--text`, `--text-2`, `--text-muted`
- Color palette: `--green-*`, `--amber-*`, `--red-*`, `--blue-*`, `--purple-*`
- Semantic (prefer these in components): `--btn-primary-bg`, `--btn-primary-text`
- Layout: `--radius-*`, `--shadow-*`
- Fonts: `--font-ui`, `--font-display`, `--font-mono`
