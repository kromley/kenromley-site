# kenromley.com

Static personal site for Ken Romley — Fractional Chief AI Officer & AI advisor.

## Structure
- `public/` — the deployed site
  - `index.html` — the page
  - `ken-romley.jpg` — headshot (referenced by the page and the schema)
  - `robots.txt` — opens the site to search and AI crawlers; points to the sitemap
  - `sitemap.xml`
  - `llms.txt` — structured summary for AI assistants
- `firebase.json` — Firebase Hosting config (serves the `public/` folder)

## Deploy (Firebase Hosting)
1. Install the CLI: `npm install -g firebase-tools`
2. `firebase login`
3. Link a Firebase project: `firebase use --add`
4. `firebase deploy`

The site is plain static HTML/CSS — no build step.
