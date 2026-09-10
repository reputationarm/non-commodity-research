---
title: Steelman then break
stage: verification
purpose: Attack a conclusion you already believe, in an order that prevents lazy objections and reflexive agreement.
inputs:
  - CONCLUSION: what you believe, stated flatly
  - EVIDENCE: what you relied on
  - PLANNED_ACTION: what you will do if it holds
models_tested:
  - claude-opus-5
status: working
updated: 2026-09-10
---

## When to use

Between reaching a conclusion and acting on it — especially when the conclusion
is one you wanted to reach, or when the action is expensive or hard to reverse.

The steelman comes first on purpose. Ask a model to critique something cold and
it produces a list of hedges it doesn't believe; make it argue your side well
first, and the subsequent attack has to clear a real bar.

## Prompt

```text
I have reached a conclusion. Attack it.

CONCLUSION: {{CONCLUSION}}
EVIDENCE I RELIED ON: {{EVIDENCE}}
WHAT I WILL DO IF IT HOLDS: {{PLANNED_ACTION}}

Work in this order. Do not shortcut it.

1. STEELMAN. Restate my conclusion in its strongest form — stronger than I put
   it, with the best version of my reasoning. If you cannot make it strong,
   say what is missing before you continue.

2. LOAD-BEARING CLAIMS. Which specific claims is the conclusion resting on?
   Mark each: verified / plausible / assumed. Anything both load-bearing and
   assumed is the real risk. Say so directly.

3. THE STRONGEST COUNTER-CASE. Argue the opposite as someone who believes it,
   not as a devil's advocate going through the motions. Use my own evidence
   against me where it can be turned.

4. WHAT I WOULD EXPECT TO SEE. If my conclusion is true, what else would be
   true that I have not checked? If it is false, what would I expect to see
   that I may have already dismissed? Give me a concrete check for each.

5. FAILURE MODES OF MY EVIDENCE. Survivorship, selection, recency, small
   samples, sources with an incentive, my own prior. Name only the ones my
   evidence is actually vulnerable to — not the full list.

6. VERDICT. One of: holds / holds with conditions / does not hold on this
   evidence. Then name the single cheapest thing that would move it.

Do not be agreeable. But if it holds, say it holds and stop — manufactured
objections waste my time exactly as much as flattery does.
```

## Expected output

Six sections ending in a one-word verdict. Section 2 is the one to read twice:
the pattern to watch for is a claim marked "assumed" that everything else
depends on.

A verdict of "holds" with a short section 3 is a legitimate result. Treat a
long, strained section 3 as evidence the model is performing rather than
finding.

## Notes

- The closing line is what makes the "holds" verdict trustworthy. Without it the
  model manufactures objections to look rigorous.
- State the conclusion flatly. Hedged input ("it seems X might") gives it
  nothing solid to push against and the whole run goes mushy.
- Including PLANNED_ACTION visibly changes the output — it calibrates the
  scrutiny to the stakes.

## Changelog

- 2026-09-10 — Created.
