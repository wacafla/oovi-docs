---
layout: default
title: Domain Intelligence Playbook
nav_order: 1
description: Production blueprint for finding and evaluating local-service domains before they drop.
permalink: /
---

# Domain Intelligence Playbook
{: .fs-9 }

Turn hundreds of thousands of expiring-domain rows into a ranked drop-day list of zero to five defensible local-service assets. The normal target is two or three registrations per day.
{: .fs-6 .fw-300 }

[Start with the machine architecture]({{ '/architecture/' | relative_url }})
[Review the scoring model]({{ '/scoring/' | relative_url }})

---

## Operating target

| Stage | Expected daily volume |
|:--|--:|
| Expiring-feed rows | 100,000–500,000 |
| Early-filter survivors | 5,000–25,000 |
| Lifecycle watchlist | 250–1,500 |
| Confirmed `pendingDelete` candidates | 20–100 |
| Ranked drop-day queue | 5–20 |
| Registered domains | 0–5 |

The correct result can be zero. The limit is a ceiling, not a quota.

## Core rules

Evidence before opinion
: Store raw evidence separately from scores and AI explanations.

Cheap decisions first
: Do not pay for SEO data until deterministic rules have removed most candidates.

Expiration is not the drop
: Treat the published expiration date as a discovery signal. Monitor registry status and calculate the actionable drop window only after `pendingDelete` is confirmed.

Standard registration only
: Exclude auctions, backorders, premium aftermarket listings, and domains that require anything beyond normal registration price.

Human approval, automated timing
: Approve the ranked queue before drop day, then let the registrar integration submit registration attempts at the predicted drop time.

Business outcomes win
: Optimize for qualified lead profit and asset value, not third-party SEO metrics alone.

## Recommended stack

| Layer | Recommendation |
|:--|:--|
| Scheduling and orchestration | Temporal Cloud or cron for the MVP |
| Feed ingestion | Python + PostgreSQL `COPY` |
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

No S3 layer is required for the first version. Download the provider file to temporary local storage, load it into an unlogged PostgreSQL staging table, merge it into canonical tables, record its checksum and import result, then delete the temporary file.
