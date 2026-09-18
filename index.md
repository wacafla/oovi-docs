---
layout: default
title: Domain Intelligence Playbook
nav_order: 1
description: Production blueprint for selecting and building the best expired domains for local service SEO.
permalink: /
---

# Domain Intelligence Playbook
{: .fs-9 }

Turn hundreds of thousands of daily expired-domain rows into zero to five defensible local service assets. The normal target is two or three registrations per day.
{: .fs-6 .fw-300 }

[Start with the machine architecture]({{ '/architecture/' | relative_url }})
[Review the scoring model]({{ '/scoring/' | relative_url }})

---

## Operating target

| Stage | Expected daily volume |
|:--|--:|
| Raw feed | 100,000–500,000 |
| Hard-filter survivors | 5,000–25,000 |
| Enriched candidates | 250–1,500 |
| AI-reviewed finalists | 20–50 |
| Human review queue | 10–20 |
| Registered domains | 0–5 |

The correct result can be zero. The limit is a ceiling, not a quota.

## Core rules

Evidence before opinion
: Store raw evidence separately from scores and AI explanations.

Cheap decisions first
: Do not pay for SEO data until deterministic rules have removed most candidates.

Standard registration only
: Exclude auctions, backorders, premium aftermarket listings, and taken domains.

Human registration gate
: Keep final registration approval human until at least 60 days of measured results.

Business outcomes win
: Optimize for qualified lead profit and asset value, not third-party SEO metrics alone.

## Recommended stack

| Layer | Recommendation |
|:--|:--|
| Durable orchestration | Temporal Cloud |
| File landing | Amazon S3 + EventBridge |
| Data processing | Python + Polars |
| System of record | PostgreSQL |
| SEO and keyword evidence | DataForSEO |
| AI review and generation | OpenAI Responses API |
| Review console | Next.js |
| Site factory | WordPress + WP-CLI + REST API |
| Build automation | GitHub Actions |
| QA | Playwright + Lighthouse CI + Screaming Frog |
| DNS and edge | Cloudflare |
| Measurement | Search Console + GA4 + CallRail |
| Reporting | Metabase |
