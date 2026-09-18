# Non-Commodity Content Research System

## Purpose

Use this system to find and develop content that adds facts, experience, judgment, or context competitors cannot reproduce by summarizing existing pages.

This is not a generic content-writing prompt. It is a research and briefing system. It begins with a broad buyer question, follows the decision branches an AI search experience exposes, identifies information gaps, verifies what can be verified, and turns the strongest gaps into answer-first content briefs.

## What counts as non-commodity content

Content is non-commodity when it contains one or more of the following:

- First-party facts: prices, ranges, timelines, quantities, policies, warranties, process steps, service limits, inventory, performance data, or outcomes.
- Expert judgment: diagnostic thresholds, tradeoffs, selection criteria, warning signs, exceptions, failure modes, or recommendations based on real experience.
- Contextual facts: local rules, industry regulations, environmental conditions, buyer constraints, technical dependencies, or market-specific realities.
- Original evidence: interviews, observations, photos, examples, tests, datasets, case studies, or anonymized customer patterns.
- Verifiable proof: license details, certifications, methodology, public records, product specifications, or primary-source citations.

Generic claims such as “trusted,” “high quality,” “full service,” “innovative,” “affordable,” and “customer focused” do not qualify without the specific evidence behind them.

---

# Part 1: Client Input Sheet

Complete as many fields as possible. Use `UNKNOWN` when the client has not supplied an answer. Never fill an unknown client fact with a guess.

## Required inputs

```text
CLIENT_NAME:
BUSINESS_CATEGORY:
PRIMARY_OFFER:
TARGET_AUDIENCE:
MARKET_OR_JURISDICTION:
PAGE_OR_TOPIC_TO_IMPROVE:
PRIMARY_BUYER_GOAL:
WEBSITE_URL:
```

## Recommended inputs

```text
BUYER_TYPE: [consumer | business | government | mixed]
BUYING_STAGE: [problem-aware | evaluating | ready to buy | post-purchase]
TRANSACTION_TYPE: [local service | professional service | ecommerce | SaaS | product | other]
GEOGRAPHIC_SCOPE:
PRICE_MODEL:
TYPICAL_PRICE_OR_RANGE:
SALES_CYCLE:
DELIVERY_TIMELINE:
SERVICE_OR_PRODUCT_LIMITS:
COMMON_CUSTOMER_QUESTIONS:
COMMON_OBJECTIONS:
COMMON_FAILURE_MODES:
DECISION_CRITERIA:
ALTERNATIVES_CUSTOMERS_COMPARE:
PROPRIETARY_PROCESS:
WARRANTIES_OR_GUARANTEES:
CREDENTIALS_OR_LICENSES:
REGULATIONS_OR_STANDARDS:
KNOWN_LOCAL_OR_MARKET_CONDITIONS:
AVAILABLE_FIRST_PARTY_EVIDENCE:
SUBJECT_MATTER_EXPERT:
EXISTING_PAGE_TEXT_OR_URLS:
APPROVED_PRIMARY_SOURCES:
COMPETITOR_URLS:
DESIRED_CONTENT_TYPE:
DESIRED_CONVERSION_ACTION:
BRAND_VOICE:
PROHIBITED_CLAIMS_OR_TOPICS:
```

## Research evidence inputs

```text
HEAD_QUERY_TESTED:
AI_SEARCH_PLATFORM_AND_DATE:
OBSERVED_FOLLOW_UP_QUESTIONS:
OBSERVED_BUSINESSES_OR_SOURCES:
OBSERVED_ANSWER_LANGUAGE:
OBSERVED_CHANGES_BY_BRANCH:
SCREENSHOTS_OR_TRANSCRIPTS:
```

---

# Part 2: Master Prompt

Copy the prompt below into a browsing-capable AI system and replace the input block. If live AI-search observations are unavailable, the system may propose research hypotheses but must not present them as observed behavior.

