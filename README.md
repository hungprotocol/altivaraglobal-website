# altivaraglobal-website

Altivara Global website — the public-facing site for Altivara Group Pte. Ltd.

## Stack

Plain HTML, CSS, and static assets. No build step.

## Structure

```
altivaraglobal-website/
├── assets/
│   ├── logos/      # altivara_logo*.png/svg
│   ├── icons/      # altivara_logo_icon*.png/svg
│   ├── images/     # general site imagery
│   └── favicons/   # favicon.ico, favicon.svg
├── css/
│   └── styles.css
├── docs/           # internal planning docs (not deployed)
│   ├── roadmap.md
│   ├── architecture.md
│   └── seo-plan.md
├── prompts/        # AI prompts used to build/maintain the site
│   └── website-prompts.md
├── README.md
├── CLAUDE.md       # context for AI assistants working on this repo
├── index.html
├── corporate.html
├── privacy.html
├── terms.html
└── data-protection.html
```

HTML pages live at the root for clean URLs (`altivaraglobal.com/privacy.html`,
not `altivaraglobal.com/pages/privacy.html`). All asset references use
relative paths into `assets/` and `css/`.

## Local preview

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

Upload the contents of this repository to `/var/www/altivaraglobal.com/`,
overwriting the existing site files. Preserve the directory layout —
all internal paths assume it.

The `docs/` and `prompts/` directories are for internal use and can be
excluded from the deployed site if desired.

## Adding a new page

1. Copy `corporate.html` as a starting template (it has the standard
   header and footer).
2. Save the new file at the repo root: `new-page.html`.
3. Update the `<title>`, `<meta name="description">`, and page body.
4. Add a link to the new page in the header `<nav>` and footer link
   lists of every existing HTML file.

Keep new pages at the root unless and until you have enough pages to
justify a grouped folder (`/services/`, `/case-studies/`, `/legal/`).
At that point, move pages into the new folder, update their asset paths
to `../assets/...` and `../css/...`, and add 301 redirects from the old
URLs at the web server level.
