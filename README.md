# attoforce-web

Source for [attoforce.ai](https://attoforce.ai) — a minimal, static single-page site for Attoforce.

> make AI work

## What's here

```
attoforce-web/
├── index.html          # the entire site
├── css/styles.css      # styles
├── assets/             # SVG logos + favicon
│   ├── logo-dark.svg
│   ├── logo-light.svg
│   ├── logo-mark.svg
│   ├── logo-mark-light.svg
│   └── favicon.svg
├── CNAME               # (optional) custom domain for GitHub Pages
├── LICENSE
└── README.md
```

No build step, no framework, no JavaScript bundler. Just three static files plus assets. Any static host will serve it.

## Preview locally

```bash
# Python 3
python3 -m http.server 8000

# or Node
npx serve .
```

Then open [http://localhost:8000](http://localhost:8000).

## Deploy to Porkbun (static hosting)

Porkbun offers free static hosting on any domain registered with them.

1. Log in at [porkbun.com](https://porkbun.com) and open **Domain Management** for `attoforce.ai`.
2. Under the domain, click **Static Hosting → Enable**.
3. ZIP the contents of this folder (not the folder itself — the ZIP's root should contain `index.html`):
   ```bash
   cd attoforce-web
   zip -r ../attoforce-web.zip . -x "*.git*" "*.DS_Store"
   ```
4. In the Porkbun dashboard, **upload the ZIP**. Porkbun will extract it to the hosting root.
5. Wait for the SSL certificate to provision (usually 5–30 minutes).
6. Visit `https://attoforce.ai`.

To update the site later, upload a new ZIP — Porkbun replaces the previous contents.

## Deploy to GitHub Pages (alternative)

1. Push this repo to GitHub (see below).
2. Go to **Settings → Pages**.
3. Set **Source** to `Deploy from a branch`, **Branch** to `main`, folder `/ (root)`.
4. To use `attoforce.ai`, keep the `CNAME` file in this repo and in Porkbun DNS, add:
   - `ALIAS` or `ANAME` for `attoforce.ai` → `<your-github-username>.github.io`
   - `CNAME` for `www.attoforce.ai` → `<your-github-username>.github.io`

## Push to GitHub

The repo has already been initialized with an initial commit. To publish:

```bash
# Create the remote repo on github.com first (empty, no README)
git remote add origin git@github.com:<your-github-username>/attoforce-web.git
git branch -M main
git push -u origin main
```

## Editing content

- **Copy** lives inline in `index.html` — edit the `<section>` blocks directly.
- **Colors & typography** are defined as CSS variables at the top of `css/styles.css`.
- **Logos** are inline SVG for the hero, and standalone SVG files in `assets/` for everywhere else.
- **Contact email** is `dp@attoforce.ai` — search-and-replace if it ever changes.

## Brand

See `../AttoForce-Brand-Guide.html` (one level up in this workspace) for the full brand system.

## License

MIT — see [LICENSE](./LICENSE).
