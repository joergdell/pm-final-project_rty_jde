# Experimentation Plan (Module 5)

> Revised after a pre-launch review. Changes: three arms instead of one variant, the T-204 back-button fix moved out of the test, a 72-hour primary metric, guardrail margins with a stated method, and an explicit shipping rule. Figures marked *derived* are my own calculations. Thresholds and targets are proposals to confirm with stakeholders. Two launch gates are still open (see the end).

## Get your documents ready
- **From M3, your hypothesis sentence:** Based on the 77.9% document-step continuation, the 853 failed uploads (T-201) and N-01 ("I did not know if they meant this month or a normal month"), I believe that fixing mobile upload and explaining why income is asked for the mobile-first consumer will result in more plans completed in one sitting, as measured by a 7-point change (77.9% → 85.0%) in document-step to plan-review continuation. I will protect the 60-day missed-payment rate (at or below 19.0%) and will make a go/no-go decision after 4 weeks.
- **From M3, your primary success metric & guardrail metric:** Primary success metric: continuation from document step to plan review, 77.9% → 85.0%. The target is an assumption. Guardrail metric: missed payments within 60 days of new agreements stay at or below 19.0%. The PRD adds that the agreement rate must not fall below 46.0%. Note: the experiment redefines the primary metric as 72-hour continuation and the guardrails as comparisons against the control arm (see below).
- **From M4, the feature you scoped in your PRD (this is what you're testing):** Reliable mobile income-document step. A mobile upload that works on the first try, plus a short in-flow explanation of why income is asked, what it means and how long it is kept, so the consumer can finish the plan in one sitting without calling. The Must-Haves are:
  1. Upload succeeds on mobile.
  2. Progress plus a clear confirmation or error with retry.
  3. In-flow explainer.
  4. Answers kept when going back or leaving.

## Define your experiment parameters
- **Feature under test (pull from your M4 PRD):** Reliable mobile income-document step: working mobile upload with progress and a clear confirmation or error with retry, answers kept when the user goes back or leaves the income step, and (arm C only) a short in-flow explainer (why income is asked, what "income" means, how long it is kept).
- **Persona (pull your M2 persona):** A mobile-first consumer who started an instalment journey and reached the income document step, and who wants to finish in one sitting without calling anyone.
- **Expected outcome (the behaviour change you expect, from your M3 hypothesis):** More mobile consumers continue from the document step to plan review and finish the plan without an agent call.
- **Primary success metric (the one number that defines success, from M3):** Share of mobile users who reach plan review within 72 hours of their first document-step view. The 72-hour window counts users who leave and return later, which matches the saved-answers feature. Same-session continuation is reported as a secondary metric. Each user is enrolled once, on first exposure, with sticky assignment, so users with several journeys count once.
- **Baseline rate (today's rate of your primary metric, from your M3 data):** Not yet known. The 77.9% figure (5,943 reached the document step, 4,630 reached plan review) is an all-device funnel rate, not the 72-hour mobile definition. Mobile users are likely below it. Re-pull the mobile-only 72-hour rate before launch and recompute the target from it (launch gate 2).
- **Guardrail metric & boundary (what must not break, and how far it can move before you investigate):**
  - *Guardrail 1, agent contact within 7 days (baseline 31.0%):* breached only if arm C is significantly higher than A (one-sided 5% test) **and** the point estimate is at least +2.0 points. A true harm of about 4 points is caught about two times in three, and smaller harms are not reliably caught.
  - *Guardrail 2, missed payments within 60 days (baseline 19.0%):* not a pass/fail test at day 28, because the cohort is immature. Monitored until the last enrolled agreement is 60 days old. A point estimate of +4.0 points or more over control triggers a review. About 760 agreements per arm gives roughly ±3.9 points of noise *(derived)*.
  - Compare against the control arm, not against the historical 19.0%, because the variant may bring in users who previously dropped out.
- **Minimum Detectable Effect (the smallest improvement worth shipping, your floor):** Target +7.1 percentage points (assumption from M3). The ship floor is +5.0 points. It sits below the target because the target is an assumed effect and not a measured one. To be recomputed from the mobile baseline.
- **Sample size per arm (use the calculator in the builder, baseline + MDE):** About 470 users per arm for 7.1 points (80% power, 5% significance, two-sided) *(derived)*. Three arms need about 1,410 users in total. With about 1,075 mobile users per week at the document step *(derived, to be confirmed)*, 21 days of enrollment gives about 1,075 per arm, enough to detect effects down to about 4.7 points *(derived)*.
- **Traffic split & test duration (50/50 standard, cover ≥ 2 weekly cycles):** Equal three-way split (A, B, C), randomised per user, mobile users only. Duration 28 days: enrollment on days 1 to 21, follow-up to day 28, so every enrolled user has a complete 72-hour and 7-day window. This covers four weekly cycles. A split that deviates significantly from equal (p < 0.01) invalidates the test and it is rerun.
- **Significance threshold (p < 0.05 is standard, explain any deviation):** p < 0.05 (95%), two-sided, for the single decision comparison (C vs A). The guardrail check and the C vs B harm check use one-sided 5% tests because they only look for harm. B vs A and C vs B are diagnostic and are not used for the ship decision.

## Define your control and variant
- **Control (A), the current experience (reference your M2 moment of misery and M3 funnel/workflow data):** The income document step as it exists today on mobile:
  - The income questions are asked with no help text. There is no explanation of why income is asked, what "income" means (this month or a normal month) or how long it is kept (T-206, N-01).
  - The user uploads a photo of the income document. For large phone photos the upload times out and the document never arrives, 853 journeys in the sample month (T-201).
  - Funnel result: only 77.9% continue from the document step to plan review (5,943 → 4,630, all devices). Today's progress and error display is not described in the data pack, so confirm it with engineering before the test. The control arm is instrumented as well, so first-try upload success has a baseline.
- **Variant (B and C), your change, copy the relevant screens & functional requirements from your M4 PRD:** Two variant arms, so the explainer can be separated from the technical fix.
  - **Arm B, reliability:** photo upload succeeds on mobile for typical phone photos (size limit to be confirmed with engineering); upload progress and a clear confirmation, or an error with a retry option, so a document never disappears silently; entered answers on the income step are kept when the user goes back or leaves and returns.
  - **Arm C, reliability plus explainer:** everything in B, plus a short in-flow text on the income step covering purpose, definition (this month or a normal month) and retention period, with the final wording agreed with compliance.
  - What each comparison tells me: C vs A is the full feature and drives the ship decision. B vs A shows the technical fix alone. C vs B shows the explainer alone.
  - Arm B is still a bundle of three changes, so B vs A attributes the effect to the reliability package, not to one part of it. Step-level events are logged (upload attempted, succeeded or failed, explainer viewed, back clicked) for descriptive diagnosis only.
- **Isolation check, what has NOT changed? (list everything identical between arms):** Everything outside the income document step stays identical across A, B and C:
  - The document is still required. The "skip under a set amount" option from the PRD is not in this test.
  - The affordability questions and their order.
  - Plan options and plan order (the 6-month plan stays first). Changing it would distort the missed-payment guardrail.
  - The plan review screen. The T-204 back-button fix (answers cleared on the plan review screen) is **removed from the test** and released to all users before the baseline is pulled, so it is identical in every arm and cannot move the primary metric.
  - Amount shown in the portal compared with the letter (T-203) and the reminder timing (T-207).
  - The chat assistant and the agent screen (T-205).
  - Outreach: letters, QR codes, email and SMS reminders, and the entry channel mix.
  - Eligibility rules, income document review rules and amounts offered.
  - App version and release cycle for everything else. No other release touches the portal journey during the 28 days.

## Formalize your hypothesis & shipping criteria
- **Your hypothesis (filled in):** I believe that a reliable mobile income-document step (arms B and C) for the mobile-first consumer at the income document step will result in more plans completed in one sitting without an agent call, as measured by a lift in 72-hour continuation from document step to plan review above the mobile control baseline [target to be set from the re-pulled baseline; working assumption +7.1 points], within 28 days. We will protect agent contact within 7 days (Guardrail 1) and missed payments within 60 days (Guardrail 2), each compared against the control arm.
- **Your shipping criteria (filled in):** The read date is day 28, fixed. No results are reviewed before this date.
  - **SHIP C** if C beats A by at least 5.0 points in 72-hour continuation (p < 0.05, confidence interval above zero), C is not significantly worse than B, and Guardrail 1 is not breached. The explainer is shipped by default because it is likely needed for transparency (T-206, N-12), not only for conversion.
  - **SHIP B only** if B beats A on the same test and C is significantly worse than B (one-sided 5%). The explainer then goes back to compliance and copy review.
  - **ITERATE** if the lift is positive and significant but below 5.0 points, or a guardrail is breached while the lift is positive.
  - **KILL** if the upper end of the 95% interval for C vs A is below +2.0 points.
  - **INCONCLUSIVE** if the lift is not significant and the upper end of the interval is +2.0 points or higher. Rerun with a larger sample, do not ship.
  - **After shipping:** Guardrail 2 is monitored until the last enrolled agreement is 60 days old. A rise of +4.0 points or more over control triggers a rollback review.
- **Hardest parameter to define, and did it change your hypothesis? (quick debrief):** The hardest was the guardrail. Missed payments within 60 days takes longer to observe than the test lasts, and a tight margin cannot be resolved with about 1,000 users per arm (the noise is about ±3.9 points). That changed the plan in four ways: a second, faster guardrail (agent contact within 7 days), margins set to what the sample can resolve, an explicit test method for each guardrail, and the missed-payment check as monitored follow-up with a rollback option. The pre-launch review also split the variant into three arms, moved T-204 out of the test, and replaced same-session with 72-hour continuation. The core hypothesis did not change. The 7.1-point target is still my M3 assumption, not a measured effect, and should be replaced once real mobile data exists.

## Open launch gates
1. **Compliance wording and retention period.** Arm C cannot launch with a placeholder. Draft for compliance to edit (not final): "We ask for your income to find a monthly amount that fits you. Please give your normal monthly income, not only this month. We keep this information for [retention period, to be confirmed by compliance]."
2. **Mobile-only baseline and real traffic.** Analytics to supply, mobile only: the 72-hour continuation rate from first document-step view to plan review, and weekly users reaching the document step. Launch condition: at least about 470 users per week across the three arms (about 1,410 in 21 days). If traffic is lower, extend enrollment and move the read date, keeping a 7-day follow-up after enrollment closes.
