# AGENTS.md — Lycée Oued Elma Website

## Project overview

Static Arabic/RTL school website. Single page (`index.html` + `style.css`) with inline JS. No build system, no package manager, no tests.

## Commands

No build, dev-server, or test commands exist. The site is pure HTML/CSS/JS — serve with any static file server:

```bash
npx serve .
# or
python3 -m http.server
```

## Key facts

- **RTL** — `<html lang="ar" dir="rtl">`. All layout is right-to-left. Do not flip it.
- **Fonts** — Cairo font is **self-hosted** in `assets/fonts/Cairo/` (loaded via `@font-face`). The Google Fonts CDN links in `index.html` are commented out; do not re-enable them without reason.
- **CSS variables** — Full design token system in `:root` (`style.css:1-73`). Colors, spacing, radius, shadows, transitions. Use these variables rather than hardcoded values.
- **JS** — Vanilla inline `index.html:500-537`. Scroll-based back-to-top button + IntersectionObserver for fade-in animations. No frameworks.
- **No external dependencies** — Zero npm packages, no bundler, no preprocessor.
- **Skills available** — `.agents/skills/designing-beautiful-websites/` (UI design skill) and `.github/skills/premium-frontend-ui/` (GitHub Copilot frontend skill). Use these when asked to improve visuals.
- **`instruct-177.md`** — A school counseling report document, not code. Do not edit unless specifically asked.

## Style conventions

- Utility classes: `.layout-flex`, `.gap1`, `.gap1_5`, `.no-wrap`, `.align-center`, `.content-justify_space-between`
- Section pattern: `<section id="..."><div class="container"><div class="section-header">...</div>...</div></section>`
- Hover animations use `translateY(-Npx)` + shadow elevation consistently
- Responsive breakpoints: 1024px, 768px, 480px
