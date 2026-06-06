# New Relic Foundation

Productized New Relic monitoring setup for SaaS teams. One price, one week delivery.

## What it is

A fixed-price (EUR 850) New Relic monitoring package for small SaaS teams without dedicated DevOps. Full-stack setup: APM, host, browser, Docker, synthetics, alerts, and The Foundation Kit -- a documented runbook of everything configured.

## Sales page

Single-page site at `public/index.html` -- plain HTML, zero dependencies, system fonts only. Served via nginx behind Traefik at `danielpetrica.com/newrelic`.

## Files

| File | Purpose |
|------|---------|
| `public/index.html` | Sales page |
| `public/og-image.jpg` | Open Graph / social media share image |
| `public/favicon.ico` / `public/favicon-32.png` | Browser favicons |
| `public/apple-touch-icon.png` | Apple Touch Icon |
| `public/images/daniel-petrica.jpg` | Author photo |
| `compose.yaml` | Docker Compose deployment config |
| `nginx.conf` | nginx config (root-based, SPA fallback) |

## Deployment

```bash
git clone git@github.com:danielpetrica/newrelic-foundation.git
cd newrelic-foundation
docker compose up -d
```

To update:

```bash
git pull && docker compose up -d --force-recreate
```

The nginx container serves from `public/` and is exposed via Traefik at `PathPrefix(/newrelic)`.

## Integrations

- **Stripe** -- payment link for checkout
- **Mailcoach** -- email capture for freebie PDF ("5 New Relic Alerts Every SaaS Should Have")