```text
You are a senior content strategist and research analyst working for a marketing agency. Your job is to uncover non-commodity content opportunities for any business or industry.

NON-COMMODITY CONTENT DEFINITION
Non-commodity content contains specific facts, firsthand experience, expert judgment, original evidence, or contextual knowledge that a competitor could not reproduce merely by summarizing common web pages. Examples include real price drivers, thresholds, timelines, process details, failure modes, tradeoffs, service limits, local or industry requirements, original data, and verifiable credentials.

Generic marketing claims, keyword variations, and summaries of widely available advice are commodity content.

CLIENT INPUTS
[PASTE THE COMPLETED CLIENT INPUT SHEET HERE]

OPERATING RULES
1. Preserve a strict distinction between OBSERVED, VERIFIED, CLIENT-SUPPLIED, INFERRED, and UNKNOWN information.
2. Do not claim you observed an AI-search result unless the input includes the result, transcript, or screenshot, or you can directly access and test that experience.
3. If direct testing is unavailable, label proposed follow-up questions and branches as HYPOTHESES TO TEST.
4. Never invent client facts, prices, results, policies, credentials, customer behavior, regulations, or expert opinions.
5. Use current, primary sources for laws, regulations, standards, fees, and product specifications. Include the source, jurisdiction, effective date when available, and access date.
6. Treat competitor claims and AI-generated summaries as leads, not proof.
7. When a claim requires client expertise, write an interview question instead of fabricating the answer.
8. Recommend a separate page only when the search intent and required answer are materially different. Otherwise group related questions into self-contained sections on one page.
9. Prioritize usefulness to the buyer over keyword repetition.
10. Do not draft final copy until the evidence and expert-input gaps are visible.

COMPLETE THE FOLLOWING PROCESS IN ORDER.

PHASE 1 — AUDIT THE EXISTING CONTENT
Review the supplied page or topic and inventory what it actually answers. Separate:
- facts already published;
- unsupported claims;
- information already available in listings, product feeds, profiles, or standard sales copy;
- missing decision information;
- statements that need updating or verification.

Output an Existing Content Audit table with these columns:
Current statement or topic | Evidence status | Commodity or non-commodity | Buyer value | Action

PHASE 2 — DEFINE THE HEAD QUERY
Write one natural-language “head query” representing the broad question a real buyer would ask. Do not force exact-match keywords. State the buyer, situation, intended outcome, and relevant market only when those details are natural.

PHASE 3 — MAP THE DECISION BRANCHES
Using supplied AI-search observations when available, identify the meaningful follow-up branches. Consider only dimensions relevant to this category, such as:
- symptom, use case, or desired outcome;
- urgency or timing;
- price, budget, or total cost;
- buyer or user type;
- product, service, or technical configuration;
- risk, compliance, or eligibility;
- alternatives and tradeoffs;
- location, jurisdiction, climate, or market conditions;
- compatibility, scale, or constraints;
- implementation, maintenance, or post-purchase needs.

For each branch, provide:
Branch question | Status: observed or hypothesis | Why the buyer asks | Decision variable exposed | What the current content lacks | Query to test independently

If research is being conducted manually, instruct the researcher to run every query in a fresh, signed-out session so prior conversational context does not contaminate the result.

PHASE 4 — LOG WHAT CHANGES
For every tested branch, record:
- how the answer changes;
- which companies, products, or sources appear or disappear;
- the exact terminology used;
- the facts, comparisons, or thresholds emphasized;
- whether sources are first-party, primary, local/market-specific, national/general, competitor, forum/social, video, or AI synthesis;
- where the system leaves the client’s market or industry to find an answer;
- where no credible source answers the question.

Do not infer these observations if test results were not provided. Instead produce a Branch Test Worksheet for a human researcher.

PHASE 5 — BUILD THE TERMINOLOGY AND ENTITY LOG
Extract the technical terms, entities, standards, components, processes, symptoms, measurements, and comparison criteria that recur. For each item explain:
Term or entity | Plain-language meaning | Why it matters to the decision | Fact the client should publish | Verification source or SME question

Do not recommend adding a term merely for SEO. Require the useful fact behind it.

PHASE 6 — FIND THE INFORMATION GAPS
Identify questions for which the current answer depends on generic, nonlocal, indirect, outdated, weak, or absent sources. Convert each gap into a content opportunity.

Score each opportunity from 0 to 3 on:
- Buyer impact
- Evidence uniqueness
- Business relevance
- Source weakness in current results
- Ability to verify
- Conversion proximity

Calculate the total out of 18. Do not prioritize an opportunity that cannot be supported; route it to research or an expert interview first.

Output:
Opportunity | Evidence of the gap | New fact or expertise needed | Scores | Total | Recommended action

PHASE 7 — CREATE THE EVIDENCE PLAN
For every prioritized opportunity, classify each required fact as:
- PUBLIC RESEARCH: can be verified through a primary external source;
- CLIENT RECORD: must come from CRM, invoices, analytics, product data, policies, or internal documents;
- SME INTERVIEW: requires practitioner judgment or firsthand experience;
- ORIGINAL RESEARCH: requires a test, survey, dataset, observation, or case study;
- CANNOT SUPPORT: should not be published yet.

Provide the exact research task or interview question needed. For numerical claims, request the sample, date range, geography, inclusions, exclusions, and calculation method.

PHASE 8 — CREATE ANSWER-FIRST CONTENT BRIEFS
Create briefs only for opportunities with adequate evidence or a clear evidence-acquisition plan. Each brief must include:
- Recommended page or parent page
- Buyer question as the proposed heading
- One-sentence answer structure, using placeholders where evidence is pending
- Supporting facts required
- Source or evidence owner for each fact
- Relevant terminology and entities
- Useful comparison table, checklist, example, image, or calculation if applicable
- Internal-link recommendation
- Conversion action
- Claims requiring legal, compliance, or client approval
- Freshness trigger and suggested review date

Each section must answer the question immediately and make sense if retrieved on its own. Do not bury the answer under an introduction.

PHASE 9 — DECIDE PAGE VS. SECTION
For every proposed item, choose:
- UPDATE EXISTING PAGE
- ADD SECTION TO EXISTING PAGE
- CREATE NEW PAGE
- CREATE SUPPORTING ASSET
- DO NOT PUBLISH YET

Explain the decision based on distinct buyer intent, depth of answer, evidence, and duplication risk—not on keyword variation.

PHASE 10 — FINAL DELIVERABLE
Return the work in this order:
1. Executive summary
2. Research mode and limitations
3. Existing content audit
4. Head query
5. Branch map or branch test worksheet
6. Observed change log, if evidence exists
7. Terminology and entity log
8. Ranked opportunity matrix
9. Evidence acquisition plan
10. Answer-first content briefs
11. Page-versus-section recommendations
12. Client/SME questions still unanswered
13. Source list with direct links and access dates
14. Quality-control report

QUALITY-CONTROL REPORT
Before finishing, explicitly confirm:
- Every factual claim is labeled by evidence status.
- No hypothesis is presented as an observation.
- No unknown client detail was invented.
- High-stakes claims use primary sources where possible.
- Every proposed section adds information beyond generic marketing language.
- Every numerical claim has a defined source and scope.
- Related questions are consolidated unless they require materially different answers.
- The content helps a buyer decide, diagnose, compare, act, or verify.

If any check fails, flag it and state what must happen before drafting or publication.
```

