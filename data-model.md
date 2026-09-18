---
layout: default
title: Data model
nav_order: 9
permalink: /data-model/
---

# Data model

```text
feed_runs
  id, source, file_hash, delivered_at, rows_received, schema_version, status

domains
  id, fqdn, root, tld, first_seen_at, current_status, registration_status

domain_observations
  domain_id, feed_run_id, source_row_id, availability_checked_at, drop_time, raw_payload

features
  domain_id, parser_version, tokens, geo_json, service_json, lexical_json

enrichments
  domain_id, provider, data_type, payload, fetched_at, expires_at, cost

keyword_candidates
  domain_id, keyword, service_cluster, geo_id, intent, generation_source

keyword_metrics
  keyword_candidate_id, provider, location_code, measured_volume, modeled_volume,
  cpc, competition, monthly_history, confidence, fetched_at

scores
  domain_id, model_version, components_json, penalties_json, raw_score,
  confidence, adjusted_score, decision

reviews
  domain_id, reviewer_type, reviewer_id, prompt_version, outcome, reasons

registrations
  domain_id, registrar, registered_at, registration_term, renewal_price,
  approved_by, thesis

sites
  domain_id, site_class, template_version, wp_url, launched_at, status

performance_daily
  site_id, date, impressions, clicks, calls, forms, qualified_leads, revenue
```

The domain is the durable identity. Every feed observation, evidence snapshot, predicted keyword, score, review, registration, site, and outcome attaches to it.
