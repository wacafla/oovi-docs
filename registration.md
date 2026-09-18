---
layout: default
title: Drop-day registration
nav_order: 7
permalink: /registration/
---

# Drop-day registration

The operator approves candidates before the drop. The machine handles timing, final checks, registrar routing, duplicate prevention, and outcome logging.

## Ranked event queue

Each card shows:

- domain, current registry state, and predicted drop window
- score, confidence, rank, and maximum acceptable normal registration price
- predicted keyword clusters and target geography
- measured and modeled local search volume
- estimated monthly lead value
- backlink, archive, safety, and trademark evidence
- portfolio overlap and intended site thesis
- registrar routes and readiness status

## Queue controls

- target two or three registrations per day; absolute maximum five
- normal registration only; reject premium, auction, aftermarket, and backorder paths
- maximum one domain per exact geo/service pair
- maximum two domains in the same service category per day
- require an approved build or hold thesis
- require a fresh lifecycle check before attempts begin
- keep ranked fallbacks for every drop window
- record approver, evidence version, score version, and reason

## Execution rules

1. Lock the candidate event so only one worker can own it.
2. Recheck RDAP/WHOIS state and registrar availability near the drop window.
3. Send attempts through the preferred registrar, with a second registrar as a controlled fallback when allowed.
4. Treat timeouts as unknown, not failures; reconcile before retrying.
5. Stop all routes when registration is confirmed.
6. Verify ownership, renewal settings, nameservers, DNSSEC policy, and final charged price.
7. Write the result to the decision ledger whether the attempt succeeds or fails.

Registration can be automated after human approval because timing is machine work. Autonomous selection should wait until the system has enough measured outcomes to quantify false positives, false negatives, and human reversals.