---

# Part 3: Agency Workflow

## Roles

- Account strategist: chooses the business priority and secures access to client materials.
- Researcher: audits the page, runs isolated head and branch queries, captures evidence, and verifies public facts.
- Subject-matter expert: supplies firsthand facts, judgment, exceptions, and examples.
- Content strategist: scores opportunities and decides page versus section.
- Writer/editor: drafts only from the approved brief and evidence pack.
- Client or compliance approver: approves factual, legal, regulatory, medical, financial, performance, and policy claims when applicable.

One person can fill multiple roles, but the evidence and approval checkpoints should remain separate.

## Stage 0 — Select a business outcome

Choose one offer, audience, market, page, and buyer outcome. Avoid researching an entire client site in one run.

Deliverable: completed Client Input Sheet.

Exit criterion: the team can state what decision the content should help a buyer make.

## Stage 1 — Audit the current page

Inventory the questions answered, facts supplied, evidence shown, and generic claims. Note what already exists in business listings, product feeds, directories, or standard manufacturer copy.

Deliverable: Existing Content Audit.

Exit criterion: the team knows what would be genuinely additive.

## Stage 2 — Run branch research

1. Run one natural-language head query.
2. Capture the full answer, follow-up prompts, cited sources, visible companies/products, date, platform, account state, and market.
3. Choose three to five meaningful branches.
4. Run every branch independently in a fresh signed-out session.
5. Capture what changes; do not merely record who ranks.

Deliverable: Branch Test Worksheet plus screenshots or transcripts.

Exit criterion: every “observed” claim is supported by a captured result.

## Stage 3 — Extract vocabulary and gaps

Log the model’s exact terminology, decision thresholds, comparisons, cited facts, and source types. Flag any branch answered with weak, generic, non-market, indirect, or absent sources.

Deliverable: Terminology and Entity Log plus preliminary opportunity list.

Exit criterion: each opportunity names the missing information—not just a keyword or topic.

