---
title: Competitor teardown
stage: analysis
purpose: Read a competitor from observable evidence only, separating structural advantage from surface polish.
inputs:
  - COMPETITOR: name, and the material you are giving it to read
  - OUR_POSITION: how you currently position against them
  - DECISION: what this teardown is meant to inform
models_tested:
  - claude-opus-5
status: working
updated: 2026-09-10
---

## When to use

Before pricing changes, positioning work, or deciding whether to chase a segment
a competitor already holds. The discipline it adds is the split in section 5 —
most teardowns list everything the competitor does well and call it an
advantage, which tells you nothing about what you can take from them.

## Prompt

```text
Tear down a competitor using only evidence I could verify myself.

COMPETITOR: {{COMPETITOR}}
OUR POSITION: {{OUR_POSITION}}
WHAT I AM DECIDING: {{DECISION}}

Structure:

1. WHAT THEY SELL, in their words. Quote their own framing. Then restate it in
   plain language with the marketing stripped out.

2. WHO IT IS FOR. Infer the buyer from observable signals only — pricing tiers,
   integrations, job postings, case study logos, support hours, contract terms.
   Cite the signal behind each inference and mark inferences as inferences.

3. HOW THEY MAKE MONEY. The unit of pricing, what scales the bill, what is
   free, and where margin plausibly sits. If pricing is hidden, say so and
   infer from the sales motion instead.

4. WHAT THEY ARE BUILDING. Read job postings, changelogs, docs and talks as a
   roadmap. Distinguish shipped from announced from merely staffed-for.

5. STRUCTURAL ADVANTAGE. What would be genuinely hard for us to copy — data,
   distribution, switching costs, regulatory position, capital? Keep this
   separate from things that only look hard: brand, polish, feature count.

6. WHERE THEY ARE EXPOSED. Their positioning forces trade-offs. Name the
   customers those trade-offs leave badly served, and say whether that segment
   is one we can actually reach.

7. SO WHAT, FOR MY DECISION. Three sentences. No hedging.

Rules: every claim carries its evidence inline. Where you have no evidence,
write "unknown" rather than reasoning your way to a plausible answer. Never
repeat their marketing language as though it were established fact.
```

## Expected output

Seven sections, evidence inline throughout, and a visible number of "unknown"
entries. A teardown with no unknowns in it was written from vibes.

Section 5 should be short. If it lists more than three genuine structural
advantages, either the competitor is unassailable or the model has smuggled
polish into the list — check which.

## Notes

- Give it real material to read. Run without source text it produces a
  confident, generic teardown of a company that doesn't exist.
- Section 6 is where the useful output usually is, and it is the section models
  skimp on. Push back and ask it to name the underserved segment concretely.
- Run `verification/steelman-then-break.md` on section 7 before acting on it.

## Changelog

- 2026-09-10 — Created.
