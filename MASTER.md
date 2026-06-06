# New Relic Foundation — Master Reference

> **Status**: Sales page built. Stripe live. Mailcoach live. Deploy pending.  
> **Repo**: github.com/danielpetrica/newrelic-foundation  
> **Live URL**: danielpetrica.com/newrelic  
> **Last updated**: June 2026

---

## 1. Product Summary

Fixed-price New Relic monitoring setup for SaaS teams without dedicated DevOps. One package = one application, full stack monitoring, one week delivery, €850.

**Tagline**: "The monitoring setup your SaaS should have shipped with. Delivered in one week from the moment you provide access."

**Name**: Working name — "Productized New Relic Consulting for Software Teams." Needs a shorter final name.

---

## 2. Pricing

| Item | Price | Notes |
|---|---|---|
| Package (one app) | €850 | Single price, no tiers, no negotiation |
| Payment plan | €425 + €425 | Second payment due on delivery or 30 days, whichever first |
| Upwork listing | €1,020 | Absorbs 20% platform fee, nets ~€850 |
| Tuning pass (add-on) | €200 | 2h tuning over 2 weeks, €100/hr |
| Monthly retainer | €250/mo | Monthly review + up to 2 threshold adjustments. Extra work at €65/hr |
| Agency white-label commission | €150 | Agency takes credit, you're invisible, you net €700 |
| Agency co-branded commission | €200 | Your name stays on Foundation Kit, you net €650 |

**Refund policy**: If environment doesn't match checkout claims, full refund minus time spent at €65/hr.

**Cost basis**: €50-65/hr × 5-10h = €250-650. Strong margin at all levels.

---

## 3. Target Customer

Small SaaS teams (8-25 people) without dedicated DevOps/SRE. Sweet spot: has a CTO or technical founder who understands monitoring but doesn't have time to set it up.

**Supported stacks** (OR combinations, not AND):
- **Backend**: PHP (Laravel) or Node.js
- **Frontend**: Vue, React, Nuxt, Next.js, or any standard JS framework
- **Host**: Linux VPS — Docker-based or directly on the machine
- **Proxy**: Apache, Nginx, or Traefik

**Excluded** (custom quote or rejection):
- Kubernetes / Nomad / custom orchestration
- AWS platform services (EC2 alone is fine)
- Windows Server
- Multi-region / HA clusters
- Non-standard agents (Python, Ruby, .NET)
- NRQL dashboards as primary deliverable

---

## 4. Scope

### Included (The Foundation Kit)

| Category | Details |
|---|---|
| APM | PHP (Laravel) or Node.js agent config, tuned to framework |
| Host monitoring | Linux — CPU, memory, disk, network |
| Browser monitoring | Script provided, installed by client dev |
| Docker monitoring | Container-level visibility (or direct-on-machine) |
| Synthetics | Ping, full page load, SSL certificate checks |
| Alert policies | Conditions scoped to app, sane thresholds |
| Alert delivery | Email + Slack configured |
| Web server | Apache, Nginx, or Traefik dashboards |
| MySQL | Query performance, connections, slow queries |
| System logs | Included |
| App logs | Included for standard frameworks (Laravel Monolog, Node Winston/Bunyan) |
| NRQL | Minor customization for alert functionality only |
| Foundation Kit | Documented runbook — every alert, threshold, configuration decision |

### Excluded
- Custom NRQL queries or dashboards
- Kubernetes, AWS monitoring, multi-region
- Touching client application code
- Browser script installation (client dev does this)

### Delivery
- **Timeline**: One week from SSH access confirmed (not from purchase)
- **Tuning window**: 14 days included — threshold adjustments, alert tweaks
- **Bus factor**: Foundation Kit documented so any DevOps engineer can take over

---

## 5. Service Provider Identity

**Daniel Petrica** — andrei@danielpetrica.com