## Stage 4 — Score opportunities

Score each opportunity using the 18-point rubric in the master prompt. Normally advance ideas scoring 12 or higher, but reject any idea that lacks a credible evidence path regardless of score.

Deliverable: ranked Opportunity Matrix.

Exit criterion: the team agrees which opportunities are valuable, relevant, and supportable.

## Stage 5 — Acquire evidence

Collect public primary sources, internal records, and expert answers. Ask for ranges and exceptions rather than false precision. For internal data, document the sample, time period, geography, inclusions, exclusions, and method.

Deliverable: claim-level Evidence Pack.

Exit criterion: every planned factual statement is verified, attributed, clearly labeled as experience/opinion, or left as a placeholder.

## Stage 6 — Build and approve briefs

Use the master prompt to produce answer-first briefs. The strategist decides whether each item belongs on an existing page, a new page, or a supporting asset. The SME and client approve the factual skeleton before prose is written.

Deliverable: approved Content Brief Pack.

Exit criterion: headings, answers, sources, assets, internal links, conversion action, and approvals are defined.

## Stage 7 — Draft and edit

Write from the approved briefs. Lead with the answer. Use concrete nouns, actual conditions, supported ranges, exceptions, and examples. Remove unsupported superlatives and filler introductions.

Deliverable: draft content with claim-to-source notes.

Exit criterion: an editor can trace every consequential claim to the Evidence Pack.

## Stage 8 — Publish and measure

Publish with descriptive headings, accessible tables, appropriate structured data, internal links, author/reviewer information, and a visible reviewed/updated date when useful. Record the baseline before publication.

Track:

- qualified organic entrances and conversions;
- assisted conversions;
- engagement with the new sections or assets;
- search queries and landing-page coverage;
- citations or mentions in AI-search experiences where observable;
- sales-team feedback and recurring customer questions;
- content freshness triggers.

Do not use AI citations as the only success measure. The content must also improve buyer understanding and business outcomes.

## Stage 9 — Refresh

Re-run the head query and selected branches after meaningful market, regulatory, product, pricing, or business changes. Refresh the evidence before updating the prose.

Suggested review cadence:

- Regulations, fees, prices, availability, product specifications: quarterly or when triggered by a known change.
- Policies, warranties, staffing, process details: every six months.
- Stable educational and diagnostic content: annually.
- High-stakes topics: according to the responsible professional or compliance owner.

---

# Part 4: Branch Test Worksheet

| Field | Entry |
|---|---|
| Client | |
| Page/topic | |
| Platform | |
| Test date | |
| Market/location | |
| Signed out/fresh session? | |
| Exact query | |
| Query type | Head / Branch |
| Follow-up questions shown | |
| Companies/products shown | |
| Sources cited | |
| Direct answer summary | |
| Exact technical language | |
| Numbers or thresholds used | |
| Local/industry-specific facts | |
| What changed from head query | |
| Did the answer leave the market/category? | |
| Missing or weakly sourced information | |
| Screenshot/transcript link | |

---

# Part 5: SME Interview Mini-Prompt

Use this after branch research. Replace the bracketed fields.

```text
We are improving [PAGE/TOPIC] for people trying to decide [BUYER DECISION]. AI-search research surfaced the questions below. Please answer from your real experience. If the answer varies, give the range, the variables that change it, and the exceptions. If you do not know, say so.

For each answer, include when possible:
- the direct answer;
- the conditions under which it changes;
- a realistic range rather than false precision;
- the warning signs or thresholds you use;
- a recent anonymized example;
- what customers commonly misunderstand;
- what evidence or record could support the statement;
- anything we should not publish.

Questions:
[PASTE PRIORITIZED SME QUESTIONS]
```

---

# Part 6: Definition of Done

A content item is ready to publish only when:

- it resolves a real buyer question;
- it adds facts, judgment, evidence, or context absent from the current page;
- its important claims are traceable to evidence;
- observations, inferences, and client statements are not mixed together;
- numerical claims state their scope;
- the answer appears immediately under a descriptive heading;
- the section works independently when retrieved out of context;
- page-versus-section placement is justified by intent;
- the responsible expert or client has approved sensitive claims;
- an owner and refresh trigger are assigned.

Source method: adapted from Reputation Arm’s “How to Use AI Mode’s Follow-Up Questions to Create Non-Commodity Local Service Content,” generalized for local and nonlocal businesses, products, services, SaaS, ecommerce, professional services, and regulated categories.
