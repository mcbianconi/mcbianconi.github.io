# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A personal CV/resume website hosted on GitHub Pages. The site is plain static HTML + a single CSS file — **zero JavaScript, zero build step, zero runtime dependencies**. The previous MDwiki/Bootstrap/jQuery stack was removed in May 2026.

## File Layout

```
/index.html        Portuguese (pt-BR) CV, served at /
/en/index.html     English CV, served at /en/
/style.css         Single stylesheet, shared by both pages
/favicon.svg       Site favicon (inline SVG)
/avatar.jpg        Legacy profile photo (kept for old external links)
```

The two HTML pages have the same structural skeleton; only the visible text differs. When editing one language, mirror the structural changes in the other so the layout stays in sync.

## Design System

The visual is **neo-brutalism + solarpunk palette**:

- Background: cream `#FAF5E6`
- Primary text / forest green: `#1F3D2B`
- Accent yellow (sun): `#F4C430`
- Accent terracotta: `#C9542B`
- Borders / shadows: ink `#0B0B0B`
- Borders are always solid `3px solid #0B0B0B`; shadows are hard offsets (`6px 6px 0`) with no blur.
- No `border-radius` anywhere.
- Typography uses Google Fonts (Space Grotesk for display, JetBrains Mono for labels) with system fallbacks. The font `<link>` is the only external request the page makes.

All design tokens are CSS custom properties at the top of `style.css` — change them there to retheme the whole site.

## Editing Content

All CV content is inline in the two HTML files. Edit the matching `<section>` in both `index.html` and `en/index.html`. Keep:

- Sensitive contact info (phone, personal address, old email) out of the public site.
- The footer "last updated" string in sync between languages.

## Deployment

Pushing to the `main` branch automatically deploys via GitHub Pages. No CI pipeline, no build process — the files in the repo are exactly what gets served.

## Local Preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000 and http://localhost:8000/en/
```

Or open `index.html` directly in a browser via `file://` — works the same.
