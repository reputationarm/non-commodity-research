---
title: Decision memo
stage: synthesis
purpose: Compress findings into a one-screen memo someone can act on without reading the research.
inputs:
  - DECISION: the decision being made
  - WHO_DECIDES: the audience and what they already know
  - FINDINGS: raw findings, unpolished
  - CONSTRAINTS: time, budget, politics
models_tested:
  - claude-opus-5
status: working
updated: 2026-09-10
---

## When to use

The last step, once the research is done and verified. Its job is compression
with the uncertainty left visible — most memo formats quietly delete the
uncertainty, which is the part the decision-maker most needs.

Do not use it to make thin research look finished. The "what I did not check"
section will expose that anyway, which is the point.

## Prompt

```text
Turn my findings into a memo someone can act on without reading the research.

DECISION: {{DECISION}}
AUDIENCE: {{WHO_DECIDES}}
FINDINGS: {{FINDINGS}}
CONSTRAINTS: {{CONSTRAINTS}}

Format, in this order:

  RECOMMENDATION — one sentence containing an actual verb. Not "consider
  exploring". Recommend something.

  CONFIDENCE — high / medium / low, plus the one thing that would raise it.

  WHY — three points maximum. Each is a finding, not an argument. Lead with the
  one that survives the most hostile reading.

  WHAT THIS COSTS — money, time, opportunity, reversibility. State explicitly
  whether this is a one-way door.

  WHAT WOULD MAKE THIS WRONG — the two findings that would reverse the
  recommendation, and whether either is checkable now.

  WHAT I DID NOT CHECK — gaps in the research, stated plainly. This section is
  not optional and must never be empty.

  NEXT STEP — one action, one owner, one date.

Rules: no throat-clearing, no restating the question back to me, no "in today's
landscape". If the honest recommendation is "do nothing yet", say that and name
what you are waiting for. Length: one screen. If it does not fit on one screen,
the thinking is not finished.
```

## Expected output

Seven labelled blocks on a single screen. The quality check is the gap between
CONFIDENCE and RECOMMENDATION: a firm recommendation at low confidence is fine
if "what would make this wrong" is honest, and dishonest if it isn't.

## Notes

- "What I did not check" is the section people try to cut. Keep it — it is what
  makes the memo survive being wrong later.
- Feeding it unpolished findings works better than pre-summarized ones. Summary
  of a summary loses the specifics that make the WHY section land.
- If the output runs long, the usual cause is too many findings going in. Cut
  the inputs, not the format.

## Changelog

- 2026-09-10 — Created.
