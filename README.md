# RETIS Digital Authority Platform

The website and digital infrastructure for **RETIS Systems** — a Kenyan cybersecurity risk assessment, security-by-design software, secure hosting, digital growth, and training company based in Nairobi.

This isn't a brochure site. It's built as the infrastructure behind a single funnel:

```
Lead Generation → Cyber Assessments → Consulting → Remediation →
Managed Advisory → Training → Software → Research → Industry Authority
```

Developed via Claude AI.

## Structure

Static HTML/CSS/JS, one file per URL, structured to match the production sitemap directly:

```
/                                   Home
/finsec-360/                        FINSEC 360™ — flagship financial-sector assessment
/cyberguard/                        CyberGuard™ — recurring advisory
/cybersecurity-solutions/           Cybersecurity pillar page
/security-gap-assessment/           Security Gap Assessment
/secure-software-development/       Security by Design pillar page
/cybersecurity-training-kenya/      Training pillar page
/digital-marketing-kenya/           Digital Growth pillar page
/secure-hosting/                    RETIS Secure Host™
/pricing/                           Pricing hub (all five commercial pillars)
/cyber-risk-check/                  Interactive lead-gen scoring tool
/insights/                          Knowledge Hub index
/insights/cybersecurity/what-is-a-cybersecurity-risk-assessment/
                                     Example full Insights article
/kenya-cyber-risk-intelligence/     Original research programme hub
/industries/                        Industries index
/industries/banking/
/industries/saccos/
/industries/fintech/
/industries/psps/
/about/leadership/                  Founder profile (Morris Mureti)
/contact/
/privacy-policy/                    Draft — needs legal review before launch
/terms-of-service/                  Draft — needs legal review before launch
/sitemap.xml
/robots.txt
/assets/                            Logo and founder photography
```

## Design system

Navy / obsidian / gold / purple palette, drawn from the actual RETIS logo (not the cyan originally specified in early planning docs — the real logo took precedence). Typography is IBM Plex Sans (display/body) and IBM Plex Mono (data, scores, methodology steps). Full design system rationale lives in project planning docs, not in this repo.

## Important: absolute paths assume a custom domain

Every internal link and every canonical URL in this codebase is an **absolute path** (e.g. `href="/finsec-360/"`) and schema.org/Open Graph tags point at `https://www.retistech.com/`. This is correct once deployed behind that custom domain (Vercel, Netlify, or GitHub Pages with a CNAME configured), but **will break if served from a GitHub Pages project subpath** like `username.github.io/retis-website/` without a custom domain attached, since `/finsec-360/` would resolve to the root of `github.io` rather than the repo subpath.

## What's real vs. placeholder

- **Pricing** (`/pricing/`, `/secure-hosting/`) is explicitly, visibly marked illustrative — real infrastructure costs and margins haven't been confirmed yet. Do not remove the "Illustrative Pricing" labels without replacing the numbers with confirmed figures.
- **Forms** are client-side only (no backend wired). They need a real lead-capture endpoint (serverless function → CRM/email) before launch.
- **Analytics** scaffold uses a placeholder GA4 Measurement ID (`G-XXXXXXXXXX`) — swap in the real property ID.
- **Legal pages** are structurally complete but explicitly flagged in-page as unreviewed drafts.
- **29 planned pages are not yet built** (remaining service sub-pages, most Insights articles, Insurance/Healthcare/Education/Enterprise industry pages, Case Studies) — internal links to them are live and correct, they just 404 until built.

## Deployment

Static files — deploy to Vercel, Netlify, or any static host. No build step required.
