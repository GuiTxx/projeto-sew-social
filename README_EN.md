# SEW Social Project

English README — quick guide to understand, preview and contribute to this static project.

## Overview

This repository contains the static site for the "SEW Social" project. The structure prioritizes semantic HTML and modular CSS (one file per section). The project is a landing/mini-site with sections such as hero, courses, a showcase image grid, testimonials (feedbacks), sponsors, and more.

Technologies used
- HTML5
- Plain CSS (organized under `assets/css/sections/`)
- Static assets: images and icons

## How to preview locally

Quick options (Windows PowerShell):

1) Open `index.html` directly in your browser
- Fast for quick checks, but some features or relative paths are better tested via a local server.

2) Simple HTTP server with Python (recommended for correct relative paths):

```powershell
# from project root
python -m http.server 8000
# open http://localhost:8000 in your browser
```

3) Use VS Code Live Server extension
- Provides auto-reload and convenient development workflow.

## Repository structure (summary)

Root:
- `index.html` — main page
- `README.md` — Portuguese README
- `README_EN.md` — (this file)
- `assets/` — styles, scripts and placeholders
  - `css/` — CSS files
    - `variables.css` — global variables (colors, fonts)
    - `reset.css` — base reset
    - `style.css` — global project styles
    - `sections/` — section specific CSS (cards, courses, feedbacks, grid-mostruario, etc.)
  - `js/` — scripts (if present)
- `components/` — HTML partials/components
- `images/` — site images (banners, logos, icons)

Key section CSS examples:
- `assets/css/sections/grid-mostruario.css` — showcase image grid
- `assets/css/sections/feedbacks.css` — testimonial cards
- `assets/css/sections/cursos.css` — course cards
- `assets/css/sections/sponsor.css` — sponsor styles (renamed from `patrocinadores.css`)

## Conventions & style notes

- Global variables live in `variables.css` (use `var(--name)`).
- Include `reset.css` before `style.css` to ensure consistent base styles.
- Keep one CSS file per section for modularity and maintainability.
- Prefer relative units (`rem`, `clamp()`, `max-width`) for responsive sizing.
- For spacing in flex/grid, use `gap` and set container padding to `calc(gap / 2)` so outer spacing matches the inner gaps visually.

## Known issues & quick recommendations (observed in the codebase)

- Avoid using very large fixed `top` values for positioning (e.g. `top: 282rem`). Use `top: 50%` with `transform: translate(-50%, -50%)` and reserve space with `padding` or `min-height` instead.
- For rounded corners on elements using `background-image`, prefer using a `::before` pseudo-element with `background-image` and `border-radius: inherit` to prevent the background from overflowing the rounded corners.
- Use numeric `font-weight` (e.g. `700`) instead of `bolder` when requiring a reliable bold weight.
- Make sure `grid-template-columns` and `grid-template-areas` are consistent across breakpoints to avoid layout misalignment.

## How to contribute

1. Create a branch from `main`: `git checkout -b feat/my-change`
2. Make changes locally.
3. Preview the site locally and double-check responsive behavior.
4. Commit and push: `git commit -am "feat: short description"` and `git push origin feat/my-change`
5. Open a Pull Request describing your changes and motivation.

Commit message tips
- Use prefixes like `feat:`, `fix:`, `chore:`, `style:`.
- Keep commits small and focused for easier review.

## Quick checks and testing
- Test responsiveness in browser DevTools.
- Verify image paths (Network tab) if assets fail to load.
- Validate HTML/CSS to detect conflicting rules.

## Suggested next steps

- Centralize spacing variables (e.g. `--grid-gap`, `--container-padding`) in `variables.css`.
- Optimize images (webp, srcset) and add responsive image variants.
- Add linting (stylelint) and simple local checks.
- Improve accessibility: roles, ARIA attributes, contrast checks.

## Contact
- Author / Maintainer: Guilherme Teixeira (see git history)
