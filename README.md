# PostureMaxx — Landing Page

Static landing page for the PostureMaxx iOS TestFlight beta. Designed for GitHub Pages (or any static host).

## Files

- **`index.html`** — landing page
- **`privacy.html`** — privacy policy
- **`og.svg`** — Open Graph / Twitter card image (1200×630)
- **`README.md`** — this file

## Deploy

The repo root should be served as a static site. On GitHub Pages:

1. Settings → Pages → Source: `main` branch, `/ (root)`
2. Site will be live at `https://<username>.github.io/posturemaxxweb/`

## Wiring up the newsletter (Brevo / Sendinblue)

The signup form is a Brevo JS embed. The form markup lives in `index.html` in the signup section, with form-specific CSS in the `<head>` and the validation script at the bottom of `<body>`.

If you ever need to swap forms (different list, different workspace):

1. In Brevo, get the new form's full embed code (CSS + markup + validation script).
2. Replace the corresponding sections in `index.html`:
   - The `@font-face` rules, `.sib-form-message-panel` rules, and `#sib-container` rules in the `<style>` block in `<head>`
   - The `<link rel="stylesheet" href="https://sibforms.com/forms/end-form/build/sib-styles.css">` tag
   - The form markup inside the signup section
   - The validation script + `<script defer src="...main.js">` at the bottom of `<body>`
3. Commit and push.

## Customizing

- **Email contact** — search and replace `hello@posturemaxx.app` across all files.
- **Domain** — update `og:url` and `og:image` in `index.html` if you move to a custom domain.
- **Privacy policy** — review `privacy.html` and confirm the legal entity name, retention periods, and any app-store-required sections (e.g. EULA, subscriptions) are accurate for your jurisdiction.

## Local preview

Just open `index.html` in a browser, or:

```bash
python3 -m http.server
# then visit http://localhost:8000
```
