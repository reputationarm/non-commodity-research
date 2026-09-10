# Non-Commodity Research

A personal library of the prompts I use for research — the ones worth keeping,
versioning, and reusing rather than retyping from scratch each time.

"Non-commodity" is the bar: if a prompt just asks a model to summarize something,
it doesn't belong here. What belongs here are prompts that encode a real method —
how to frame a question, where to look, what to extract, how to pressure-test a
claim before it gets repeated.

## Layout

```
prompts/
  framing/        scoping the question, defining what a good answer looks like
  sourcing/       finding primary sources, operators, filings, people
  extraction/     pulling structured facts out of documents and transcripts
  analysis/       comparison, decomposition, causal reasoning
  synthesis/      turning findings into a memo, brief, or recommendation
  verification/   fact-checking, steelmanning, red-teaming a conclusion
templates/
  prompt-template.md   the front-matter + section format every prompt uses
```

## Current prompts

| Prompt | Stage | What it does |
|---|---|---|
| [question-to-decision](prompts/framing/question-to-decision.md) | framing | Turns a vague ask into the decision it serves, with a stopping rule |
| [primary-source-ladder](prompts/sourcing/primary-source-ladder.md) | sourcing | Forces primary records before press, and reports what it could not find |
| [review-corpus-to-claims](prompts/extraction/review-corpus-to-claims.md) | extraction | Reviews into counted, dated, actionable claims, with noise flagged |
| [competitor-teardown](prompts/analysis/competitor-teardown.md) | analysis | Reads a competitor from observable evidence, structural moat vs polish |
| [steelman-then-break](prompts/verification/steelman-then-break.md) | verification | Argues your side well, then attacks it, and can return "holds" |
| [decision-memo](prompts/synthesis/decision-memo.md) | synthesis | One screen, uncertainty left visible |

They chain: framing feeds sourcing, sourcing and extraction feed analysis,
analysis goes through verification before it reaches synthesis. Each prompt's
notes say which one it hands off to.

## Conventions

- One prompt per file. Filename is kebab-case and describes the job:
  `competitor-teardown.md`, not `prompt3.md`.
- Every file starts with the YAML front matter in
  [`templates/prompt-template.md`](templates/prompt-template.md).
- The prompt body lives in a fenced block so it can be copied verbatim without
  picking up the surrounding notes.
- Placeholders use `{{DOUBLE_BRACES}}` so they're easy to spot and replace.
- Notes on what worked, what failed, and which model you ran it against go at the
  bottom. That log is the point — it's what makes a prompt reusable later.

## Using a prompt

1. Find it under `prompts/<stage>/`.
2. Copy the fenced block.
3. Replace every `{{PLACEHOLDER}}`.
4. If you change the prompt in a way that helped, commit the change and add a
   line to its changelog.

## Adding a prompt

```bash
cp templates/prompt-template.md prompts/analysis/my-new-prompt.md
```

Fill in the front matter, paste the prompt, commit.
