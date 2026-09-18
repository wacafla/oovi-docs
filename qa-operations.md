---
layout: default
title: QA and operations
nav_order: 8
permalink: /qa-operations/
---

# QA and operations

## Launch gate

| Gate | Required checks |
|:--|:--|
| Technical | HTTPS, canonicals, sitemap, robots, status codes, broken links, performance |
| Conversion | Tap-to-call, forms, spam control, CallRail, attribution, conversion events |
| Content | No placeholders, wrong cities, duplicates, contradictions, or invented claims |
| SEO | Title/H1 alignment, schema validation, internal links, unique intent, indexability |
| Legal | Trademark, privacy, SMS language, terms, licenses, claims |
| Visual | Mobile spacing, readable type, image crops, layout stability |

A required failure blocks launch.

## Automation

| Job | Technology | Failure behavior |
|:--|:--|:--|
| Site provisioning | WP-CLI + GitHub Actions | Roll back and open ticket |
| Content injection | WordPress REST API | Retry idempotently |
| Browser QA | Playwright | Block publish |
| Performance | Lighthouse CI | Block on agreed budget |
| Crawl QA | Screaming Frog | Block critical errors |
| DNS | Cloudflare API | Stop and alert |
| Sitemap submission | Search Console API | Retry and report |
| Lead monitoring | CallRail + CRM webhook | Alert immediately |

## Observability

Track:

- feed funnel counts
- enrichment cost per finalist
- API failures and rate limits
- human reversal rate
- registrations per service and market
- indexing time
- retained backlinks
- keyword movement
- calls and forms
- qualified lead rate
- revenue and profit
