# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Hugo Blox Builder is a no-code website framework built on Hugo static site generator. It provides modular, widget-based website building with 750,000+ sites using it. The project uses a multi-module architecture with both Bootstrap and TailwindCSS UI options.

## Key Commands

### Development

```bash
# View a starter template locally (replace 'academic-cv' with starter name)
./scripts/view-starter.sh academic-cv

# View a starter template with local module replacements for development
./scripts/view-starter-dev.sh academic-cv

# Update Hugo modules for all starters
./scripts/update-starter.sh
# OR
hugo mod get -u ./...
```

### Linting and Formatting

```bash
# Run all linters
pnpm run lint

# Lint JavaScript files
pnpm run lint:js
pnpm run lint:js:fix  # Auto-fix

# Lint CSS/SCSS files (Tailwind module)
pnpm run lint:style
pnpm run lint:style:fix  # Auto-fix

# Format all code with Prettier
pnpm run format
```

### Building Assets

```bash
# Build Tailwind CSS (from blox-tailwind module)
cd modules/blox-tailwind
npm run build:styles

# Build Vite assets for Tailwind module
npm run assets:dist

# Copy libraries to assets
./scripts/copy_libraries.sh
```

## Architecture

### Module System

The project uses Hugo modules with the following core components:

- **blox-bootstrap**: Traditional Bootstrap-based UI (v5)
- **blox-tailwind**: Modern TailwindCSS-based UI with AlpineJS
- **blox-core**: Core functionality shared across UI modules
- **blox-seo**: SEO optimization features
- **blox-plugin-decap-cms**: CMS integration (formerly Netlify CMS)
- **blox-plugin-netlify**: Netlify deployment optimizations
- **blox-plugin-reveal**: Reveal.js slide presentations

Module dependencies flow: `starter -> UI module (bootstrap/tailwind) -> core/seo modules`

### Module Replacements for Development

When developing modules locally, use `HUGO_MODULE_REPLACEMENTS` environment variable to point to local modules instead of remote versions. The `view-starter-dev.sh` script handles this automatically.

### Starter Templates

Located in `/starters/` directory. Each starter is a complete Hugo site with:
- `config/_default/`: Hugo and module configuration
- `content/`: Markdown content organized by type
- `go.mod`: Hugo module dependencies
- `assets/`: Custom styles and media

### Widget System

Widgets are partial templates that can be composed to build pages. Located in module `layouts/partials/` directories. Pages use a `widget_page.html` layout that iterates through widget configurations.

### Asset Pipeline

- **Bootstrap module**: Uses traditional asset copying
- **Tailwind module**: Uses Vite for bundling with PostCSS/Tailwind processing
- JavaScript libraries (KaTeX, Mermaid, Plotly) are vendored and copied during build

### Theme System

Supports multiple color themes with automatic dark/light mode switching. Theme definitions in `data/themes/` use SCSS variables for Bootstrap or Tailwind utility classes.

## Important Notes

- Hugo requires v0.134.1+ with extended version for SCSS
- Node.js and pnpm/npm required for asset building
- When modifying Tailwind styles, rebuild CSS with `npm run build:styles`
- Local CMS backend enabled via `HUGOxPARAMSxCMSxLOCAL_BACKEND=true`
- Use `--panicOnWarning` flag during development to catch Hugo errors early