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

## Wiring up Beehiiv (newsletter)

The signup form is already wired up to Beehiiv using the embed Beehiiv provided.

In `index.html`, the loader script is in `<head>`:

```html
<script
  async
  src="https://subscribe-forms.beehiiv.com/v3/loader.js"
  data-beehiiv-form="4411378e-d52b-4a37-9cf7-594444b9819d"
></script>
```

And the form renders inside an `<iframe>` in the signup section.

If you ever need to swap the form (different publication, different list):

1. In Beehiiv, create a new **Embed** form.
2. Replace the `src` of the `<script>` in `<head>` and the `src` of the `<iframe>` in the signup section with the new values Beehiiv gives you.
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
