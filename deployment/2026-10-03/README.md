# Attoforce website upload package

This folder contains the updated static website ZIP for Porkbun, including the latest website copy, offerings, careers pages, day and night controls, and Plausible analytics.

## Deploy

1. Download `attoforce-site-2026-10-03.zip` using GitHub’s Download raw file button.
2. Keep a backup of the current hosted site.
3. Upload the ZIP through the existing Porkbun hosting control for `attoforce.ai`. The ZIP has `index.html` at its root.
4. Check the homepage, an offering page and a careers page.
5. Run the installation check in Plausible and confirm a real pageview appears.

Uploading this package to GitHub does not deploy it to Porkbun. The existing website files at the repository root are unchanged.

## Analytics and verification

All 13 production HTML pages contain the supplied Plausible script directly in the head, with one initializer. Tracking is enabled for `attoforce.ai` and `www.attoforce.ai`. Local previews do not send visitor events. URL query strings, fragments, enquiry text and email subjects are excluded.

The site build, analytics checks and ZIP integrity checks passed. The SHA-256 file identifies the verified package. No synthetic events were sent to Plausible. Live dashboard receipt remains unverified until deployment.

Pageviews are automatic. Configure matching custom goals for offering, contact, email and LinkedIn clicks in Plausible. Email clicks indicate intent, not completed applications or enquiries. See [Plausible custom event goals](https://plausible.io/docs/custom-event-goals).
