# GTM Strategy & Success Dashboard (Module 6)

## Get your prior work ready
- **The feature you're launching from your M4 PRD, one feature, not a list:** Reliable mobile income-document step. A mobile upload that works on the first try (the photo is shrunk before sending), with progress and a clear confirmation or an error with retry, and answers kept when the user goes back or leaves and returns. The variant tested in M5 arm C adds a short in-flow explainer: why income is asked, what “income” means (normal monthly income), and how long it is kept.
- **What your M5 experiment will test your hypothesis, primary metric and ship / iterate rule, the evidence the launch rests on:** Hypothesis: A reliable mobile income-document step for the mobile-first consumer will result in more plans completed in one sitting without an agent call, measured by a lift in 72-hour continuation from document step to plan review above the mobile control baseline. Working target: +7.1 points, which is an assumption. The test protects agent contact within 7 days and missed payments within 60 days, both compared against the control arm.
Primary metric: Share of mobile users who reach plan review within 72 hours of their first document-step view.
Design: Three arms (A control, B reliability, C reliability plus explainer), mobile only, 28 days (enrollment days 1 to 21).
Ship rule: Ship C if it beats A by at least 5.0 points (p < 0.05), is not significantly worse than B, and the agent-contact guardrail holds. Ship B only if C is significantly worse than B. Iterate if the lift is positive but below 5.0 points. Kill if the upper end of the 95% interval is below +2.0 points. Inconclusive otherwise: rerun, don’t ship.
Evidence the launch rests on: Only 77.9% continue from the document step to plan review (all-device figure). 853 journeys had a document that never arrived (T-201). N-01: “I did not know if they meant this month or a normal month.” Mobile agreement is 43.8% against 54.0% on desktop.
Status: The test has not run, so the launch rests on the pre-test evidence above, not on results. Two gates are still open: compliance wording and retention period, and the mobile-only baseline and traffic.
- **Your persona pull your M2 persona, this anchors your audience:** A mobile-first consumer who started an instalment journey and reached the income document step, and who wants to finish in one sitting without calling anyone. The friction: the upload of a large phone photo times out and the document never arrives (T-201), and there is no help text on why income is requested or how long it is kept (T-206).

## Set your goal, then your audience
- **Primary GTM goal awareness · engagement · conversion, pick one:** Conversion
- **Why this goal? what makes this the right goal for this feature right now:** The feature lives inside the existing portal and fixes a specific step, so the job is to move more people through it, not to make them aware of it. The measured gap is conversion: only 77.9% continue from the document step to plan review (all-device figure). The M5 experiment uses the same measure as its primary metric, so the goal and the test line up.
- **Target audience the specific segment your goal implies, be precise:** Mobile users in the German portal who reach the income document step of an instalment journey. This is an existing-user segment, not a new market.

Size: about 4,660 users per month (derived assumption). It takes the 5,943 users who reach the document step and applies the 78.5% mobile share of journey starters. Mobile users probably drop earlier, so the real number is likely lower.
For context from the data pack: 6,563 of 8,360 monthly starters are on mobile, and 2,968 starters have two or more open claims (assumed practice figures).
I haven’t opened gtm_audience.csv. The figures come from the audience table in data-pack.md.
The pilot segment size and the number of agents in the pilot team are “open” in the data pack. I don’t state a number for either, and you’d need to pick your own assumption.

## Size your launch
- **Launch tier S (minimal) · M (targeted) · L (multi-channel) · XL (full GTM):** S (minimal).
- **Justification reach + revenue impact + what silence would risk:** Reach: a limited, internal segment of roughly 4,660 mobile users per month (derived, see above). It needs no external channel, since the users are already inside the step.
Revenue impact: modest but real. If the +7.1-point target held (an assumption), that would be about 330 more users reaching plan review per month and about 275 more agreements at the 83.1% plan-review-to-agreement rate (derived, depends on the mobile baseline).
Risk of silence: low. Consumers see the fix directly in the step. The one real risk is internal: agents will see fewer upload and “why income” calls, and the explainer changes what consumers ask. They should hear about it before it goes live.
- **Is this a launch or a release? does it need go-to-market, or can it just ship?:** A release. It does not need go-to-market: nothing is announced to consumers, and it ships once the M5 test supports it. It does need three low-cost steps:

A short briefing for agents and client managers.
Compliance sign-off on the explainer wording and retention period (still open).
Monitoring of the primary metric and the two guardrails after it goes live.

