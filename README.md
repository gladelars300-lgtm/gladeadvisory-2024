# gladeadvisory-2024

Glade Advisory Group website — plain Hugo (no theme), 5 languages, deployed on Netlify.

## Languages and URLs

| Language | URL    | hreflang | Content file          | UI strings     |
|----------|--------|----------|-----------------------|----------------|
| English  | `/`    | `en` (+ `x-default`) | `content/_index.md`    | `i18n/en.toml` |
| Dansk    | `/da/` | `da`     | `content/_index.da.md` | `i18n/da.toml` |
| Deutsch  | `/de/` | `de`     | `content/_index.de.md` | `i18n/de.toml` |
| Svenska  | `/sv/` | `sv`     | `content/_index.sv.md` | `i18n/sv.toml` |
| Norsk    | `/no/` | `nb`     | `content/_index.no.md` | `i18n/no.toml` |

## SEO built in

- **canonical**: each language version points to itself (`layouts/partials/seo.html`).
- **hreflang**: every page lists all its translations + `x-default` → English.
- **sitemap**: `/sitemap.xml` is an index of per-language sitemaps with `xhtml:link` alternates.
- **robots.txt**: generated, points to the sitemap.
- **Structured data**: `ProfessionalService` + `WebSite` JSON-LD on the homepages.
- Per-language `<html lang>`, `<title>`, meta description, Open Graph locale, localized 404 pages.

## Adding a page

Create one file per language with the same name, e.g. `content/services.md`,
`content/services.da.md`, … Hugo links them as translations automatically
(hreflang and sitemap follow). For localized URLs set `slug` per file
(e.g. `slug = "ydelser"` in the Danish file) — keep the file names identical.

Write each language as its own page for that market (local terms, local
examples, local search phrases), not a literal translation.

## Before go-live

- If a custom domain is used, change `baseURL` in `hugo.toml`.
- Have a native speaker review the da/de/sv/no copy.

## Local preview

```
hugo server
```

Hugo version is pinned in `netlify.toml` (0.152.2).
