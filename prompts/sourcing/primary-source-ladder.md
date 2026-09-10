---
title: Primary source ladder
stage: sourcing
purpose: Force a descent from primary records to general press, and make the model report what it could not find.
inputs:
  - QUESTION: one falsifiable question, not a topic
  - SCOPE: geography, timeframe, industry
models_tested:
  - claude-opus-5
status: working
updated: 2026-09-10
---

## When to use

When you need provenance rather than volume — anything that will be quoted,
put in front of a client, or used to justify spending money. The ladder stops
the model from answering entirely out of general press and aggregators, which
is where it goes by default.

Not for background reading where a rough map is fine.

## Prompt

```text
I need sources on the following question, and I care about provenance more
than volume.

QUESTION: {{QUESTION}}
SCOPE: {{SCOPE}}

Work down this ladder. Report what you find at each rung before moving to the
next. Do not skip a rung because a lower one is easier to search.

  Rung 1 — The record itself: filings, dockets, permits, licenses, patents,
           standards, primary datasets, official registries.
  Rung 2 — The party's own words: earnings calls, investor decks, job
           postings, changelogs, documentation, pricing pages, terms.
  Rung 3 — People with direct exposure: operators, former employees,
           suppliers, customers, regulators. Name roles and where they
           publish. Do not compile contact details for individuals.
  Rung 4 — Trade press and specialist analysts who cite rungs 1-3.
  Rung 5 — General press and aggregators. Treat these as pointers only.

For every source, give:
  - what specifically it can answer, not a general description of it
  - its date, and whether that date makes it stale for this question
  - the party's incentive to shade the truth, in a short phrase
  - whether you are confident it exists, or inferring that it should exist

Then, in a separate section: WHAT I COULD NOT FIND. List the rungs that came
back empty and say what that emptiness might itself mean — a young market, a
private company, a regulatory gap, or simply a failed search on your part.

Do not fill gaps with plausible-sounding sources. An honest empty rung is
worth more to me than a citation I have to go and disprove.
```

## Expected output

Five rungs, each either populated or explicitly empty, then the gap section.
Rungs 1-2 should carry the weight; if the answer lives entirely at rungs 4-5,
that is itself the finding — the question may not be publicly answerable.

## Notes

- The last paragraph is load-bearing. Removing it produces confident citations
  to documents that don't exist.
- Verify anything from rung 1 before it leaves your desk. The model is good at
  knowing which registry would hold a record and unreliable about what the
  record says.
- The "incentive to shade" line is the most reused part of the output — it
  survives into the memo.

## Changelog

- 2026-09-10 — Created.