- 8 years senior full-stack developer (PHP, Laravel, Node.js, Vue.js, Docker)
- New Relic specialist since 2023 — SaaS companies, security firms, own production systems
- Responsible for New Relic monitoring implementation at Warrant Hub S.p.A.
- Contributed to ISO 27001 certification at Warrant Hub as code and observability advisor
- Evaluated multiple platforms (OpenObserve, Nightwatch) before standardizing on New Relic
- Upwork profile: upwork.com/freelancers/andreidanielp

**Key differentiator**: Someone who writes production code AND instruments it — spots things in APM data that pure ops consultants miss.

---

## 6. Social Proof

### Testimonials on page

1. **Gabriel B., COO** (Jun 2023, Upwork verified) — *"We hired Andrei to set up New Relic on our website. Not only did he perfectly set up New Relic, but he also helped us understand the platform and the different alerts we received. He was always quick to respond. I highly recommend Andrei to anyone looking for a New Relic expert with excellent communication skills."*

2. **APM Tool Expert for SaaS Website** (5.0 ★, 75h, $1,646) — *"Working with Andrei is a fantastic experience. He is highly skilled with New Relic and provided valuable suggestions that greatly improved our project. His responsiveness and support whenever we needed help were outstanding."*

3. **New Relic Implementation client** (5.0 ★, 61h, $2,730) — *"Andrei is exceptionally professional and possesses extensive knowledge in his field. The project was completed to a very high standard, and we highly recommend his services."*

### Strategy
Reviews validate the person, not the specific package. Someone trusted with $2,730 in New Relic work can handle €850. After first packages deliver, request testimonials from those clients for package-specific social proof.

---

## 7. Marketing & Channels

### Primary (active effort)
- **Direct outreach**: Cold email SaaS founders from Product Hunt, BuiltWith, Laravel directories. Opener: *"I help SaaS teams level up their production monitoring. If you already have this covered, great — if not, here's a path to full observability in one week."*
- **Agency partnerships**: Any agency building software without monitoring (not cPanel/WordPress-only). Two models: white-label (€150 commission, you net €700) or co-branded (€200 commission, you net €650, keep testimonial rights).
- **PHPxTokyo talks**: Meets every 3 months. Turn blog article into 20-min talk. Room full of PHP/Laravel devs = target market.

### Secondary (passive)
- **Upwork project catalog**: List at €1,020. Set and forget. Link from proposals.
- **LinkedIn**: 1-2 posts/week. Awareness only. Don't expect direct conversions.
- **Blog article (July 2026)**: "Full-Stack New Relic Monitoring for a Laravel SaaS" — SEO play, CTA to sales page.

### Other ideas
- Indie Hackers / SaaS communities, Laravel Discord/Slack, guest posts (Laravel News, Dev.to), New Relic partner program.

### Launch timing
June-August is slow for B2B. Soft launch now, real push September-October. Don't panic over slow summer traction.

---

## 8. Competitive Positioning

| Competitor | Counter |
|---|---|
| New Relic's free onboarding | NR installs generic defaults. I tune thresholds to your traffic, build a runbook. Their goal is data in. Mine is data that's useful. |
| AI tools (ChatGPT, Claude) | AI gives config files, can't SSH in, can't verify or personalize. I've done this since 2023. |
| Hiring a DevOps consultant | €200/day × 5-7 days = €1,000-1,400 for same scope. Package is €850 with documented Foundation Kit. |
| Laravel Forge / basic monitoring | Forge tells you the server is alive. Doesn't correlate frontend slowdowns with server logs. Different product. |
| Datadog/Grafana consultants | If you're on Datadog and happy, this isn't for you. I don't fight platform wars. |

---

## 9. Sales Page Technical Details

### Stack
- **File**: Single `index.html`, zero dependencies
- **CSS**: All inline in `<style>` tag. System font stack. No web fonts.
- **JS**: Minimal (pre-qual radio logic + query param redirect handling). No frameworks.
- **Images**: Author photo (desaturated), Open Graph social image, favicons
- **Size**: ~950 lines

