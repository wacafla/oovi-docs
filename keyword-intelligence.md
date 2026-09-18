---
layout: default
title: Geo keyword intelligence
nav_order: 4
permalink: /keyword-intelligence/
---

# Geo keyword intelligence

Predict the queries a domain could rank for, then measure demand and commercial value in the exact geography.

This stage runs after `pendingDelete` is confirmed and the domain passes safety and history checks, but before final scoring.

## Keyword-generation process

Generate candidates from five sources:

1. **Parsed domain entities** — service, city, county, state, and brand terms found in the name.
2. **Service taxonomy** — primary services, subservices, materials, problems, and job types.
3. **Commercial modifiers** — contractor, company, installer, repair, replacement, cost, quote, near me, emergency, and best.
4. **Local modifiers** — city, neighborhood, county, metro, ZIP, state abbreviation, and nearby cities inside the realistic service radius.
5. **SERP expansion** — related searches, People Also Ask topics, competitor keywords, and common keyword combinations.

Example for a South Jordan garage-floor domain:

```text
garage floor coating south jordan
garage floor epoxy south jordan
polyaspartic garage floor south jordan
garage floor coating near me
garage floor coating cost south jordan
epoxy garage floor salt lake county
garage floor coating draper
garage floor coating riverton
```

## Prevent keyword explosion

Do not submit every possible combination.

Apply rules before the SEO API:

- service must match the approved taxonomy
- geography must be inside the intended service area
- phrase must have clear local or commercial intent
- remove unnatural word order
- deduplicate close variants
- group singular, plural, and spelling variants
- cap initial keyword candidates at 200 per domain
- expand only the strongest clusters

## Geo-specific SEO API lookup

Use DataForSEO Keywords Data or Google Ads search-volume endpoints with:

- keyword
- location code or location name
- language code
- search network
- device when required

Store:

```text
keyword
normalized_keyword
service_cluster
intent
location_code
location_name
language_code
monthly_search_volume
monthly_search_history
cpc
competition
competition_index
low_top_of_page_bid
high_top_of_page_bid
api_timestamp
api_source
```

## Geographic fallback ladder

City-level volume is often sparse. Query demand at several levels:

1. city
2. county
3. metro or DMA
4. state

Never treat missing city volume as zero demand. Estimate the city share from broader data and label it as modeled.

```text
estimated_city_volume =
  metro_volume
  × city_population_share
  × service_demand_adjustment
  × local_SERP_adjustment
```

Keep the measured and modeled values separate.

## Commercial value model

CPC is a useful commercial-intent signal. It is not the value of the keyword.

```text
expected_monthly_clicks =
  geo_monthly_volume × expected_organic_CTR_at_target_position

expected_monthly_leads =
  expected_monthly_clicks × site_conversion_rate

expected_qualified_leads =
  expected_monthly_leads × qualified_lead_rate

expected_monthly_lead_value =
  expected_qualified_leads × value_per_qualified_lead
```

For an owned or joint-venture service company, replace lead value with expected gross profit per closed job:

```text
expected_monthly_gross_profit =
  expected_monthly_leads
  × appointment_rate
  × close_rate
  × gross_profit_per_job
```

## Keyword opportunity score

```text
keyword_opportunity =
  normalized_demand
  × commercial_intent
  × expected_lead_value
  × local_relevance
  × rankability
  × evidence_confidence
```

Calculate domain-level keyword value from the strongest non-overlapping clusters. Do not add hundreds of closely related keyword volumes because this double-counts the same demand.

## Confidence rules

| Evidence | Confidence |
|:--|:--|
| Direct city-level API volume with monthly history | High |
| Metro volume allocated with reliable city share | Medium |
| State volume allocated to a small city | Low |
| CPC but no usable volume | Low |
| AI-predicted keyword with no SERP or API validation | Very low |

The scoring system must penalize low-confidence demand estimates.
