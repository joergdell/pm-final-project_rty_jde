# PRD & Prototype Sprint

> **Module 4 · Lab 2.** Repo file `04-roadmap/prd-and-prototype.md` — part of your submission.
> Do the lab in the **Module 4 · Exercise 2 Guide** (linked from the Module 4 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It deepens the top feature from your `roadmap-prd-prototype.md` and feeds the **Roadmap, PRD & Prototype** slide of your Module 6 deck.

## Responses

- **The "Now" feature I'm scoping (name + one-line core description):** Reliable mobile income-document step. A mobile upload that works on the first try, plus a short in-flow explanation of why income is asked, what it means and how long it is kept, so the consumer can finish the plan in one sitting without calling.
- **My finalized Must-Haves (after overriding the AI):**
  1. Photo upload succeeds on mobile for typical phone photos (size limit to be confirmed with engineering). Evidence: T-201, 853 journeys with a document that never arrived.
  2. Upload progress and a clear confirmation or error with a retry, so a document never disappears silently.
  3. Short in-flow text covering purpose, definition (this month or a normal month) and retention period. Evidence: T-206, N-01, N-06; 16.2% of agent contacts ask why income is requested.
  4. Entered answers are kept when the user goes back or leaves and returns. Evidence: T-204, N-01 ("I closed it and meant to come back").
  - Note: this repo holds no AI draft of the PRD, so I cannot show what I overrode. The list reflects my own scoping against the evidence.
- **What I demoted from Must → Should/Won't, and why:**
  - *Skip the document under a set amount* (B5 alternative): Must → Should. It changes the affordability check, and the threshold needs a compliance decision (N-12). The upload fix solves the problem without that risk.
  - *Reminder before the first instalment (T-207):* Must → Should. It is a real defect, but it does not sit on the document step I am scoping.
  - *One plan for several claims, pay-day payment date, chat assistant on every page:* Won't for this release. Multi-claim is a new feature and my value proposition clears obstacles first. My Strategic Map found no strategic case for the pay-day date. The chat already confirms plans without explaining missed-payment consequences (T-208), so extending it would spread that gap.
- **One thing my PRD makes explicit that a vague brief would have missed:** It states what "income" means (this month or a normal month) and how long it is kept, as a requirement with its own wording. A brief saying "fix the upload" would miss this, yet about 460 of the 1,313 users lost at this step are not explained by T-201 *(derived)*, so fixing only the upload may leave much of the drop-off in place. The PRD also makes the guardrail explicit: missed payments within 60 days must stay at or below 19.0%.
- **Where the prototype revealed a gap in my PRD logic (what I updated):** No interactive prototype has been built yet, so this is not a real prototype finding. Drawing the text wireframe in `roadmap-prd-prototype.md` exposed one open point: the PRD did not say what happens to an upload in progress when the user leaves and returns. I treat it as an open requirement (resume or restart, to be decided) and will re-check it once a prototype exists.
- **My shareable prototype URL:** _(not available: no prototype has been built yet; a text wireframe is in `roadmap-prd-prototype.md`)_
