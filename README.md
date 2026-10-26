# istrumpdead.io

One static page. It reads Donald Trump's Wikidata record (Q22686) in the visitor's browser and shows **Yes** if it has a date of death (P570), **No** otherwise, then lists organizations to support. Edit the `ORGS` array in `index.html` to change the list.

## Deploy free on GitHub Pages

1. Create a public GitHub repo and push these files to `main`.
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/`.
3. At your domain registrar, add DNS records for `istrumpdead.io`:
   - `A` records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `<your-github-username>.github.io`
4. Back in Settings → Pages, confirm the custom domain and tick "Enforce HTTPS" once the certificate is issued.

The `CNAME` file in this folder tells GitHub Pages which domain to serve.
