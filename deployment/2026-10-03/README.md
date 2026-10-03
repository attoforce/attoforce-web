# Attoforce formatting fix — 3 October 2026

Use `attoforce-site-2026-10-03-cache-fix.zip` for the next Porkbun upload.

The original upload contained the right pages and assets, but the styles and scripts used the same names as the earlier site. A browser retained the old stylesheet. Porkbun serves CSS with a 30-day cache lifetime.

This package gives all six CSS and JavaScript assets content-specific filenames and updates all 13 pages to load them. The Plausible head integration is preserved. The new filenames prevent old CSS/JS cache entries from being reused by new pages.

1. Download the ZIP itself (not GitHub's whole-repository Code > Download ZIP).
2. Upload it through the same Porkbun static-hosting upload screen. `index.html` is at the ZIP root.
3. Once Porkbun reports success, hard-refresh the homepage: Command + Shift + R on Mac, or Ctrl + Shift + R on Windows.
4. Check the homepage, an offering page and a careers page, including the day/night control.

The deployment remains a manual Porkbun upload. No production change is made by storing this package on GitHub. The adjacent checksum and verification report identify the tested package.

## Analytics

The supplied Plausible tracker appears once in the head of all 13 HTML pages, with one initializer. Production tracking is limited to `attoforce.ai` and `www.attoforce.ai`; local previews send no visitor events. Query strings, fragments and email subjects are excluded from analytics. Live Plausible dashboard receipt remains unverified.

Build, asset-integrity, theme, analytics and ZIP checks passed. The extracted ZIP was visually reviewed at 1280px and 390px widths. The homepage, careers and Code Transformation page rendered correctly; mobile navigation, the day-mode control and animation pause worked.
