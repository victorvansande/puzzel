# Steunpuzzel

Uitlegpagina voor de Gekkoo-steunpuzzel op het bedankingsfeest.
Bezoekers scannen een QR-code of NFC-tag en komen op deze pagina.

- `index.html` — de pagina zelf (mobiel-eerst, zelfstandig, geen build)
- `print.html` — bron voor de affiches (A4 liggend, 6 pagina's)
- `steunpuzzel.pdf` — de afdrukbare versie, gegenereerd uit `print.html`

## PDF opnieuw maken

```
& "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless=new --disable-gpu --no-first-run --virtual-time-budget=15000 --user-data-dir="$env:TEMP\edgepdf-puzzel" --print-to-pdf="C:\Users\victor\projecten\puzzel\steunpuzzel.pdf" "file:///C:/Users/victor/projecten/puzzel/print.html"
```

## Publiceren

Elke push naar `main` deployt via GitHub Actions naar Cloudflare Workers
(secrets: `CLOUDFLARE_API_TOKEN` en `CLOUDFLARE_ACCOUNT_ID`).
