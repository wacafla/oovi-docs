---
layout: default
title: Data model
nav_order: 10
permalink: /data-model/
---

# Data model

```text
feed_runs
  id, source, source_filename, sha256, fetched_at, rows_received,
  rows_loaded, schema_version, parser_version, status, error_summary

feed_stage_expiring                         -- UNLOGGED; truncate per successful merge
  feed_run_id, source_row_id, domain, reported_expiration_at, registrar, raw_payload

domains
  id, fqdn, root, tld, first_seen_at, current_lifecycle_state, watch_status

domain_observations
  domain_id, feed_run_id, source_row_id, reported_expiration_at, raw_payload, observed_at

lifecycle_observations
  domain_id, source, registry_status, registrar_status, registry_expiration_at,
  registrar_expiration_at, observed_at, raw_payload

drop_predictions
  domain_id, rule_version, predicted_drop_at, window_start, window_end,
  confidence, evidence_json, calculated_at

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
  confidence, adjusted_score, decision, scored_at

drop_queue
  domain_id, drop_prediction_id, rank, priority, approved_by, approved_at,
  max_normal_price, route_plan_json, state

registration_attempts
  domain_id, drop_queue_id, registrar, idempotency_key, attempted_at,
  request_state, response_code, result, charged_price, response_json

registrations
  domain_id, registrar, registered_at, registration_term, renewal_price,
  approved_by, thesis

sites
  domain_id, site_class, template_version, wp_url, launched_at, status

performance_daily
  site_id, date, impressions, clicks, calls, forms, qualified_leads, revenue
```

The domain is the durable identity. Keep every lifecycle observation so the drop model can be audited and improved. Keep observed timestamps separate from predicted timestamps, and never overwrite historical scores or evidence.
