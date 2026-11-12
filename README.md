# gladeadvisory-2024
Glade Advisory Group website — plain Hugo (no theme), five languages.

Standalone tools live in `static/traening/` (not localised; link them as `/traening/...` and `href.html` leaves the language prefix off).

| Language | URL | Content file |
|---|---|---|
| Dansk (default) | `/da/` | `content/_index.da.md` |
| English | `/en/` | `content/_index.en.md` |
| Deutsch | `/de/` | `content/_index.de.md` |
| Svenska | `/sv/` | `content/_index.sv.md` |
| Norsk bokmål | `/no/` (hreflang `nb`) | `content/_index.no.md` |

- **Edit text:** the content files above (front matter only; same structure in every language).
- **Edit layout:** `layouts/index.html`, styles in `assets/css/main.css`, UI strings in `i18n/`.
- **Contact email, CVR, x-default language:** `[params]` in `hugo.toml`.
- **Build locally:** `hugo server` (Hugo 0.169.0 extended, pinned in `netlify.toml`).
- **Deploy:** Netlify builds `main` with `--baseURL $URL`, so canonical URLs follow the primary domain set in Netlify.
