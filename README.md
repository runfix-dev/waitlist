# runfix waitlist

The founding-members page for runfix, "the safety net for apps built with AI", launching 1 December 2026. It is one static `index.html` (no build step) with a countdown, a Discord invite and an email address for early access.

The copy follows `../docs/RUNFIX_STRATEGY_2026-10.md` §3–§7b: pain first, then the safety net (Safe Deploy, proven fixes, Fix Lock, Deployment Guard, Spend Guard, restore), then control, the founding-member offer and the FAQ. Every claim must be true at launch (`../docs/TRACKER.md`). Never name people or companies who had incidents. Pricing stays out until it's decided.

## Publish on GitHub Pages

1. Create a public repository (for example `runfix-dev/waitlist`) and push this folder to its `main` branch.
2. In the repository: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. The workflow in `.github/workflows/pages.yml` publishes the page on every push to `main`. The address appears in the workflow run and in Settings → Pages (for example `https://runfix-dev.github.io/waitlist/`).

To use your own domain (for example `waitlist.runfix.dev`), add it in Settings → Pages → Custom domain and create the DNS record GitHub shows.

## How people join

There is no form. The page offers two ways in, in the hero and again at the bottom:

- **Join the Discord**: the invite link `https://discord.gg/ER9rfHxDwD` (also in the nav and footer). To track how many people join from this page, create a separate permanent invite in Discord → Server Settings → Invites, and replace the code everywhere in `index.html`.
- **Get early access** (the primary call to action): opens a pre-filled email to `hello@runfix.dev` with the subject "runfix early access". The body asks what the app was built with, where it runs and its link, so replies qualify themselves. The address is also shown as text with a copy button, for people whose browser has no mail app.

`LAUNCH` at the top of the script sets the countdown (default `2026-12-01T00:00:00Z`). After it passes, the page says runfix is live.

## Preview locally

```sh
python3 -m http.server 8080
# open http://localhost:8080
```
