# istrumpdead.io

One static page, no build step. Everything runs in the visitor's browser:

- **The answer** comes from Wikidata record Q22686: **Yes** if it has a date of death (P570), **No** otherwise.
- **The question** uses a random nickname from `NICKNAMES` (click it for another). The real name never appears on the page.
- **Local organizations**: the visitor's state is looked up from their IP via [GeoJS](https://www.geojs.io/), and the page shows that state's ACLU affiliate(s) plus the national ACLU. Visitors outside the US only see the worldwide list (`GLOBAL_ORGS`).

`ACLU_AFFILIATES` was pulled from `https://www.aclu.org/wp-json/wp/v2/affiliate_info?per_page=100` (52 entries: 50 states, DC and Puerto Rico; California has three).

## Deploy free on GitHub Pages

1. Create a public GitHub repo and push these files to `main`.
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/`.
3. At your domain registrar, add DNS records for `istrumpdead.io`:
   - `A` records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `<your-github-username>.github.io`
4. Back in Settings → Pages, confirm the custom domain and tick "Enforce HTTPS" once the certificate is issued.

The `CNAME` file in this folder tells GitHub Pages which domain to serve.
