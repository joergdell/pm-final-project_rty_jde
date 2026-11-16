# Hypothesis & Success Metrics

> **Module 3 · ★ Deliverable 3.** Repo file `03-analytics/hypothesis-and-metrics.md` — part of your submission.
> Do the lab in the **Module 3 · Exercise Guide** (linked from the Module 3 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It feeds the **Problem, Value & Hypothesis** slide of your Module 6 final deck.

> Data source: fictional Collection data pack (`data-pack.md`), month 6 unless stated. Figures marked *derived* are my own calculations. Targets and the decision window are assumptions.

## Pre-work: hypothesis check (qualitative anchor from Modules 1 & 2)

| Item | Answer |
|---|---|
| Role (M2) | A mobile-first consumer who started an instalment journey and reached the income document step. |
| Goal (M2) | Finish the plan in one sitting, without calling anyone. |
| Friction / moment of misery (M2) | The upload of a large phone photo times out and the document never arrives (T-201, 853 journeys in the sample month). There is no help text explaining why income is requested or how long it is kept (T-206). |
| Current workaround (M2) | Leaves the journey and phones an agent (333 upload-problem contacts per month), then re-explains details the agent cannot see (N-08, T-205). Other routes (resizing the photo, email, desktop) are unvalidated. |
| Problem hook (M1) | Two main problems: a buggy product with legacy functions, and consumers lost on mobile in unclear, poorly fitted journeys. |
| Value proposition (M1) | Resolve the biggest bug-related pain points immediately and review the journeys to gain trust and clarity. |

## Step 1: read the evidence in the case

**1. Where the experience drops (funnel)**
- Where does the case say people stall or leave? The largest step loss is before the journey: only 22.0% of portal entrants start an instalment journey (38,000 → 8,360). Inside the journey the weakest step is the income document step to plan review at 77.9% (5,943 → 4,630, so 1,313 people lost).
- Does that match the friction from Module 2? Yes. The document step is exactly where the persona's friction sits.
- Nuance: T-201 (853 journeys with a document that never arrived) could explain up to 65% of the 1,313 *(derived upper bound)*. About 460 drop-offs remain unexplained, where unclear income wording (T-206, N-01) is plausible but unproven. The 22% start step is a bigger loss in absolute terms, but it sits before the persona's moment of misery.

**2. What changed over time (six months)**
- Better: agreement rate rose from 43.1% to 46.0%, agent contact within 7 days fell from 33.4% to 31.0%, and the self-service rate rose from 31.1% to 34.7%.
- Worse: missed payments within 60 days rose from 15.2% to 19.0%. The jump starts in Month 4, when the plan screen began showing the 6-month plan first.
- Does it support the workaround? Only partly. Agent contact is falling slowly and still sits at 31%, and "document upload problem" remains 12.8% of contacts (333). The data pack has no monthly series for upload failures or document-step completion, so the trend of this specific workaround cannot be confirmed. Metric I would ask for: monthly document-step completion and upload failure rate, split by device.

**3. Which users feel it (segments)**
- Mobile is the largest segment: 6,563 of 8,360 starters (78.5%), with 43.8% agreement against 54.0% on desktop.
- Contradiction worth noting: mobile users do not contact agents more (31.1% vs 30.6% on desktop). Mobile users seem to drop out rather than call, so the "phone an agent" workaround is not specific to mobile.
- The heaviest pain per segment sits elsewhere: three or more open claims (27.6% agreement, 43.0% agent contact) and variable or shift-work income (41.6% agreement, 22.5% missed payments).
- Is that the Module 2 persona? Partly. The mobile persona matches the largest segment. The users carrying the most acute pain are multi-claim and shift-income consumers (N-01, N-03), who are a different persona.

## Step 2: craft your hypothesis

| Item | Answer |
|---|---|
| Qualitative evidence (M2) | T-201: "Income document upload times out on mobile for large photos." N-01: "It asked for my income and I did not know if they meant this month or a normal month. I closed it and meant to come back." |
| Quantitative evidence (M3) | Only 77.9% continue from the document step to plan review (1,313 lost). 853 journeys asked for a document that never arrived. Mobile agreement is 43.8% against 54.0% on desktop. |
| Persona | A mobile-first consumer at the income document step who wants to finish in one sitting without calling. The upload times out, and nothing explains why income is asked or how long it is kept. |
| Problem you are solving | Income document upload fails on mobile and the journey gives no explanation of why income is requested, so users abandon or phone an agent. |
| Strategic outcome | More mobile starters finish the plan in self-service, which should raise agreements and reduce agent calls, protecting recovery and the client relationship. The link to revenue and churn is an assumption to be tested. |
| Primary success metric (initiative signal) | Continuation from document step to plan review: 77.9% → 85.0% (+7.1 points). At current volume that is about 420 more journeys per month *(derived)*. |
| Guardrail metric (product signal) | Missed payments within 60 days of new agreements must stay at or below 19.0%. Agreement rate must not fall below 46.0%. |
| Decision window | 4 weeks after release, with at least about 4,000 document-step visitors. Assumption: roughly 1,370 visitors per week at current volume *(derived)*. |

### Hypothesis statement

Based on the 77.9% continuation at the document step, the 853 journeys where the requested document never arrived (T-201), and the quote "I did not know if they meant this month or a normal month" (N-01), I believe that fixing the mobile upload and explaining why income is requested for the mobile-first consumer at the income document step will result in more plans completed in one sitting without an agent call, as measured by a 7-point change (77.9% → 85.0%) in document-step to plan-review continuation. I will protect the 60-day missed-payment rate (at or below 19.0%) and will make a go/no-go decision after 4 weeks.

## Finalized product hypothesis

> Based on the 77.9% document-step continuation, the 853 failed uploads (T-201) and N-01 ("I did not know if they meant this month or a normal month"), I believe that fixing mobile upload and explaining why income is asked for the mobile-first consumer will result in more plans completed in one sitting, as measured by a 7-point change (77.9% → 85.0%) in document-step to plan-review continuation. I will protect the 60-day missed-payment rate (at or below 19.0%) and will make a go/no-go decision after 4 weeks.

## Success metrics

| Metric | Type | Target | Why it matters |
|---|---|---|---|
| Self-service rate (plans only, no agent contact within 7 days) | North-star | 34.7% → 38.0% | Shows that consumers finish without a call, which is the persona's goal and the value proposition (trust and clarity). Target is an assumption. |
| Document step to plan review continuation | Leading indicator | 77.9% → 85.0% | The weakest step in the funnel and the direct signal that the upload fix and income explainer work. Target is an assumption. |
| Missed payments within 60 days of new agreements | Guardrail | At or below 19.0% | Completing more journeys must not mean worse plans. This rate rose from 15.2% to 19.0% over six months and must not rise further. |
