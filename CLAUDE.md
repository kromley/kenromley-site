# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Static personal site for Ken Romley (kenromley.com) — Fractional Chief AI Officer & AI advisor based in Raleigh–Durham. **No build step.** Everything in `public/` is deployed directly.

## Deploy

```bash
firebase deploy
```

Requires `firebase-tools` CLI and an authenticated session (`firebase login`). The Firebase project is `kenromley-site` (set in `.firebaserc`).

## Architecture

The entire site is a single file: `public/index.html`. All CSS is inline in `<style>` tags in the `<head>`; there is no external stylesheet, no JavaScript framework, and no bundler.

`public/` contents:
- `index.html` — the full site (HTML + CSS + structured data)
- `ken-romley.jpg` — headshot referenced in the page and in the JSON-LD schema
- `llms.txt` — plain-text summary for AI assistants
- `sitemap.xml` — for search crawlers
- `robots.txt` — opens the site to search and AI crawlers; references the sitemap
- `favicon.ico`

## Key content conventions

- **Structured data** lives in three `<script type="application/ld+json">` blocks in `<head>`: a `Person` schema, a `ProfessionalService` schema, and a `FAQPage` schema. Keep these in sync with visible page content.
- **`llms.txt`** is a parallel summary for AI assistants — update it whenever biographical facts, services, or pricing change in `index.html`.
- **`sitemap.xml`** should be updated if the canonical URL or significant page sections change.
- CSS custom properties (`--ink`, `--paper`, `--accent`, etc.) are declared in `:root` and used throughout — change colors there, not inline.
- The design uses two Google Fonts: Space Grotesk (display/UI) and Newsreader (body copy). Font stacks fall back gracefully.
