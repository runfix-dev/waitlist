# runfix waitlist

The "launching 1 December 2026" page for runfix: one static `index.html` (no build step), with a countdown and a waitlist form.

## Publish on GitHub Pages

1. Create a public repository (for example `runfix-dev/waitlist`) and push this folder to its `main` branch.
2. In the repository: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. The workflow in `.github/workflows/pages.yml` publishes the page on every push to `main`. The address appears in the workflow run and in Settings → Pages (for example `https://runfix-dev.github.io/waitlist/`).

To use your own domain (for example `waitlist.runfix.dev`), add it in Settings → Pages → Custom domain and create the DNS record GitHub shows.

## Collect sign-ups

Open `index.html` and set the settings at the top of the script:

- `WAITLIST_ENDPOINT` — where the form sends `{"email", "app", "source"}` as JSON. A free option is [Formspree](https://formspree.io): create a form and paste its URL (`https://formspree.io/f/…`). Later you can point it at the runfix API.
- While it's empty, the button opens an email to `FALLBACK_EMAIL` (hello@runfix.dev) with the sign-up written out, so nobody is lost.
- `LAUNCH` — the launch moment (default `2026-12-01T00:00:00Z`). After it passes, the page says runfix is live.

## Preview locally

```sh
python3 -m http.server 8080
# open http://localhost:8080
```
