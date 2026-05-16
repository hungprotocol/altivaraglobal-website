# Architecture

Short by design. This is a static brochure site, not an application.

## Hosting model

Static files served from a standard web root. Current target:
`/var/www/altivaraglobal.com/`. No application server, no database, no
build step.

Deployment is `rsync` or `scp` of the repo contents to the web root.

## File layout reasoning

| Folder        | Purpose                                                    |
| ------------- | ---------------------------------------------------------- |
| `/`           | All HTML pages, kept at the root for clean public URLs     |
| `assets/`     | Binary brand assets, grouped by type                       |
| `css/`        | Single stylesheet for the entire site                      |
| `docs/`       | Internal planning — not deployed                           |
| `prompts/`    | AI prompts used during development — not deployed          |

## URL strategy

- `/` → `index.html`
- `/privacy.html`, `/terms.html`, `/data-protection.html`,
  `/corporate.html` — direct, clean paths.
- Optional later: server rewrite to drop the `.html` extension
  (`/privacy` → `/privacy.html`). Not required for launch, but
  trivial to add when desired.

## Why HTML at the root (not in `pages/`)

A `pages/` subdirectory is the standard convention for sites with
20+ pages that need grouping (`/pages/services/`, `/pages/case-studies/`).
At our current scale — five pages total — that structure costs
more in URL aesthetics than it pays back in organization. Keeping
pages at the root produces `altivaraglobal.com/privacy.html` instead
of `altivaraglobal.com/pages/privacy.html`, which reads as more polished
and avoids a future migration with 301 redirects.

If the page count grows substantially, revisit this — group by
domain (`/services/`, `/legal/`) rather than by a generic `/pages/`
bucket, and set up redirects from the old root URLs.

## Why no framework

Every consulting site this size that adopts React or Next.js ends up
spending more time on tooling than on content. The site is six pages
of static text and a logo. Plain HTML is the right tool until that
stops being true.

## When to revisit

Add structure when **at least two** of these become true:

1. Five or more pages share a header/footer that must update together
   (today: shared by copy-paste; tolerable at this scale).
2. Content needs to be authored by non-developers.
3. A blog or case-study index is added.
4. Localization (e.g., adding Bahasa or Mandarin) becomes a real
   requirement.

At that point, evaluate a static site generator (Astro, Eleventy, or
Hugo) before reaching for a JS framework.
