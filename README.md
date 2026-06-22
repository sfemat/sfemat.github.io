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

The signup form uses Brevo's JS embed. In `index.html`, the loader script is in `<head>`:

```html
<script>
  (function () {
    var s = document.createElement('script');
    s.type = 'text/javascript';
    s.async = true;
    s.src = 'https://bdb5b4a4.sibforms.com/v2/sibforms.js';
    document.head.appendChild(s);
  })();
</script>
```

The form markup (email field + Subscribe button) lives in the signup section and POSTs to Brevo's subscribe endpoint.

If you ever need to swap forms (different list, different workspace):

1. In Brevo, create a new form.
2. Update the `s.src` URL in the loader script to your new form's `sibforms.com` subdomain.
3. Update the form `action` URL in the `<form>` tag to match.
4. Commit and push.

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