### Design system

| Role | Hex | Usage |
|---|---|---|
| Background | `#fcfbf9` | Warm stone editorial background |
| Text | `#1c1917` | Dark charcoal |
| Accent | `#0f766e` | Deep teal — buttons, pricing, links, phase circles |
| Border | `#e7e5e4` | Subtle structural lines |
| Muted | `#78716c` | Secondary text, attributions |
| Amber stars | `#f59e0b` | Review ratings only |

### Sections (11 total)
1. Hero (pain headline + trust badges)
2. The Problem
3. The Cost of Nothing
4. The Solution (with Foundation Process phases)
5. What's Included (SVG checkmark features)
6. After Delivery (tuning window + retainer options)
7. Pricing (centered card, teal accent border)
8. Who I Am (bio + photo + 3 testimonials)
9. FAQ (12 entries with SVG chevron, native `<details>`)
10. Freebie (Mailcoach email capture + redirect states)
11. CTA (pre-qual Yes/No toggles → Stripe buy button)

### Redirect states
- `?sub=confirmed` — Shows "You're in. Check your inbox." Auto-scrolls to freebie section.
- `?sub=unsubscribed` — Shows "Unsubscribed. No hard feelings."
- `?paid=confirmed` — Shows "Payment received. Invoice from andrei@danielpetrica.com within 24h." Auto-scrolls to CTA.

---

## 10. Integrations

### Stripe
- **Product ID**: `prod_UeXDzk8CYWk71N`
- **Price ID**: `price_1TfE9VIKor3gonB0Bjpg8a3z`
- **Payment link**: `https://buy.stripe.com/3cIcN68A6f898Zq8eCg7e00`
- **Redirect after payment**: `danielpetrica.com/newrelic?paid=confirmed`
- **Tax**: Automatic, self-liability. VAT ID collected.
- **Customer fields**: Name, email, billing address (required), additional info (optional), preferred contact (optional)
- **Invoice**: Not auto-generated by Stripe. Manual invoice sent from andrei@danielpetrica.com within 24h. Use Xolo for partita IVA fattura generation.

### Mailcoach
- **Endpoint**: `https://grozavdev.mailcoach.app/subscribe/d3862d69-6025-4f70-bee4-81da8e338049`
- **Honeypot**: Hidden `username` field off-screen
- **Freebie PDF**: "5 New Relic Alerts Every SaaS Should Have" — content not yet written

### Plausible
- Already configured on danielpetrica.com. Tracks page visits → checkout clicks.

---

## 11. Deployment

### Infrastructure
- **Host**: VPS running Docker + Traefik (existing Ghost setup)
- **Reverse proxy**: Traefik, `PathPrefix(/newrelic)` → nginx:alpine container, priority 100
- **Network**: External `traefik` network, shared with Ghost

### compose.yaml
```yaml
services:
  newrelic-page:
    container_name: danielpetrica_newrelic
    image: nginx:alpine
    volumes:
      - .:/usr/share/nginx/html:ro
      - ./nginx.conf:/etc/nginx/conf.d/default.conf:ro
    labels:
      - traefik.enable=true
      - traefik.http.routers.newrelic-https.rule=Host(`danielpetrica.com`) && PathPrefix(`/newrelic`)
      - traefik.http.routers.newrelic-https.priority=100
      - traefik.http.routers.newrelic-https.tls=true
      - traefik.http.routers.newrelic-https.tls.certresolver=cloudflare
      - traefik.http.routers.newrelic-https.entrypoints=websecure
      - traefik.http.services.newrelic-https.loadbalancer.server.port=80
      - traefik.http.routers.newrelic-http.rule=Host(`danielpetrica.com`) && PathPrefix(`/newrelic`)
      - traefik.http.routers.newrelic-http.entrypoints=web
      - traefik.http.routers.newrelic-http.middlewares=https-redirect
    restart: unless-stopped

networks:
  default:
    external: true
    name: traefik
```

