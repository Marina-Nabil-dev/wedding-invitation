# Cloudflare Pages deployment — Mark & Marina

## Fastest deployment: Direct Upload

This project is already a static deploy-ready site. There is no build step.

1. Sign in to Cloudflare.
2. Open **Workers & Pages**.
3. Choose **Create application** → **Get started** → **Drag and drop your files**.
4. Use a project name such as `mark-marina-celebration`.
5. Upload the contents of this folder (or the prepared `cloudflare-pages-upload.zip`).
6. Choose **Deploy site**.
7. Cloudflare will give you a `*.pages.dev` URL.

Important: Direct Upload projects cannot later be converted to Git integration. If you want automatic deployments from GitHub from day one, create a Git-integrated Pages project instead.

## Before sending the link to guests

### 1. Connect the RSVP backend
Deploy `google-apps-script.gs` as a Google Apps Script Web App from the Google Sheet that owns the RSVP data. Then edit `config.js`:

```js
appsScriptUrl: 'https://script.google.com/macros/s/YOUR_DEPLOYMENT_ID/exec',
```

Do not put passwords, API keys, or private tokens in `config.js`.

### 2. Verify the exact public URL
After deployment, add this tag in `index.html` once you know the final URL:

```html
<meta property="og:url" content="https://YOUR-PROJECT.pages.dev/" />
```

If you later add a custom domain, change `og:url` to the custom domain.

### 3. Music
The site deliberately contains no commercial recording. Only add audio you are licensed/authorized to publish. Add a `<source>` inside the existing `<audio id="music">` element.

### 4. Padrino photos
The venue component intentionally remains a placeholder until photos from the exact booked Padrino branch are verified.

## Git integration alternative
For a plain static site, Cloudflare's current guidance allows a no-op build command such as `exit 0`; set the build output directory to the directory containing `index.html`.

## Production smoke test
Test on the final `pages.dev` URL:
- opening animation
- English / Arabic + RTL
- all four couple photos
- Maps button
- RSVP yes and no
- 1–4 guest names
- duplicate phone update
- exact-capacity and waiting-list cases
- cancellation / seat release / waiting-list promotion
- October 1 cutoff
- Sheet totals
- notification email
- mobile Chrome and iPhone Safari
- WhatsApp preview
