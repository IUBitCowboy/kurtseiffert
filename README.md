# kurtseiffert (personal research site)

Static Hugo site for Kurt Seiffert's public research presence.
Live at: https://iubitcowboy.github.io/kurtseiffert/ (custom domain
`kurtseiffert.com` planned — swap `baseURL` and add DNS/CNAME when the
domain lands).

## Environment

- Hugo "extended" >= 0.167 (installed via Homebrew on the Studio).
- No theme dependencies, no submodules, no npm — layouts + a single CSS
  file live in-repo.
- Build: `hugo --minify`; local preview: `hugo server`.

## Deployment

GitHub Actions (`.github/workflows/hugo.yml`) builds and deploys `main` to
GitHub Pages (official `deploy-pages` action). Deploys are self-triggering
on push to `main`.

## Standing-policy deviation (D8) — public repo

The agent-projects standard defaults to private repos. This repo is
**public**: the account is on GitHub Free, which does not offer Pages on
private repos, and the repo ships a *public website* — there is nothing in
it that is not publishable. What/why/until: public because Pages-on-Free
requires it; no secrets policy enforced by `.gitignore` + secret-scan gate
before push; review annually or when the plan changes.

## Content rules (binding)

- Humans-layer only: sanctioned public names (MCP GRID, Angband) are fine;
  internal jargon, repo paths, raw task receipts, and personal-family or
  private-lead details stay out.
- No analytics, no tracking, no third-party JS.