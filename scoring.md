---
layout: default
title: Scoring and AI review
nav_order: 5
permalink: /scoring/
---

# Scoring and AI review

## Deterministic score

Score each component from 0 to 100.

```text
Opportunity =
  0.22 × SEO evidence
+ 0.20 × Local intent
+ 0.20 × Geo keyword value
+ 0.14 × Brand usability
+ 0.12 × Historical fit
+ 0.12 × Portfolio fit
− Risk penalties
```

Geo keyword value now includes local search volume, CPC, commercial intent, expected qualified leads, rankability, and evidence confidence.

## Thresholds

| Adjusted score | Decision |
|--:|:--|
| 85–100 | Registration candidate |
| 75–84 | Manual review |
| 65–74 | Watchlist |
| Below 65 | Reject |

Confidence-adjust the score:

```text
adjusted_score = raw_score × (0.6 + 0.4 × evidence_confidence)
```

## Risk penalties

- questionable anchors: −10 to −40
- repeated topic changes: −10 to −30
- weak trademark similarity: −15
- one dominant referring domain: −5 to −20
- portfolio saturation: −5 to −25
- modeled keyword demand with weak evidence: −5 to −20

Malware, phishing, strong trademark conflicts, casino/pharma link profiles, or clear deindexing evidence are hard disqualifiers.

## AI finalist review

Send only 20–50 structured evidence packets.

Required response:

```json
{
  "decision": "register | review | reject",
  "recommended_use": "money_site | redirect | brand | hold",
  "best_service": "garage floor coatings",
  "best_market": "South Jordan, Utah",
  "best_keyword_clusters": ["garage floor coating", "polyaspartic floor"],
  "estimated_monthly_geo_volume": 320,
  "estimated_monthly_lead_value": 4800,
  "score_adjustment": -4,
  "confidence": 0.88,
  "strengths": [],
  "risks": [],
  "disqualifiers": [],
  "required_human_checks": []
}
```

Run a second adversarial review on the top five: find the strongest reason not to register each domain.
