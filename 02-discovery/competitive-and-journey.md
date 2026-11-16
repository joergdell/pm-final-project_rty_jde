# Competitive Analysis & Journey Map

> **Module 2 · Lab 2 — ★ Deliverable 2.** Repo file `02-discovery/competitive-and-journey.md` — part of your submission.
> Do the lab in the **Module 2 · Exercise 2 Guide** (linked from the Module 2 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It becomes the **Competitive Analysis & Journey Map** slide of your Module 6 final deck. Builds on your `ai-synthesis.md` and your Module 1 `problem-hook.md`.

## Responses

- **Role, who are you solving for?:** A mobile-first consumer who started an instalment journey and reached the income document step.
- **Goal, what is this user ultimately trying to achieve?:** Finish the plan in one sitting, without calling anyone.
- **Friction, the main barrier (moment of misery) stopping them:** The upload of a large phone photo times out and the document never arrives (T-201, 853 journeys in the sample month). There is no help text explaining why income is requested or how long it is kept (T-206). The document step is the weakest in the funnel: only 77.9% continue to plan review.
- **External tools the user is forced to use:** Phone and agent call (the only external channel evidenced: 333 upload-problem contacts per month). Phone camera and gallery to produce the document (follows from T-201). To validate, not in the research: email or post as an alternative route, and a desktop browser as a fallback.
- **The process, the 3–5 manual steps they take:**
  1. Photograph the income document on the phone and try to upload it. The upload times out and the document never arrives.
  2. Look for help on why income is asked and how long it is kept, and find none.
  3. Leave the journey, meaning to come back later.
  4. Call an agent to resolve the upload problem or the income question.
  5. Re-explain the details already typed online, because the agent cannot see them.
- **Core frustration, where the process feels most "broken":** The upload times out and the document never arrives, with no explanation of what happened or why income is needed. The user cannot finish in one sitting and falls back on a phone call.
- **The evidence, a quote or behavior from the research:**
  - T-201: "Income document upload times out on mobile for large photos. 853 journeys in the sample month asked for a document that never arrived."
  - N-01: "It asked for my income and I did not know if they meant this month or a normal month. I closed it and meant to come back."
  - N-08 (agent side): "Half my calls start with me asking for the same details they already typed online. I cannot see what they entered."
  - Behavior: 333 contacts per month are about document upload problems (11.7 min average each); 78.5% of starters are on mobile.
  - Note: no interview directly covers the upload failure, so T-201 and the contact data carry that part. The N-01 and N-08 quotes come from other personas and support the same moment.
- **Journey map, a shareable link or the map file you committed:** Future-state journey (4 stages, Action → Benefit). Not validated with real users; the internal states are assumptions drawn from N-01 and N-06.

  1. **Understand the ask**
     - User Action: Reads short income explainer → knows what income means, how long kept
     - Internal State: Hesitant → reassured, willing to continue
     - Pain Point Addressed: Adds income help text → removes ambiguity and data fear (T-206, N-01)
  2. **Capture and upload**
     - User Action: Photographs document; app compresses it → upload succeeds first try
     - Internal State: Anxious → confident, sees live progress and confirmation
     - Pain Point Addressed: Fixes mobile upload timeout → no lost document (T-201)
  3. **Review and confirm**
     - User Action: Reviews plan, goes back freely → answers stay saved
     - Internal State: Cautious → informed on amount and missed-payment outcome
     - Pain Point Addressed: Fixes state loss, amount mismatch, hidden consequences → trust (T-204, T-203, T-208)
  4. **Agree and stay on track**
     - User Action: Confirms plan, gets reminder before first due date → pays on time
     - Internal State: Relieved, in control → no need to call
     - Pain Point Addressed: Fixes late reminder; agent sees entries → fewer repeat calls (T-207, T-205)

  **Competitive advantages over the manual workaround**
  1. Finish in one sitting → no call, no waiting, no repeated explanations
  2. Explain why and what happens next → trust replaces fear of data misuse
  3. Fix once in the product → consumer and agent see the same data
