---
title: Review corpus to operational claims
stage: extraction
purpose: Convert a pile of customer reviews into counted, dated, actionable claims — separating signal from single-voice noise.
inputs:
  - BUSINESS_NAME: the business
  - LOCATION: single location; do not mix locations in one run
  - DATE_RANGE: period the corpus covers
  - REVIEWS: the raw review text
models_tested:
  - claude-opus-5
status: working
updated: 2026-09-10
---

## When to use

When you have a review corpus and need to tell an operator what to actually fix.
The default summary — "customers mention slow service" — is useless because it
carries no count, no trend, and no sense of whether one angry regular is driving
it. This forces all three.

One location per run. Merging locations produces averages that describe nobody.

## Prompt

```text
Below is a corpus of customer reviews for a single business location.

BUSINESS: {{BUSINESS_NAME}}
LOCATION: {{LOCATION}}
PERIOD: {{DATE_RANGE}}
REVIEWS:
{{REVIEWS}}

Convert this into operational claims. A claim is something the operator could
act on, act against, or measure. "Service was bad" is not a claim. "Waits
exceed 20 minutes on weekend evenings" is.

For each claim give:
  - CLAIM: one sentence, in the operator's vocabulary
  - COUNT: how many distinct reviews support it
  - PERIOD: when those reviews cluster, and whether the claim is getting
    better, worse, or holding
  - SEVERITY: does this cost a repeat visit, a rating star, or neither
  - QUOTE: one verbatim fragment, under 15 words, that is most representative
  - CONTROLLABLE: yes / partly / no — is this within the operator's control

Then three separate sections:

  SIGNAL VS NOISE. Which claims rest on a single review, on reviews posted
  within a day of each other, or on accounts whose phrasing suggests one
  author? Flag them separately. Do not fold them into the counts above.

  WHAT THE REVIEWS DO NOT SAY. Name the things customers of this business type
  would normally mention that are absent here. Absence is evidence.

  CONTRADICTIONS. Where reviewers directly disagree, give both sides with
  counts rather than picking a winner.

Rank claims by COUNT x SEVERITY, not by how strongly they are worded.

Do not infer any demographic, health, or identity attribute of a reviewer, and
do not name individual reviewers.
```

## Expected output

A ranked claim table, then the three sections. A good run surfaces at least one
claim in "what the reviews do not say" that the operator has been assuming was
fine.

Watch the CONTROLLABLE column: a corpus where the top three claims are all "no"
means the problem is the location or the market, not the operation.

## Notes

- Ranking by count x severity is what stops the loudest one-star review from
  setting the agenda.
- The signal-vs-noise section is the reason this prompt exists. Without it the
  counts quietly include review-bombing and the operator chases a ghost.
- Feed the output into `synthesis/decision-memo.md` when it goes to a client.
- Do not paste reviewer names in. The claims don't need them.

## Changelog

- 2026-09-10 — Created.
