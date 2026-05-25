# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A personal CV/resume website hosted on GitHub Pages using [MDwiki](https://github.com/Dynalon/mdwiki) (v0.6.2). MDwiki is a client-side JavaScript application that reads Markdown files and renders them as a styled HTML page — there is no build step, no package manager, and no server-side code.

## Content Files

All CV content lives in Markdown files:

- `index.md` — Portuguese (pt-br) version, served at `/`
- `en/index.md` — English version, served at `/en/`

**This is where all edits to the CV should be made.** Do not edit the HTML files to change content.

## How MDwiki Works

`index.html` (identical in both `/` and `/en/`) is the MDwiki runtime — a self-contained single-page app that:
1. Loads when the browser visits the root
2. Fetches and parses `index.md` from the same directory
3. Renders the Markdown as a Bootstrap-styled page

The `[gimmick:theme](cosmo)` directive at the top of each `.md` file sets the Bootstrap theme. The `[en]` / `[pt-br]` links between the two language versions are plain Markdown links.

## Configuration

`config.json` controls MDwiki behavior for the whole site:
- `useSideMenu` — enables a side navigation menu built from headings
- `additionalFooterText` — custom footer text
- `anchorCharacter` — character rendered next to anchor links

## Deployment

Pushing to the `main` branch automatically deploys via GitHub Pages. There is no CI pipeline or build process.

## Keeping Both Language Versions in Sync

`en/index.html` is a byte-for-byte copy of `index.html`. If `index.html` ever needs updating (e.g. a new MDwiki version), the copy in `en/` must be updated identically.