### nginx.conf
Custom config with `/newrelic` alias and trailing slash redirect:
```nginx
server {
    listen 80;
    root /usr/share/nginx/html;

    location = /newrelic {
        return 301 /newrelic/;
    }

    location /newrelic {
        alias /usr/share/nginx/html;
        index index.html;
        try_files $uri $uri/ /newrelic/index.html;
    }
}
```

### Deploy
```bash
git clone git@github.com:danielpetrica/newrelic-foundation.git
cd newrelic-foundation
docker compose up -d
```

To update:
```bash
git pull && docker compose up -d --force-recreate
```

---

## 12. Files in Repository

| File | Purpose |
|---|---|
| `index.html` | Sales page (production) |
| `PLAN.md` | Original planning document |
| `DESIGN-SPEC.md` | Original design specification |
| `MASTER.md` | This file — master reference |
| `README.md` | Public repo readme |
| `compose.yaml` | Docker Compose deployment config |
| `nginx.conf` | Custom nginx config (Traefik PathPrefix support) |
| `og-image.jpg` | Open Graph / social media share image (1200×630) |
| `favicon.ico` | Browser favicon (legacy) |
| `favicon-32.png` | Browser favicon (32px) |
| `apple-touch-icon.png` | Apple Touch Icon (180px) |
| `images/daniel-petrica.jpg` | Author photo (Kyoto, kimono, professional) |

---

## 13. Remaining Work

| Status | Task | Priority |
|---|---|---|
| ❌ | Write freebie PDF — "5 New Relic Alerts Every SaaS Should Have" | 1 |
| ❌ | Deploy to danielpetrica.com/newrelic | 1 |
| ❌ | Build direct outreach list (20-30 SaaS targets) | 2 |
| ❌ | Send agency partnership pitches (5-10 agencies) | 2 |
| ❌ | Create Upwork project catalog listing | 3 |
| ❌ | Write July blog article | 3 |
| ❌ | Submit PHPxTokyo talk proposal | 3 |
| ❌ | Finalize product name (current name is a working placeholder) | 4 |
| ❌ | Get first package-specific testimonials after delivery | 4 |

---

## 14. Objection Handling Reference

All objections are baked into the page's FAQ section:

1. **"€850 seems like a lot"** — Breakdown of 8+ features, 2-3 weeks DIY vs. 1 week done
2. **"Can you do it for less?"** — One price, payment plan available, no feature stripping
3. **"Why you?"** — 8 years dev + New Relic since 2023 + Warrant Hub ISO 27001
4. **"We have Sentry/Datadog/Grafana"** — Not for you, no hard sell
5. **"We can DIY"** — Opportunity cost: dev hours vs. shipping features
6. **"What if we don't like it?"** — 14-day tuning window + Foundation Kit = never locked in
7. **"Am I locked in?"** — Zero commitment beyond setup. Optional retainer.
8. **"CEO dashboards?"** — Out of scope, separate quote at €65/hr
9. **"K8s/AWS/Windows?"** — Not the right fit, happy to refer
10. **"Not ready"** — Blog article in July, package here when you are
11. **"Will this increase my NR bill?"** — Yes, free tier may be exceeded. Estimate before we start.
12. **"GDPR?"** — SSH access only, no data leaves your infra. You remain data controller.

---

## 15. Photography & Visual Assets

- **Author photo**: Professional shot, Kyoto, kimono, green tree canopy background. Taken by a hired photographer. Desaturated (`saturate(30%)`) to match page palette. Full color on hover. 120px circular on desktop, centered above text on mobile.
- **OG image**: 1200×630. Desaturated photo left, headline right, accent teal domain link. Matches page aesthetic.
- **Favicon**: Generated from author photo — 16px .ico, 32px .png, 180px Apple Touch.
- **No other images on the page**. Design philosophy: absence of typical consulting website signifiers IS the differentiation.
