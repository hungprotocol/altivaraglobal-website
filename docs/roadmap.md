# Roadmap

Living document. Order is rough priority, not strict sequencing.

## Phase 1 — Foundation (current)

- [x] Reorganize repo: `assets/`, `css/`, `docs/`, `prompts/` folders
      with HTML pages at the root for clean URLs
- [ ] Verify all internal links resolve after migration
- [ ] Add `<meta>` description and Open Graph tags to every page
- [ ] Add a `sitemap.xml` and `robots.txt`

## Phase 2 — Content depth

- [ ] Expand the Services section on `index.html` with capability detail
- [ ] Add a dedicated `approach.html` or `methodology.html`
- [ ] Add a `contact.html` with a structured inquiry form (mailto for
      now; form backend TBD)
- [ ] Case study / engagement summaries (anonymized where required)

## Phase 3 — Polish

- [ ] Dark logo asset usage on dark sections (already in `assets/logos/`)
- [ ] Responsive QA across iPhone, iPad, common Android viewports
- [ ] Performance: confirm Lighthouse ≥ 95 across all four categories
- [ ] Accessibility: WCAG 2.1 AA pass on all pages

## Phase 4 — Discovery

- [ ] SEO plan execution (see `seo-plan.md`)
- [ ] Backlinks from corporate registries, industry directories
- [ ] LinkedIn company page alignment

## Out of scope (intentionally)

- Client portal, login, or any authenticated experience
- Blog / CMS — if needed later, evaluate static-site generators
  before introducing a database
