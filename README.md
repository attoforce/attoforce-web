# attoforce-web

Source for [attoforce.ai](https://attoforce.ai) — a minimal, static single-page site for Attoforce.

> make AI work

## Contents

```
attoforce-web/
├── index.html              # the entire site (one page, anchored sections)
├── css/styles.css          # gray-monochrome stylesheet
├── assets/                 # SVG logos + favicon
│   ├── favicon.svg
│   ├── logo-dark.svg       # dark wordmark on light bg
│   ├── logo-light.svg      # light wordmark on dark bg
│   ├── logo-gray.svg       # black wordmark + white arrow on brand gray
│   ├── logo-mark.svg       # icon only, dark
│   └── logo-mark-light.svg # icon only, light
├── CNAME                   # attoforce.ai (used by GitHub Pages if you choose it)
├── LICENSE                 # MIT
└── README.md
```

No build step. No framework. No JS bundler. Any static host will serve it.

## Site sections

1. **Hero** — logo + "make AI work" + short intro
2. **Who we are** — AI & Cloud startup, founder context, ASEAN/India/APJ
3. **Our Belief** — "The hardest work is making things simple" + Vision card
4. **Core Tenets** — Simplification, Speed, Precision, Outcomes
5. **Team** — DP bio with LinkedIn link
6. **Services** — Coming soon
7. **Contact** — mailto:contact@attoforce.ai

## Preview locally

```bash
cd attoforce-web
python3 -m http.server 8000
# → open http://localhost:8000
```

Or: `npx serve .`

## Deploy to Porkbun Static Hosting

Porkbun offers free static hosting on any domain registered with them —
perfect for this site.

### Step 1 — Enable static hosting

1. Log in at [porkbun.com](https://porkbun.com).
2. Go to **Domain Management** and click **Details** on `attoforce.ai`.
3. Scroll to **Static Hosting** and click **Manage** → **Enable**.
4. Wait a minute for Porkbun to provision the hosting environment and
   issue an SSL certificate (first-time setup).

### Step 2 — Prepare the upload

Porkbun expects a ZIP whose root contains `index.html` (not a folder
wrapping it). From inside this repo:

```bash
cd attoforce-web

# Clean up anything you don't want shipped
rm -f .DS_Store

# Create the deploy zip (exclude git + system files)
zip -r ../attoforce-web.zip . \
  -x "*.git*" ".git/*" ".git_old/*" ".git.stale.*/*" "*.DS_Store" "README.md" "LICENSE"
```

> The excludes above omit files that shouldn't be public (git history,
> stale backups, macOS noise). Keeping `README.md` and `LICENSE` out of
> the zip is optional — they're harmless but add bytes.

### Step 3 — Upload

1. In the Porkbun dashboard for `attoforce.ai`, open **Static Hosting**.
2. Click **Upload File** and select `attoforce-web.zip`.
3. Porkbun extracts the zip into the hosting root. The previous contents
   (if any) are replaced.
4. Give it 1–2 minutes for the CDN to refresh. Visit
   [https://attoforce.ai](https://attoforce.ai).

### Updating the site later

1. Edit files locally → `python3 -m http.server 8000` to preview.
2. Re-zip (same command as Step 2).
3. Re-upload the new zip in Porkbun Static Hosting. That's it.

### Using `www.attoforce.ai` too

In Porkbun's DNS for `attoforce.ai`, add a `CNAME` record:
- **Host:** `www`
- **Type:** `CNAME`
- **Answer:** `attoforce.ai`

This keeps both `attoforce.ai` and `www.attoforce.ai` pointing at the
same static site.

## Editing content

- **Copy** lives inline in `index.html` under each `<section>`. Edit
  prose directly.
- **Palette & typography** are CSS variables at the top of
  `css/styles.css` (`--ink`, `--mist`, `--cloud`, etc.).
- **Logos** are SVG. The hero logo is inlined in `index.html`;
  everywhere else uses files from `assets/`.
- **Contact email** is `contact@attoforce.ai` — search-and-replace if
  it changes.

## Brand

See `../AttoForce-Brand-Guide.html` (one level up in this workspace)
for the full brand system — palette, type, logo usage rules.

## License

MIT — see [LICENSE](./LICENSE).
