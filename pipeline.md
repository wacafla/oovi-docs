---
layout: default
title: Domain pipeline
nav_order: 3
permalink: /pipeline/
---

# Domain pipeline

## 1. Source contract

Keep each feed file unchanged. Record:

- provider
- file hash
- delivery time
- schema version
- parser version
- row count
- processing status

Minimum row fields:

```text
domain
status
expiry_or_drop_time
registrar
availability_checked_at
tld
source
source_row_id
```

## 2. Normalize

Create these features before external API calls:

| Feature | Example |
|:--|:--|
| root | southjordanroofing |
| tokens | south jordan roofing |
| geo entity | South Jordan, Utah |
| service entity | roofing |
| lexical pattern | geo_service_exact |
| length | 18 |
| hyphens | 0 |
| digits | 0 |
| pronounceability | 0.91 |

## 3. Hard filters

Reject or quarantine candidates based on:

- unsupported TLD
- excessive length
- two or more hyphens
- unexplained digits
- unrecognized language
- adult, pharma, casino, or crypto history
- known trademark or franchise name
- invalid or ambiguous geography
- weak service fit
- prior rejection
- taken, auction, backorder, or aftermarket status

## 4. Availability gate

Only continue when a registrar API confirms that the domain is available for standard registration.

Check twice:

1. Before paid enrichment.
2. Immediately before registration.

Availability is volatile. A positive result is evidence for that moment, not a reservation.

## 5. Progressive enrichment

### Tier A

- DNS and registration status
- Archive snapshot count
- First and last archive date
- Prior page titles and language
- Safe Browsing and blacklist checks
- Historical redirects and topic changes

### Tier B

- referring domains
- top linked pages
- recoverable historical URLs
- anchor-text distribution
- dofollow ratio
- new and lost links
- spam indicators
- keyword and SERP history
- predicted geo keywords and local search demand

### Tier C

- trademark review
- exact-name reputation search
- manual inspection of top referring pages
- market economics
- portfolio overlap
