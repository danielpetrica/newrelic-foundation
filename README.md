# New Relic Foundation

Productized New Relic monitoring setup for SaaS teams. One price, one week delivery.

## What it is

A fixed-price (€850) New Relic monitoring package for small SaaS teams without dedicated DevOps. Full-stack setup: APM, host, browser, Docker, synthetics, alerts, and The Foundation Kit — a documented runbook of everything configured.

## Sales page

The single-page sales site at `index.html` — plain HTML, zero dependencies, system fonts only. Served via nginx behind Traefik at `danielpetrica.com/newrelic`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Sales page |
| `PLAN.md` | Full planning document |
| `DESIGN-SPEC.md` | Original design specification |
| `og-image.jpg` | Open Graph / social media share image |
| `favicon.ico` / `favicon-32.png` | Browser favicons |
| `apple-touch-icon.png` | Apple Touch Icon |
| `images/daniel-petrica.jpg` | Author photo |

## Deployment

Static files served by nginx:alpine. Add to your Traefik docker-compose stack:

```yaml
newrelic-page:
  image: nginx:alpine
  volumes:
    - ./newrelic-foundation:/usr/share/nginx/html:ro
  labels:
    - "traefik.enable=true"
    - "traefik.http.routers.newrelic.rule=Host(`danielpetrica.com`) && PathPrefix(`/newrelic`)"
    - "traefik.http.services.newrelic.loadbalancer.server.port=80"
```

## Integrations

- **Stripe** — payment link for checkout
- **Mailcoach** — email capture for freebie PDF ("5 New Relic Alerts Every SaaS Should Have")
