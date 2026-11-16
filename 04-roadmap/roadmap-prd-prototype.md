# Roadmap, PRD & Prototype

> **Module 4 · ★ Deliverable 4.** Repo file `04-roadmap/roadmap-prd-prototype.md` — part of your submission.
> Do the lab in the **Module 4 · Exercise 1 Guide** (linked from the Module 4 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It becomes the **Roadmap, PRD & Prototype** slide of your Module 6 final deck. (Your Module 4 · Exercise 2 PRD sprint lands in `prd-and-prototype.md`.)

> Case: BU Collection, digital instalment journey (German portal). Data from the fictional practice data pack; figures marked *derived* are my own calculations. Phase timing and targets are assumptions. Backlog items B1–B8 have not been scored for value and effort, so the order below follows the Module 1 value proposition (fix obstacles first, then add features) and is not a scoring result.

## High-level product roadmap

_Future direction, key milestones, and phased execution over time._

**Direction:** Clear the consumer's way first. Volume is already high (38,000 portal entrants, 8,360 journey starters per month), so the first phase removes the failures and gaps that cost completed plans. New features come after.

**Phase 1, Now (weeks 1–4): fix and explain**
- Reliable income-document upload on mobile, or skip the document under a set amount (B5, T-201).
- Plain explainer on why income is asked, what it means and how long it is kept (B2, T-206).
- Keep affordability answers when using the back button (T-204).
- Send the reminder before the first due date, never after (T-207).
- Milestone: document-step to plan-review continuation rises from 77.9% towards 85.0%.

**Phase 2, Next (weeks 5–8): make the journey trustworthy**
- Portal amount matches the letter, starting with purchased portfolios (T-203).
- Chat assistant shows what happens after a missed payment before confirming a plan (T-208).
- Agent handoff summary: what the consumer entered and why a plan was offered (B4, T-205).
- Review the plan-screen order. The 6-month plan first coincides with missed payments rising from 15.6% to 19.0% (Month 3 to Month 6).
- Milestone: fewer clarity-driven agent contacts; missed payments no worse than 19.0%.

**Phase 3, Later (weeks 9–12 and beyond): fit the journey to the user**
- One plan for several open claims (B1, T-202). Agreement is 52.1% with one claim and 27.6% with three or more.
- Affordability check before the plan options (B3).
- Pay-day payment date (B6): only if evidence appears. My Strategic Map found no strategic case for it today.
- Milestone: agreement rate for multi-claim consumers improves.

**Deliberately not planned:** chat assistant on every portal page (B8). The chat already confirms plans without explaining consequences, so extending it first would spread that gap.

## PRD snippets

_The key elements of your simplified PRD._

**Feature (Now):** Reliable mobile income-document step.

**Problem:** On mobile, the income document upload times out for large photos and the document never arrives (853 journeys in the sample month). The step also gives no explanation of why income is asked or how long it is kept. Only 77.9% of users continue from this step to plan review (1,313 lost; T-201 explains up to 65% of that *(derived upper bound)*).

**Target user:** A mobile-first consumer who started an instalment journey and reached the income document step (78.5% of starters use mobile). Goal: finish the plan in one sitting without calling anyone.

**Goal and metrics**
- Primary: document-step to plan-review continuation, 77.9% → 85.0% (assumption).
- North-star: self-service rate (plans only, no agent contact within 7 days), 34.7% → 38.0% (assumption).
- Guardrail: missed payments within 60 days of new agreements stay at or below 19.0%.

**Requirements**

| Priority | Requirement |
|---|---|
| Must | Photo upload succeeds on mobile for typical phone photos (size limit to be confirmed with engineering). |
| Must | Show upload progress and a clear confirmation or error with a retry. |
| Must | Short in-flow text: why income is asked, what "income" means (this month or a normal month), how long it is kept. |
| Must | Keep entered answers when the user goes back or leaves and returns. |
| Should | Skip the document under a set amount (threshold needs a compliance decision). |
| Should | Reminder before the first instalment is sent before the due date. |
| Won't (this release) | One plan for several claims, pay-day date, chat on every page. |

**User stories**
- As a mobile consumer, I want my photo to upload on the first try, so I can finish on my break without calling.
- As a shift worker, I want to know what "income" means here, so I can answer without guessing.
- As a consumer, I want to know how long my income data is kept, so I am not afraid to type it.

**Acceptance criteria (draft)**
- A large phone photo uploads successfully, or a clear error with a retry option appears. The document never silently disappears.
- The income step shows the explainer, covering purpose, definition and retention period, without leaving the flow.
- Using the back button on plan review keeps all affordability answers.

**Risks and open questions**
- Retention period and exact wording need a compliance decision (N-12: decisions must be explainable to consumer and agent).
- Skipping the document under a set amount changes affordability checks. Threshold and risk are open.
- The data pack has no monthly upload failure rate by device, so the effect size is an assumption.
- About 460 of the 1,313 lost users are not explained by T-201. The explainer may not recover them.

**Out of scope:** changing plan options or order, multi-claim plans, new chat features.

## Wireframes / prototype

_A visual or interactive model of your proposed solution._

No interactive prototype or link exists yet. Text wireframe of the income document step (mobile):

```
+--------------------------------+
|  Step 3 of 5   Your income     |
|--------------------------------|
|  Why we ask                    |
|  We check what monthly amount  |
|  fits you. Use your normal     |
|  monthly income. Kept for      |
|  [retention period - TBC].     |
|--------------------------------|
|  Upload income document        |
|  [ Take photo ] [ Choose file ]|
|                                |
|  photo.jpg   ########--  80%   |
|  (error: [Try again])          |
|--------------------------------|
|  [ Back ]          [ Continue ]|
|  Your answers are saved.       |
+--------------------------------+
```

_[prototype link: to be added once built]_
