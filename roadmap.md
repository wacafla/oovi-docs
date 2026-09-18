---
layout: default
title: 90-day roadmap
nav_order: 11
permalink: /roadmap/
---

# 90-day roadmap

## Weeks 1–2: PostgreSQL ingestion

- schedule feed download and direct `COPY` ingestion
- create unlogged staging and canonical tables
- normalize and deduplicate domains
- create service and geography taxonomies
- record checksums, parser versions, counts, and failures
- expose daily funnel counts

## Weeks 3–4: lifecycle watchlist

- implement cheap deterministic filters
- integrate RDAP with a controlled WHOIS fallback
- store state changes as append-only observations
- implement registry-specific drop-window rules
- close renewed, transferred, and auction-only candidates
- validate predictions against actual drops

## Weeks 5–6: full intelligence

- trigger paid enrichment only for confirmed `pendingDelete` candidates
- add archive, safety, backlink, and anchor checks
- predict keyword clusters
- request city, county, metro, and state keyword metrics
- calculate modeled geo demand, lead value, and confidence
- publish the first drop-day ranked report

## Weeks 7–8: scoring and execution

- version scoring weights and risk rules
- add structured AI and adversarial reviews
- build the approval and drop-queue screen
- integrate at least two registrar APIs
- implement locks, idempotency, reconciliation, and attempt logs
- run dry tests without purchase calls

## Weeks 9–10: WordPress factory

- finalize the block theme and pattern library
- define the site-brief schema
- automate staging builds and content injection
- configure measurement and call tracking
- automate technical and visual QA

## Weeks 11–12: controlled operation

- enable human-approved timed registration attempts
- launch a small cohort
- measure capture rate, indexing, rankings, calls, and leads
- inspect missed and rejected candidates
- adjust lifecycle rules and scoring weights
- document operator procedures and incident recovery

By the end of week four, the system should produce a credible lifecycle watchlist. By the end of week eight, it should produce and execute a human-approved ranked queue for each drop window.
