# CLAUDE.md

Context for AI assistants (Claude, Cursor, Copilot, etc.) working in this
repository. Read this first before making changes.

## What this is

The public website for **Altivara Group Pte. Ltd.** trading as **Altivara
Global** — a Singapore-based business operations and consulting company
serving Southeast Asia and select global engagements.

## Tech stack

- Plain HTML5 + CSS3. No JavaScript framework, no build step, no package
  manager. Files are served as-is from a web root.
- Static assets only (PNG, SVG, ICO).

## Layout rules (important)

- **All HTML pages live at the repo root.** This keeps deployed URLs
  clean (`altivaraglobal.com/privacy.html`, not `/pages/privacy.html`).
- Asset paths in every HTML file are relative to the root:
  - CSS: `css/styles.css`
  - Logo: `assets/logos/altivara_logo.png`
  - Favicon: `assets/favicons/favicon.ico`
- Page-to-page links are bare filenames: `<a href="privacy.html">`.

When adding a new page, copy an existing one (e.g., `corporate.html`)
as the template so the header, footer, and path conventions stay
consistent.

## Content guidelines

- Tone: professional, restrained, consulting-firm voice. Avoid hype words
  ("revolutionary," "cutting-edge," "synergy").
- Geography: Singapore · Philippines · Asia-Pacific · select global.
- Contact email used throughout: `contact@altivaraglobal.com`.
- Three corporate pillars: **Altivara Group Pte. Ltd.** (entity),
  **Altivara Global** (market-facing brand), and **Capabilities**
  (Business Consulting, Operations, Workforce, Technology Enablement).

## Things not to do

- Don't introduce a build step, npm/yarn, or any JS framework without
  explicit approval. The site must remain copy-paste deployable.
- Don't inline base64 images into HTML — keep them in `assets/`.
- Don't add tracking, analytics, or third-party scripts without approval.
- Don't change `assets/` or `css/` directory names — every HTML file
  depends on them.
- Don't move HTML files into subdirectories without also updating asset
  paths to step up (`../assets/...`, `../css/...`) and adding redirects
  for the old URLs.

## Working notes

- `docs/` and `prompts/` are internal-only and may be excluded at deploy
  time. They are part of the repo for project history and AI context.
