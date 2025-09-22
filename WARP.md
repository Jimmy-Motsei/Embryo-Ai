# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

Repository overview
- Purpose: Static HTML presentation of the Embryo‑AI website audit, plus supporting summary pages.
- Stack: Pure HTML/CSS/vanilla JS. No package manager, no build system, no test or lint tooling configured.
- Key files:
  - index.html: Interactive 12‑slide deck with embedded styles and a small JS controller.
  - audit-summary.html, recommendations.html, client-responsibilities.html, next-steps.html: Static content pages with a shared top nav.
  - assets/maru-logo.png: Shared logo referenced by all pages.

Important note about README
- The README mentions Reveal.js, slides.md, and styles.css, but the current code does not include those files nor load Reveal.js. The deck is implemented directly in index.html with inline CSS and custom JS. Treat the repository as a self‑contained static site.

Common commands (macOS/zsh)
- Serve locally (recommended for navigation and hash routing):
  ```bash path=null start=null
  # From repo root
  python3 -m http.server 8000
  # then open in your browser
  open http://localhost:8000
  ```
- Alternative local server (Node present on your machine):
  ```bash path=null start=null
  npx serve . --listen 8000
  open http://localhost:8000
  ```
- Open a page directly without a server (works, but some features behave better with a server):
  ```bash path=null start=null
  open index.html
  ```
- Build/lint/test: Not applicable. There is no configured build, linter, or test framework in this repo.

How the code is structured (big picture)
- Navigation shell (all pages)
  - A fixed top navbar with links to: Presentation (index.html), Summary, Responsibilities, Recommendations, and Next Steps.
  - Shared asset: assets/maru-logo.png. If you change its path or name, update all HTML files that reference it.
  - The non‑deck pages import https://stackedit.io/style.css for typography and layout.
- Slide deck (index.html)
  - Slides are literal <section class="slide"> elements. The active slide is controlled by toggling the .active class.
  - JS controller (inline, at bottom of index.html):
    - Collects all elements with .slide into an array and tracks currentSlide.
    - Binds keyboard handlers (ArrowLeft/ArrowRight/Space) and click‑to‑advance on the slide area.
    - Updates a progress bar (#bar) and a simple counter (#count) on each slide change.
    - Supports hash navigation: changing location.hash to a number (e.g., #5) jumps to that slide.
  - CSS is embedded at the top of index.html and covers layout, typography, cards, progress bar, and responsive tweaks. There is no external stylesheet.

Working effectively in this repo
- Editing slides:
  - To add a slide, duplicate one of the existing <section class="slide"> blocks in index.html and adjust its content. The controller will pick it up automatically and the counter will update.
  - To deep‑link to a slide, navigate to index.html#N (1‑indexed).
- Keeping pages consistent:
  - The navbar and logo markup are duplicated across HTML pages. If you update structure or styles in one, mirror the change in the others.
- Network requirements:
  - index.html loads Google Fonts; the other pages load a stylesheet from stackedit.io. An internet connection is required for those assets unless you in‑line or vendor them.

Notes for future automation
- If you want linting/formatting or CI later, introduce them explicitly (e.g., Prettier/HTMLHint) and add the corresponding config files and scripts. Until then, do not assume any build, lint, or test commands exist.
