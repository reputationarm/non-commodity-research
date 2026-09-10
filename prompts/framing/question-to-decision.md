---
title: Question to decision
stage: framing
purpose: Turn a vague research request into the decision it serves, with falsifiable sub-questions and a stopping rule.
inputs:
  - RAW_REQUEST: the request exactly as it was given to you, unpolished
  - KNOWN_CONTEXT: what you already know that bears on it
models_tested:
  - claude-opus-5
status: working
updated: 2026-09-10
---

## When to use

Run this before any other prompt when someone hands you a research ask that
sounds reasonable but doesn't say what it's for — "look into X", "what's going
on with Y". It is the cheapest way to avoid a week of research that answers a
question nobody needed answered.

Not for use when the decision is already explicit and agreed. Skip it then.

## Prompt

```text
You are helping me scope a research task before any research happens.

Here is the request as it was given to me:
{{RAW_REQUEST}}

Context I already have:
{{KNOWN_CONTEXT}}

Do not answer the request. Instead produce the following:

1. DECISION. State the decision this research is meant to serve, in one
   sentence of the form "Whether to X, given Y." If the request could serve
   more than one decision, list each and mark which you believe is primary.
   If it serves no decision at all, say so plainly — that is a finding, not a
   failure.

2. WHAT WOULD CHANGE MY MIND. For the primary decision, name the two or three
   findings that would flip it. Be specific enough that I would recognize one
   if I saw it.

3. SUB-QUESTIONS. Break the request into 4-7 questions each answerable with
   evidence. Every sub-question must be falsifiable: if no possible finding
   could make the answer "no", rewrite it. Order them by how much they would
   move the decision, not by how easy they are to research.

4. CHEAPEST DISCRIMINATING TEST. For each sub-question, name the single
   fastest source or check that would materially narrow it.

5. STOPPING RULE. State the condition under which I should stop researching
   and decide anyway — expressed in time, in sources consulted, or in
   diminishing returns.

6. WHAT I AM ASSUMING. List the assumptions embedded in the request itself
   that, if wrong, make the whole exercise pointless.

Be terse. No preamble.
```

## Expected output

Six labelled sections, most under a screen total. The tell that it worked:
section 6 names an assumption you hadn't noticed you were making, and the
sub-questions in section 3 are ordered differently from how you'd have written
them.

If every sub-question is answerable by a single search, the framing is too
shallow — the request probably needed no research at all.

## Notes

- The "if it serves no decision, say so" clause matters. Without it the model
  invents a decision to be helpful, and you research a fiction.
- Pairs directly into `sourcing/primary-source-ladder.md`: feed it the
  top-ranked sub-question, not the original request.
- Failure mode: with thin `KNOWN_CONTEXT` the assumptions section gets generic.
  Paste more than feels necessary.

## Changelog

- 2026-09-10 — Created.
