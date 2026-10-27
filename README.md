# runfix waitlist

The "launching 1 December 2026" page for runfix: one static `index.html` (no build step), with a countdown, a Discord invite and an email address to join the waitlist.

## Publish on GitHub Pages

1. Create a public repository (for example `runfix-dev/waitlist`) and push this folder to its `main` branch.
2. In the repository: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. The workflow in `.github/workflows/pages.yml` publishes the page on every push to `main`. The address appears in the workflow run and in Settings → Pages (for example `https://runfix-dev.github.io/waitlist/`).

To use your own domain (for example `waitlist.runfix.dev`), add it in Settings → Pages → Custom domain and create the DNS record GitHub shows.

## How people join

There is no form. The page offers two ways in, in the hero and again at the bottom:

- **Join the Discord**: the invite link `https://discord.gg/ER9rfHxDwD` (also in the nav and footer). To track how many people join from this page, create a separate permanent invite in Discord → Server Settings → Invites, and replace the code everywhere in `index.html`.
- **Email us to join the waitlist**: opens a pre-filled email to `hello@runfix.dev`. The address is also shown as text with a copy button, for people whose browser has no mail app.

`LAUNCH` at the top of the script sets the countdown (default `2026-12-01T00:00:00Z`). After it passes, the page says runfix is live.

## Preview locally

```sh
python3 -m http.server 8080
# open http://localhost:8080
```