## Choose your top three channels and plan assets
- **Channel 1 owned / earned / paid, and why it reaches your audience:** Owned: the income document step itself (the in-product explainer, progress and error messages). 100% of the audience sees it, at the exact moment of need. Users are already inside the portal, so no channel has to find them.
- **Channel 2 owned / earned / paid, and why:** Owned, but only after the M5 test: the existing outreach that brings users into the portal (email reminder 3,770, SMS reminder 2,543, letter QR code 2,047 starters per month). A line such as “you can upload your document from your phone” could go into these messages. It is held back on purpose, because the test keeps outreach identical across arms. It would be a post-test addition.
- **Channel 3 owned / earned / paid, and why:** Owned, internal: a briefing and knowledge-base entry for agents and client managers. Agents get the upload and “why is income asked” calls (333 and 419 contacts per month), so they need to know what consumers now see. Client managers need a line for clients, who watch complaints and broken plans (N-10).

Paid and earned channels are deliberately not used. This is a release inside the existing product, so paying for reach would add cost without reaching anyone new.
- **Enablement & assets what Sales / CS / Support need, plus the assets to build (one-pager, demo, etc.):** Agents (Support): a one-pager covering what changed, what the consumer sees, a consistent answer to “why is my income asked and how long is it kept”, and what to say about a failed upload. It must say plainly that agents still cannot see what the consumer entered (T-205 is not part of this release).
Client managers: a short note on the expected effect and the guardrails, so they can answer client questions.
Compliance: the approved explainer wording and retention period (still open).
To build: the agent one-pager, an FAQ entry and the client note. The three-arm demo (prototype.html) already exists and can serve as the walkthrough for A versus C.

## Make it executable
- **Ownership named owner per key activity, individual, not department:** Product, test and go/no-go: Joerg Dell (assumption: you own the feature).
Build and event logging: SD.
Wording and retention period sign-off:NU.
Mobile baseline, traffic pull and analysis:JD.
Agent briefing and one-pager: TD
Client note: KH
- **Budget & resource gaps what costs extra, and any asset you can't currently build:** Costs extra: engineering time for the upload fix, the test assignment and the event logging. Compliance review time. Analyst time for the baseline pull and the guardrail monitoring. A small amount of agent time for the briefing. I haven’t estimated amounts, since the data pack has no cost figures.
Gaps I can’t close today: the mobile-only baseline and traffic are unknown, the retention period is unknown, and there is no dashboard for the 60-day missed-payment guardrail. Agents also still have no view of what the consumer entered, so enablement can’t promise it.
Paid budget: none needed.
- **Timeline Phase 1 beta → Phase 2 launch moment → Phase 3 post-launch:** Phase 1, beta (the A/B test): about two weeks of prep before the start. That covers the two open gates (compliance wording, baseline and traffic), the T-204 release to all users, and the event logging. Then 28 days of testing, with enrollment on days 1 to 21 and follow-up to day 28.
Phase 2, launch moment: day 28 is the fixed read date. If the ship rule is met, release to all mobile users and send the agent one-pager and client note in the days before.
Phase 3, post-launch: monitor missed payments until the last enrolled agreement is 60 days old (about day 81). Afterwards, consider the outreach line (channel 2), then take the next backlog item.

## Define how you'll know it worked
- **Success metrics 2 to 3 metrics that match your GTM goal:** 72-hour continuation, mobile (primary): share of mobile users who reach plan review within 72 hours of first seeing the document step. Ship floor is +5.0 points over control. The baseline is still open: the 77.9% is an all-device funnel figure.
First-try upload success rate: share of users whose first upload succeeds. It shows whether the technical fix works, so it needs a baseline from the control arm.
Agent contact within 7 days (guardrail): baseline 31.0%. It shows whether more people finish without a call, and whether the new text creates new questions. Missed payments within 60 days run alongside it as a monitored guardrail.
- **Bad signal to watch for e.g. high reach, zero signups = message-market mismatch:** Continuation: it rises, but missed payments rise too (the test sets a review at +4.0 points over control). This would mean the step now lets in users who cannot afford the plan.
First-try upload success: it goes up while continuation stays flat. Then the upload was not the real blocker, and the roughly 460 users T-201 does not explain are the problem. Also watch for failure clusters by phone model or browser.
Agent contact: it rises by 2.0 points or more over control (the test’s guardrail breach rule). This would mean the explainer is raising questions, not answering them.
Overall: high reach with no change in continuation, which is message-market mismatch.
- **Most likely post-launch decision double-down · iterate · pivot · deprioritize, and what would trigger it:** My judgement is iterate, because the +7.1-point target is an assumption and sits close to the ceiling of about 14 points (853 failed uploads out of 5,943 users, derived). The decision rules and their triggers:

Double-down: C beats A by at least 5.0 points and the guardrails hold. Ship C, then move on to the next obstacles: the amount mismatch (T-203), missed-payment consequences (T-208) and the agent view (T-205).
Iterate: the lift is positive but below 5.0 points, or only B beats A. Ship B and rework the explainer with compliance and copy.
Pivot: first-try upload success is high but continuation is flat. Investigate the unexplained drop-offs, such as income wording and data fear (N-06).
Deprioritize: the upper end of the 95% interval for C vs A is below +2.0 points.
