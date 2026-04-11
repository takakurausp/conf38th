# Project: Static Conference Site

## Build Commands

```bash
npm run build      # Build Tailwind CSS: src/input.css → docs/output.css
npm run watch      # Watch mode for development
```

**Important**: Always run `npm run build` after modifying `src/` files.

## Directory Structure

```
docs/              # Static site root (committed)
  ├── index.html   # Main page
  ├── output.css   # Built CSS (16KB, minified)
  ├── fonts/       # Self-hosted fonts (M PLUS 1p .woff2)
  └── images/
src/               # Tailwind sources (gitignored)
  ├── input.css    # Tailwind entry point
  └── fonts.css    # @font-face declarations
```

**Key**: `src/` is gitignored. Only `docs/` output is committed.

## Git Ignore Rules

Never commit: `node_modules`, `package-lock.json`, `src/`, `tailwind.config.js`, `.opencode/`

## Design Conventions

- **Typography**: Gothic body (M PLUS 1p web font) + Mincho headings (system fonts)
- **Responsive**: Font size 1.125rem on desktop (768px+), default on mobile
- **No external deps**: Tailwind CDN and Google Fonts are self-hosted

## HTML Conventions

- Use `eventListener` instead of inline `onclick`
- Include skip link for accessibility
- Tab panels need `role="tablist"`, `role="tab"`, `role="tabpanel"`, `aria-selected`, `aria-controls`
- All images need `alt` attributes

## Tailwind Config

- Content: `./docs/**/*.html`
- Plugins: forms, typography, aspect-ratio, line-clamp
- Font families: defined in `src/fonts.css` and inline HTML styles
