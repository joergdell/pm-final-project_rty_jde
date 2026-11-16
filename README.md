# A Fair Way Forward: a reliable mobile income-document step

> Mobile consumers drop out of the instalment journey at the income document step. A working upload and a clear explanation of why income is asked would let them finish in one sitting without calling an agent.

**Joerg Dell · cohort not stated** · https://github.com/joergdell/pm-final-project_rty_jde

> Practice case: Riverty BU Collection, digital instalment journey. All data comes from a fictional practice data pack and is not Riverty research.

---

## Final Project Deliverables

### Slide 5 · Strategy
- **Problem:** Two problems: a journey that breaks on mobile, and one that is unclear and not fitted to the consumer. Only 77.9% continue from the income document step to plan review (all-device figure), and 853 journeys in the sample month asked for a document that never arrived (T-201).
- **Value proposition:** Resolve the biggest bug-related pain points first and review the journey to gain trust and clarity. Clear the consumer's way before adding new features.
- **Hypothesis:** A reliable mobile income-document step for the mobile-first consumer will result in more plans completed in one sitting without an agent call, measured by a lift in 72-hour continuation from document step to plan review. Working target +7.1 points (an assumption). Agent contact within 7 days and missed payments within 60 days are protected.

### Slide 6 · Research
- **Competitive analysis:** The manual workaround is the competitor: the consumer leaves the journey and phones an agent (333 upload-problem and 419 "why is income asked" contacts per month), then repeats details the agent cannot see. The future-state journey replaces this with one sitting, one explanation and shared data. No external competitor is analysed, and the research does not cover one.
- **Journey map:** A four-stage future state for a mobile-first consumer at the income document step: understand the ask, capture and upload, review and confirm, agree and stay on track. Each stage names the user action, internal state and the pain point it addresses. See `02-discovery/competitive-and-journey.md`.

### Slide 7 · Blueprint
- **Roadmap:** Phase 1 (weeks 1–4): mobile upload fix, income explainer, reminder timing. Phase 2 (weeks 5–8): amount matches the letter, chat shows missed-payment consequences, agent handoff summary. Phase 3: one plan for several claims and an affordability check. Timing is an assumption and the backlog items were not scored.
- **PRD highlights:** Feature: reliable mobile income-document step. Musts: upload succeeds on mobile, progress and a clear confirmation or error with retry, an in-flow explainer (purpose, meaning of income, retention period), and answers kept when going back or leaving. Out of scope: multi-claim plans, pay-day date, chat on every page.
- **Prototype:** `04-roadmap/prototype.html`, a self-contained demo with a switch between three arms (control, reliability, reliability plus explainer) and a browser-side event log. Uploads are simulated and nothing is sent anywhere.

### Slide 8 · Validation
Three-arm A/B test (control, reliability, reliability plus explainer), mobile only, 28 days with enrollment on days 1 to 21. Primary metric: share of users reaching plan review within 72 hours of first seeing the document step. Guardrails: agent contact within 7 days and missed payments within 60 days, both compared against control. Ship C if it beats control by at least 5.0 points (p < 0.05) and the guardrails hold. The test has not run yet. Two launch gates are open: compliance wording and retention period, and the mobile-only baseline and traffic.

### Slide 9 · Launch
- **GTM:** Goal: conversion. Audience: mobile users in the German portal who reach the income document step (about 4,660 per month, a derived assumption). Tier S, a release rather than a launch. Channels: the step itself, post-test outreach messages, and an internal briefing for agents and client managers.
- **Metrics:** 72-hour continuation (primary), first-try upload success rate, and agent contact within 7 days as a guardrail, with missed payments within 60 days monitored. Most likely decision: iterate.

### Slide 10 · Story
- **Friction + aha:** _(not filled: the Individual Insights reflection in `06-launch/individual-insights.md` has not been written yet)_
- **Takeaways / next:** Next steps follow from the open items: get compliance wording and the retention period, pull the mobile-only baseline and real traffic, then run the three-arm test. Later backlog items are the amount mismatch, missed-payment consequences and the agent view of what the consumer entered.

---

Submitted to the Product Management Certification learning platform · Product School.
