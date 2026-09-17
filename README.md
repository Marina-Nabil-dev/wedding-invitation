# Mark & Marina — The Celebration Continues

Cloudflare Pages-ready wedding after-party invitation.

## Public frontend
Static HTML/CSS/JS. No build tool or server is required. Couple photos are stored under `assets/couple/`. The Padrino gallery remains a verified-photo placeholder.

## RSVP backend
`google-apps-script.gs` is the Google Apps Script backend. It implements:
- backend RSVP deadline enforcement
- normalized-phone duplicate/update behavior
- max 4-person party
- 70-person private capacity
- Confirmed / Waiting List / Declined states
- FIFO waiting-list promotion when a whole party fits
- ScriptLock protection against simultaneous overbooking
- email notifications to the configured address

Set the deployed Apps Script `/exec` URL in `config.js` before going live.

## Cloudflare
The project includes `_headers`, `_redirects`, `404.html`, favicon, Open Graph image, and `CLOUDFLARE_DEPLOY.md`.

## Still intentionally pending
- live Google Apps Script deployment URL
- verified Padrino interior photos
- licensed/user-provided music file
- final Cloudflare `pages.dev` URL / optional custom domain
