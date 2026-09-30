# munro.com.au — landing page

Static landing page for **munro.com.au**: profiles and links for Richard Munro
(Alternate Business Strategies) and Matthew Munro (Munro Solutions).

Repo: `MrMattMunro/munro-landing` · served by GitHub Pages.

## Files
- `index.html` — the whole page (self-contained; fonts from Google Fonts)
- `richard.jpg`, `matt.jpg` — 512×512 headshots referenced by `index.html`
- `CNAME` — added at cutover only (contains `munro.com.au`); see below

## Status
- Repo created and pushed; GitHub Pages enabled on `main` / root.
- Live preview: the `*.github.io` Pages URL (no custom domain yet).

## Cutover to munro.com.au (do these together)
Only these need Richard's Microsoft 365 access; the repo is already done.

**1. DNS — in the Microsoft 365 admin center.** Change only these two records:

| Record | Type  | Value |
| ------ | ----- | ----- |
| `@`    | A     | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (replace the old `52.237.209.250`) |
| `www`  | CNAME | `mrmattmunro.github.io` (delete the old `www` A record first) |

**2. Add the custom domain to the repo.** Either commit a `CNAME` file containing
`munro.com.au`, or set it under **Settings → Pages → Custom domain**. Then tick
**Enforce HTTPS** once the cert provisions (up to ~1 hour after DNS resolves).

### ⛔ DO NOT TOUCH — these carry Richard's business email
- `_dmarc` (TXT)
- `selector1._domainkey`, `selector2._domainkey` (CNAMEs)
- the MX record (`munro-com-au.mail.protection.outlook.com`) and `autodiscover`

The `lyncdiscover` / `sip` / `_sipfederationtls` / `_sip._tls` records are dead
Skype-for-Business entries — harmless, leave them.
