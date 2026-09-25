# second-wind-site

Landing page for [Second Wind](https://github.com/secondwindformac/second-wind):
"A second wind for your old Mac". Static site, GitHub Pages, no build step.

**Live:** https://secondwindformac.com/ · Spanish: [`/es/`](https://secondwindformac.com/es/)

## Structure

```
index.html        English (default language)
es/index.html     Spanish
compatibility/    "Will my Mac work?" checker (es/compatibilidad/)
download/         Download page (es/download/)
rescue/           Rescue card (es/rescue/)
styles.css        Shared styles (light + dark via prefers-color-scheme)
assets/           Screenshots (real E2E test run), favicon
```

## Adding a language

1. Copy `es/` to a new folder named by ISO code (`pt/`, `fr/`, etc.) and translate the strings.
2. Fix the two relative prefixes if depth changes (they won't for one level): `../styles.css`, `../assets/`.
3. Add the new `<link rel="alternate" hreflang="xx">` to **every** page, and the new entry in each page's `.lang` selector.

## Buttons ↔ links.conf

Button URLs mirror `links.conf` in the main repo (marked with `<!-- from links.conf: KEY -->`
comments): donations → `DONATE_URL` (Ko-fi), support → `CONTACT_EMAIL`
(hello@secondwindformac.com). If they change, update `links.conf` there and the
marked hrefs here in the same commit. Nothing a normal visitor clicks for help
should lead to GitHub.

## Custom domain: secondwindformac.com (CONNECTED 2026-08-30)

Registrar: domains.com. DNS: 4 apex `A` records → `185.199.108.153/.109/.110/.111`
and `CNAME www` → `secondwindformac.github.io`. This repo carries the `CNAME` file
(that is what keeps the custom domain across Pages builds, so do not delete it),
every `canonical`/`hreflang`/`og:` URL points at the domain, and the main repo's
`links.conf` `WEBSITE_URL` does too. HTTPS is enforced (Let's Encrypt via Pages).
The old `secondwindformac.github.io/second-wind-site` URLs 301-redirect here.

## License

Site code MIT. Screenshots are our own (from the project's validated end-to-end run).
Mac, macOS and MacBook are trademarks of Apple Inc.; Ubuntu is a trademark of Canonical Ltd.
Second Wind is an independent project, not affiliated with or endorsed by Apple or Canonical.
