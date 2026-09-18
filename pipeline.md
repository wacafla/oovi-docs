---
layout: default
title: Domain pipeline
nav_order: 4
permalink: /pipeline/
---

# Domain pipeline

## 1. Import directly into PostgreSQL

The ingest object is one provider file per feed run, not one S3 object and not one API call per domain.

1. Download the daily CSV, TSV, ZIP, or gzip file to ephemeral disk.
2. Calculate SHA-256 and create a `feed_runs` row.
3. Decompress as a stream when possible.
4. Use PostgreSQL `COPY` into an unlogged staging table.
5. Validate row count, required columns, encoding, and malformed-row rate.
6. Merge new observations and update canonical domains with set-based SQL.
7. Commit the run summary, then remove the temporary file.

Preserve the source row in `jsonb` if replay or audit matters. PostgreSQL is the system of record; S3 can be added later only if retaining the original vendor files becomes useful.

Minimum source fields:

```text
domain
reported_expiration_at
registrar
tld
source
source_row_id
raw_payload
```

## 2. Early normalization and filtering

Create lexical, service, and geographic features without external paid calls. Reject unsupported TLDs, poor names, excluded industries, obvious trademarks, irrelevant geographies, and previous rejects.

The output is a lifecycle watchlist, not a registration list.

## 3. Lifecycle monitoring

Poll registry status on a schedule that increases in frequency as the expected transition approaches.

| State | Suggested check rate | Action |
|:--|:--|:--|
| Expiring or grace period | Daily | Keep or close based on renewal evidence |
| Redemption period | Every 6–12 hours | Refresh cheap evidence and capacity forecast |
| `pendingDelete` | Every 15–60 minutes | Confirm drop window and start full intelligence |
| Available | Immediate | Attempt only if pre-approved |
| Renewed, transferred, or auction-only | Stop | Close with reason |

Rate limits and registry terms override these starting values.

## 4. Full intelligence

Run expensive calls only on confirmed `pendingDelete` candidates:

- complete archive and abuse review
- referring domains, anchors, linked pages, and lost links
- predicted service and geo keyword clusters
- city, county, metro, and state search demand
- CPC, commercial intent, local SERPs, and rankability
- trademark and reputation review
- portfolio overlap and expected lead value

## 5. Rank by drop event

Create a separate queue for each drop window. Rank candidates by adjusted opportunity, evidence confidence, expected lead value, registration feasibility, and portfolio constraints. Keep several approved fallbacks because competitors may capture the first choices.

## 6. Attempt and record

Immediately before the window, refresh status and disqualifiers. At the predicted time, submit idempotent registration attempts through configured registrars. Stop further attempts after confirmed success. Record every request, response, price class, and outcome.
