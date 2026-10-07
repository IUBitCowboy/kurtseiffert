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

## DNS

Cloudflare manages `kurtseiffert.dev` (plus parked `kurtseiffert.com`/`.net`).

- Apex (`@`): four A records → `185.199.108.153` / `185.199.109.153` /
  `185.199.110.153` / `185.199.111.153` (GitHub Pages apex IPs).
- `www`: CNAME → `iubitcowboy.github.io`.
- **All records must be DNS-only (grey cloud).** Proxying (orange cloud)
  breaks Let's Encrypt issuance for GitHub Pages; if ever re-proxied, set
  SSL/TLS mode to Full (strict).
- `static/CNAME` (must ship in the deploy artifact — Hugo ignores root-level
  CNAME) keeps the Pages binding across workflow-type deploys.
- `kurtseiffert.com` is **parked intentionally** — reserved for future
  commercial use (book/publications). No DNS records by design: binds would
  tie the name to the research site in search indexes.
- `kurtseiffert.net` parked, no records, no redirects.

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