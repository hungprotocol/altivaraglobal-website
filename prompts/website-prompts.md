# Website Prompts

Reusable prompts for AI assistants working on this site. Paste into
Claude / Cursor / ChatGPT as needed.

---

## 1. Add a new page

> Create a new page at `<slug>.html` (at the repo root) that matches the
> structure, header, and footer of `corporate.html`. Use the standard
> asset paths: `css/styles.css`, `assets/favicons/favicon.ico`,
> `assets/logos/altivara_logo.png`. Page-to-page links should be bare
> filenames. The page content should cover: <topic>. Tone: professional,
> restrained consulting voice. Do not introduce JavaScript.

## 2. Update site-wide navigation

> The header `<nav>` and footer link list appear on every HTML file at
> the repo root. I want to add a link to `<new page>`. Update every
> file. Link paths are bare filenames (e.g., `<a href="new-page.html">`)
> because all HTML files live at the same level.

## 3. Refresh copy on an existing page

> Rewrite the body of `<file>` to <objective>. Keep the existing HTML
> structure, headings, and CSS classes. Do not change the navigation
> or footer. Match the tone of the rest of the site: precise,
> understated, no marketing hype.

## 4. SEO meta pass

> For `<file>`, write a `<title>` under 60 characters and a
> `<meta name="description">` under 160 characters that target the
> query "<query>". Also draft Open Graph tags (`og:title`,
> `og:description`, `og:url`, `og:image`) suitable for a corporate
> consulting site. The OG image will live at
> `assets/images/og-default.png`.

## 5. Accessibility review

> Audit `<file>` for WCAG 2.1 AA compliance. Check: heading hierarchy,
> alt text on images, color contrast (CSS variables are in
> `css/styles.css`), keyboard navigation, ARIA labels on the header
> nav, and form accessibility if any forms are present. Output a
> prioritized list of fixes.

---

## Tips for using these prompts

- Always paste the relevant existing file as context before issuing
  one of the prompts above. The AI cannot see the repo.
- For multi-file edits, ask for a unified diff or a list of changes
  per file — don't accept a wholesale "here's the new version" reply.
- After any AI-assisted change, verify links manually by opening
  `index.html` and clicking through every nav and footer link.
