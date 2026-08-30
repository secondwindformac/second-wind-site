# second-wind-site

Landing page for [Second Wind](https://github.com/secondwindformac/second-wind) —
"A second wind for your old Mac". Static site, GitHub Pages, no build step.

**Live:** https://secondwindformac.github.io/second-wind-site/ · Spanish: [`/es/`](https://secondwindformac.github.io/second-wind-site/es/)

## Structure

```
index.html        English (default language)
es/index.html     Spanish
styles.css        Shared styles (light + dark via prefers-color-scheme)
assets/           Screenshots (real E2E test run), favicon
```

## Adding a language

1. Copy `es/` to a new folder named by ISO code (`pt/`, `fr/`, …) and translate the strings.
2. Fix the two relative prefixes if depth changes (they won't for one level): `../styles.css`, `../assets/`.
3. Add the new `<link rel="alternate" hreflang="…">` to **every** page, and the new entry in each page's `.lang` selector.

## Buttons ↔ links.conf

Button URLs mirror `links.conf` in the main repo (marked with `<!-- from links.conf: KEY -->`
comments). When a real donate/support channel exists, update `links.conf` there and the
marked hrefs here in the same commit.

## Custom domain — secondwindformac.com (2-step activation)

The domain is chosen but activates only after purchase (Porkbun or Cloudflare, ~US$10/yr).
Doing it earlier would break the github.io URL. The day it's bought:

1. **DNS at the registrar**: `A` records for the apex → `185.199.108.153`,
   `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, and a `CNAME` for
   `www` → `secondwindformac.github.io`.
2. **This repo**: add a file named `CNAME` containing exactly `secondwindformac.com`,
   then in repo Settings → Pages set the custom domain and tick **Enforce HTTPS**
   (cert takes ~15 min). Finally replace `secondwindformac.github.io/second-wind-site`
   with `secondwindformac.com` in every `canonical`/`hreflang`/`og:` URL here, and
   point `WEBSITE_URL` in the main repo's `links.conf` at the new domain.

## License

Site code MIT. Screenshots are our own (from the project's validated end-to-end run).
Mac, macOS and MacBook are trademarks of Apple Inc.; Ubuntu is a trademark of Canonical Ltd.
Second Wind is an independent project, not affiliated with or endorsed by Apple or Canonical.
