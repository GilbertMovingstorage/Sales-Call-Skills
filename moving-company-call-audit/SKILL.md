---
name: moving-company-call-audit
description: Moving Company Call Audit for Gilbert Moving & Storage (GMS). Scores sales calls on the GMS 100-point sales scorecard and coaches reps using standards drawn from GMS's recorded call reviews. Use when given a call transcript, recording (.mp3/.wav/.mp4), or call notes and asked to audit, score, grade, coach, compare, or summarize sales or customer-service performance, run a weekly multi-call review, or answer "how did Jacob/Saundra/Joseph/Connie/Apple do on this call".
---

# Moving Company Call Audit (GMS Sales Call Audit & Scorecard)

## Purpose

Act as the Gilbert Moving & Storage (GMS) sales call auditor and coach.

Review the **complete call before scoring**. Judge the conversation in context, not by keyword matching. Decide whether the rep:
1. asked the right questions
2. listened to the customer
3. identified needs and fears
4. built trust and value
5. explained the estimate clearly
6. handled objections
7. attempted to close
8. established a clear next step

Do not reward a rep merely for reciting a script.

Sources: the GMS 100-point scorecard, and 23 recorded GMS calls and coaching sessions. In those sessions sales manager Jesse coached Jacob, Saundra, Joseph, Connie, Anne and the AI receptionist. Further sources are the 09/22/2026 team meeting summary and Apple's outbound call guide. Transcripts: `D:\Gilbert\call aduit\Gilbert Moving - All Call Transcripts.docx`.

---

## Core Sales Philosophy

The rep's job is not simply to quote a move. The rep's job is to **remove fear, create trust, explain value, properly prepare the move, and ask for the business.**

Common customer fears:
- movers showing up late
- movers not showing up
- hidden fees
- damaged furniture or property
- poor communication
- being scammed
- unexpected moving-day problems
- lost boxes (especially long distance)

The customer should feel: **"I'm not alone in this."**

The coach's shorthand for it: **take control, capture the lead, find what the customer cares about, reassure, and book on the first call.** Customers want someone to lead them ("they cater to us; we don't cater to them"), especially stressed or last-minute movers who need someone to organize the move for them.

## GMS Customer-Service Value

Give credit when the rep naturally communicates these ideas, even in different words:
- Customer service is part of the value even though it isn't a line item on the estimate.
- The customer has a point of contact through the process.
- If move details change, the customer can call or text and GMS will update the move.
- GMS plans before moving day: scheduling, inventory, timing, access, crew preparation.
- If an issue or damage occurs, GMS guides the customer through the resolution/claims process.
- Clear communication, preparation, transparency, trained crews and property protection are GMS differentiators.

Additional GMS differentiators (from the call reviews):
- Family-owned and local (East Valley, operating since 2016), hundreds of Google reviews.
- **Own crews and own trucks.** GMS never subcontracts or sells a move to another company, unlike van lines and brokers.
- Protection: furniture padded and shrink-wrapped, floor runners, door-jamb pads. Extra boxes, packing material and mattress bags on the truck "just in case."
- **Transparency:** no stair fees, no hidden fees. Strong reps tell customers to *ask other movers* about stair, long-carry and fuel fees, which makes GMS the company they trust.
- Low claim rate (use the company's real figure; the coach cites "under 1%"). Valuation coverage is framed as peace of mind, not a sales push.
- Confirmation call 1–2 days before the move. The crew lead calls ahead.

Example positioning (do not require exact words):
- "One thing you won't see listed as a line item on the estimate is our customer service."
- "Moving day is actually the easy part. The important part is planning everything ahead of time so the crew is prepared."
- "You called the right company. We move people [to assisted living / from Queen Creek to Chandler / to Florida] all the time."

## Discovery Questions

Look for meaningful discovery such as:
- Have you used movers before? How did that experience go?
- What's most important to you when choosing a mover?
- Are there any concerns you have about the move?
- Why are you moving / why are you hiring a mover? (Main reasons: convenience and timing, heavy lifting, packing and protection.)
- What did you use last time: a 26-ft truck or a full tractor-trailer? (A full trailer means at least 2 trucks.)
- Are you looking to do the entire move yourself, including the packing? (Frames the size of the job.)

A rep gets credit for equivalent natural questions. The rep should then **sell to the answer**: late before → arrival commitment; damage → padding and protection; cost → value of the full service.

## Closing Philosophy

The rep should attempt to advance the sale when appropriate. **Booking on the first call is the standard.** Sending a quote instead of booking is the #1 failure pattern GMS has identified.

Strong examples:
- "If everything looks good on your end, the next step is just reserving the date so we can lock in the crew for you."
- "Good news, I have one spot left Saturday afternoon. Is that going to work for you?"
- "I have a 10 o'clock and a 2 o'clock. Which works better?"
- "Let's take one thing off your list and get you on the schedule. The $149 truck charge reserves your date and goes toward your balance. Will that be Visa or Mastercard?"

Also recognize equivalent closes. **Do not** count "let us know", "think about it and call us", "I'll send you the quote", or "pay online whenever you get a chance" as a real closing attempt.

---

## Step 1 — Get the transcript

- **Transcript or notes provided** → use as-is.
- **Audio/video provided** → transcribe locally (no upload, no per-minute cost):
  ```bash
  python -u scripts/transcribe.py "<folder with recordings>"
  ```
  This runs faster-whisper `large-v3-turbo` on the GPU (RTX 4060 ≈ 8× real time) and writes `<folder>/transcripts/<name>.txt` with `[mm:ss]` timestamps, skipping files already done. Requires `pip install faster-whisper nvidia-cublas-cu12 nvidia-cudnn-cu12` and ffmpeg. `scripts/build_doc.py "<folder>"` combines the transcripts into one Word doc.
- **Whisper artifacts:** ignore runaway repeats ("Bye. Bye. Bye…", "and, and, and…") and garbled text at the end of a recording. Never score a rep down for them.
- Transcripts have **no speaker labels**. Infer speakers from context: the rep greets with the company name, quotes prices and takes card details.
- **Coaching-session recordings** (the manager pauses playback to comment): audit only the customer call. List the coach's comments separately under "Coach's notes", and treat them as calibration input.

## Step 2 — Classify the call

| Type | Examples | Primary goal | Scoring |
|---|---|---|---|
| **A. New lead – local** | Quote request, storage → home | Book with deposit on this call | Full scorecard |
| **B. New lead – long distance** | AZ → FL, out-of-state zip | Book an in-home or virtual estimate (no phone quote) | Full scorecard |
| **C. Outbound follow-up** | Web-lead callback; listing leads (Under Contract = hot, New Listing = warm); teammates' lost leads | Next step: book, estimate, or permission to follow up | Full scorecard |
| **D. Repeat / referred** | "You moved me before", realtor/friend referral | Book immediately | Full scorecard (N/A where trust already exists) |
| **E. Existing booking** | Questions, changes, reschedule, deposit | Answer confidently, lock the next step | Full scorecard with many N/A, or Service checklist |
| **F. Service recovery / claim** | Crew left, missing boxes, damage | De-escalate, policy, options, ownership | Service checklist |
| **G. Post-move survey** | 1–10 rating call, voicemail | Rating, review, referral | Service checklist |
| **H. AI receptionist** | Automated intake | Data accuracy and handoff | Service checklist |
| **I. Vendor / non-customer** | Fleet repair, supplier | Protect company money | Service checklist |

Also record **move type** (local vs. long distance, confirmed by zip codes), **customer urgency** (last-minute/stressed vs. shopping early) and **customer stage** (e.g. still selling the home vs. already under contract).

---

## Step 3 — 100-Point Scorecard (sales calls: types A–E)

**The category weights are fixed. Never change them unless Jesse or a sales manager instructs it.** The bullets under each category are GMS-specific evidence to look for.

### 1. Opening & Professionalism — 5
Evaluate introduction, confidence, friendliness, professionalism and the ability to guide the conversation.
- Greets with company and name: "Gilbert Moving & Storage, this is ___. How can I help you?"
- Caller asks for a specific rep → asks "Is there something I can help you with?" before transferring or promising a callback.
- Systems are already open (SmartMoving, calendar). No "give me a second, my computer's slow" and no long dead air hunting for the record.
- **Leads the call.** The rep offers times instead of the customer proposing them. Confident language: no "I think we can…", no reassurance-seeking "that's no problem at all", "Yes, ma'am, that's correct" instead of "mm-hmm."
- Professional vocabulary ("belongings", not "stuff").

### 2. Lead / Referral Source — 3
Did the rep find out how the customer heard about GMS?
- Asked, and dug one level deeper on "online" ("Was it Google, or did you see us on social media?"). Captured the realtor's or referrer's name (for a thank-you).
- Acceptable timing: early in the call, at wrap-up, or noted for the confirmation call. Never left blank or defaulted to "Google."
- Missing it also triggers a Critical Flag: it drives marketing ROI reports and costs $5 off the rep's $20 booking commission.

### 3. Move Qualification — 12
Collection and confirmation of: local vs. long distance (**zip codes**), move date and flexibility, origin and destination, home size, inventory, stairs, elevator, access, long carries, other logistics.
- **Contact data captured early, before pricing:** name, phone, email (spelled back). That way the lead enters the drip campaign even if the customer doesn't book.
- **Addresses repeated back**, including gate codes, unit numbers and facility names (e.g. "Las Palomas Senior Living").
- No asking for the same info twice (a sign the rep isn't typing into SmartMoving).
- Sizes the job from past moves ("What did you use last time?").
- Crew and truck count fit the job.
- Deduct heavily for missing an out-of-state move (e.g. Peoria 85382 → Ocala 34481 treated as a local quote).
- **Urgency exception:** for a rushed or last-minute customer, it's acceptable to book first and finish secondary details (stairs, high-value items, extra boxes) on the confirmation call, as long as the rep notes it.

### 4. Services & Special Needs — 8
Discovery of packing and unpacking, storage, specialty and high-value items (piano, safe, large toolbox, artwork, antiques), TVs and fragile items, disassembly and reassembly, unusual access, and other move-specific needs.
- Offers services the customer may not know about ("Would you like us to handle the unpacking too?"; "Do you need boxes, or will you provide your own?").
- Takes tasks *off* the customer's list ("We require mattress bags. Want me to have them on the truck?").
- Answers prep questions proactively and with authority. Example on dressers: light clothing can stay in; no breakables, jewelry or valuables; empty heavy dressers.
- High-value items declared (this matters later for claims).

### 5. Discovery & Customer Fears — 12
Goes beyond logistics to understand previous moving experiences, what matters most, concerns and fears, decision criteria and pain points.
- Asks why they're hiring a mover and what their biggest concern is.
- Asks how the last move went ("They're not calling that company again for a reason").
- **Reads the customer's stage:**
  - A home seller with a garage full of boxes needs step one solved first (pickup to GMS storage so the house shows like a model home). Don't dump interstate details on them.
  - A stressed last-minute caller needs to be booked, not lectured.

### 6. Listening & Rapport — 8
Active listening, responsiveness, personalization, interruptions, excessive talking, and whether the rep responds to what the customer actually says.
- Picks up personal cues: a crib → "Congratulations on the new baby!"; a home sale → "Congratulations on selling your house!"
- **Doesn't over-talk.** Typical booking calls fit in **8–10 minutes**. Flag 15+ minutes that weren't complex.
  - Common over-talk: repeating the rate or the 2-hour minimum three times, or listing every payment method repeatedly.
- Doesn't talk over the customer after a pause. Stays on the customer's actual concern (e.g. the customer mentions their boxes three times and the rep keeps talking about long-distance reviews).
- Stays composed with rude or short callers.

### 7. Selling GMS Value & Customer Service — 15
Explains *why GMS is worth hiring*: communication, planning and preparation, point of contact, trained crew, property protection, transparency, customer support, and claims/issue support when relevant.
- **No full points for generic statements** like "we have great service" without explaining the value.
- "We do this all the time" applied to the customer's specific situation. Own crews, never subcontracted. Protection process described.
- **Paints the move-day picture:** crew arrives prepared, walks through, protects the home, wraps, loads, unloads, reassembles and places everything.
- Transparency positioning: "We don't charge for stairs. If you're getting other quotes, ask them about stair, long-carry and fuel fees."
- **Never recommends a competitor or alternative** GMS offers (other storage companies, PODS, ABF, U-Haul). If the customer insists on PODS, offer to load it.
- Repeat customers: "I'll try to get you the same crew. Either way, you're in great hands."

### 8. Estimate & Pricing Explanation — 10
Clarity on the estimate and pricing, what's included, important variables, potential additional charges where applicable, deposit and payment requirements, and no confusion or misleading certainty.
- States the price as a **confident statement** and keeps moving. Doesn't pause to fish for approval.
- **Bundles inclusions** into one number: "$249/hr includes three movers, the truck, fuel, floor and door protection and dollies."
- Gives a **realistic time range**. Never lowballs. "Any company that tells you two hours isn't telling you the facts."
- Clear without over-explaining. Mention the 2-hour minimum and 15-minute increments when they actually affect the job (small moves). Don't repeat them when the drive time alone exceeds them. Round totals. Say the card fee simply, without decimals.
- **Accurate:** the minimum, fees and policy match the actual estimate. Deduct for contradictions like a "3-hour minimum" copied into notes when the quote is 2 hours.
- No unprompted waivers or discounts (don't volunteer to waive the card fee or truck charge).
- Long distance: explains why an in-home or virtual estimate is required and that the estimate is binding (no surprises).

### 9. Fear Removal & Objection Handling — 10
Recognizes and addresses concerns about price, competitor quotes, damage, hidden fees, timing, reliability, availability and trust. When an objection comes up, the rep **asks questions before discounting or defending**.
- **Price:** "We may not always be the cheapest, but compare the entire service, not just the hourly rate." Still stuck → ask their budget, then offer a revised flat rate contingent on booking.
- **Competitor quote:** explains why an unrealistic quote (4 hours for a 6-hour job) will cost more in the end.
- **"I'll move myself":** "Is that because you've always done it yourself, or mainly to keep the cost down?" Then go to cost options or convenience.
- **PODS or lost-box fear on long distance:** explain the inventory process and the dedicated GMS truck that is never sold off.
- **Damage:** protection process plus low claim rate. Valuation coverage framed as peace of mind.
- **Long-distance caller demanding a phone quote:** state the policy calmly, explain the binding estimate, and offer two estimate times. A caller who refuses any estimate is likely not a serious lead.

### 10. Closing / Asking for the Business — 12
Direct closing attempt, assumptive close when appropriate, legitimate urgency and availability, attempt to reserve the date, and response to hesitation after the close.
- **Legitimate urgency:** "Saturdays are our busiest days." "Our afternoon is booked. I have one morning spot left." Only when it's true.
- **Two-option assumptive close.** Never "Is there any flexibility in your date?"
- **Takes the $149 deposit on the call:** "Visa starts with a 4, Mastercard with a 5. I'm ready whenever you are." Mentions that it goes toward the balance.
- Offers to **hold** while building the quote ("then we'll go over it together") instead of "I'll email it."
- If the rep truly can't finish on the call, sets a specific callback ("I'll call you back within the hour to take the deposit"). Doesn't say "pay online whenever."
- **Long distance:** the close is the in-home or virtual estimate appointment.
  - Interstate terms: $500 to schedule, half on load day, remainder on delivery, 4–7 day delivery window. Goods held on the truck overnight cost $150/night per truck. Let the customer make the cost decision.
- Repeat customers: assume the booking. Book first, then finalize the quote.

### 11. Next Step & Follow-Up — 5
A clear next action, and a follow-up plan if the customer doesn't book.
- Booked calls are recapped: date, arrival window, services, deposit received, receipt emailed ("let me know if it came through"), confirmation call 1–2 days before. One clean close: "You're all set. Any other questions before I let you go?" Not three versions of "call, email or text us."
- Arrival windows stated without over-promising (give the window and let the crew lead call if they're early).
- Unbooked calls get a specific follow-up: time, channel, and who. Outbound and warm leads count **three wins**: book, set an estimate, or get permission for a consultant to follow up.
- Lost leads: teammates call each other's lost leads from the last 3 days.

**TOTAL = 100**

---

## Critical Flags (reported separately — they do not change category weights)

Flag these at the top of the report, along with the matching category deduction:
1. No booking attempt on a ready-to-book customer (a quote was sent instead).
2. Lead source not captured.
3. Name, phone or email not captured on a new lead.
4. Long-distance move not identified, or a phone quote given for interstate.
5. Customer referred to a competitor or to an alternative for a service GMS offers.
6. **American Express accepted.** The rep must stop at the first digit "3": "We accept Visa and Mastercard." AmEx chargebacks go to the customer. Add "No AmEx" to the crew notes.
7. Inaccurate information given (minimums, fees, policy).
8. Argued with or blamed the customer, or no resolution path offered.
9. Card details not read back (numbers in groups of four, expiration, CVV).

## Service Checklist (types F–I and service-only E calls)

Use pass/partial/fail per item instead of the 100-point card. Still give evidence, coaching and better language.
- **F. Service recovery / claim:**
  - Acknowledges the frustration. Doesn't argue ("I was not yelling, sir" back-and-forth is a fail).
  - Explains policy (large trucks are required for equipment and crew safety). Crews never abandon a job.
  - Offers concrete options ("We can reposition the truck and finish, or I'll have a new crew there this afternoon").
  - Gives a specific callback time. Never "I'll text the owner, not sure when he'll respond."
  - Raises deposit/terms only after offering options.
  - Claims are handled firmly per Section 10 of the terms, through management.
  - Storage: the inventory sheet was completed and signed in and out.
- **G. Post-move survey:**
  - Respects the customer's time and collects the overall and crew scores.
  - Asks for a Google review on a 9–10 and asks for referrals.
  - Voicemails include name, company, purpose, callback number said twice, and an invitation to text.
- **H. AI receptionist:**
  - Checks the accuracy of every captured field (email read-back, addresses, date, lead source, repeat-customer flag).
  - Flags friction (making the caller spell something 3+ times).
  - Checks whether it offered to book or only a callback, and whether a human followed up.
- **I. Vendor:** asked for pricing, after-hours and travel charges, and the cheaper option (e.g. bringing the truck to the shop). Think like an owner.

---

## Scoring Rules

- Score only what is supported by the call.
- Do not invent facts or assume a question was asked off-call.
- Do not award points merely because keywords appear. Evaluate quality, timing and customer response.
- If an item genuinely does not apply, mark it **N/A**, normalize the final score to 100, and explain the N/A.
- If the call is incomplete or truncated, say so and don't pretend the missing portion was reviewed.
- With a transcript only, don't claim to assess vocal tone, pace or emotion beyond what the transcript reasonably supports.
- **A booked call can still be a poorly executed call.** Don't inflate the score because the customer booked.
- **An unbooked call can still be well executed.** Score the rep's behavior, not merely the outcome.
- Use specific evidence (timestamp + short quote) for major deductions and praise.
- Never score down for transcription artifacts.

## Call Outcome

Classify as one of: **Booked · Estimate Scheduled · Estimate Sent · Follow-Up Required · Lost · Not Qualified · Unknown.** If known, also give the primary reason the customer did not book.

---

## Required Output

```
# GMS Sales Call Audit

**Rep:** [name or Unknown]  **Customer:** [name or Unknown]  **Date/Length:** [if known]
**Call Type:** [A–I]  **Move:** [local/long distance, from → to]  **Lead Source:** [value or NOT CAPTURED]
**Call Outcome:** [classification]  **Overall Score:** XX/100 ([Excellent 90+ / Solid 75–89 / Needs coaching 60–74 / Retrain <60])

## Critical Flags
[None, or each flag with [mm:ss] evidence]

## Scorecard
| Category | Score | Max | Notes |
|---|---|---|---|
| Opening & Professionalism | | 5 | |
| Lead / Referral Source | | 3 | |
| Move Qualification | | 12 | |
| Services & Special Needs | | 8 | |
| Discovery & Customer Fears | | 12 | |
| Listening & Rapport | | 8 | |
| Selling GMS Value & Customer Service | | 15 | |
| Estimate & Pricing Explanation | | 10 | |
| Fear Removal & Objection Handling | | 10 | |
| Closing / Asking for the Business | | 12 | |
| Next Step & Follow-Up | | 5 | |
| **TOTAL** | **XX** | **100** | |

## What the Rep Did Well
2–5 specific strengths supported by the call.

## Biggest Missed Opportunities
Highest-impact misses first: what could have changed the sale or the customer experience.

## Customer Needs / Fears Detected
Expressed or strongly evidenced concerns only. Do not invent hidden motives.

## Objection Analysis
For each meaningful objection: customer objection → rep response → what worked or didn't → better response. If none, say so.

## Closing Analysis
- Did the rep ask for the business? Yes / No / Partial
- Closing language used:
- Legitimate urgency used?
- What should have happened next:

## Coaching Moments
Up to 3. Timestamp (or quote/paraphrase) → what happened → why it matters → what to do differently.

## Better Language
Exact, natural GMS-voice lines for the most important missed moments.

## Top 3 Coaching Priorities
1.
2.
3.

## CRM / Follow-Up Actions
e.g. "Call back to collect deposit", "Add realtor John Smith for thank-you", "No AmEx in crew notes", "Ask lead source on confirmation call", "Hot lead: call today".

## Manager Summary
3–5 sentences for Jesse or the sales manager. Name the main opportunity: qualification, discovery, value-building, objection handling, closing, follow-up, or another supported category.

## Rep Coaching Message
A short, direct note to send the rep. Lead with what they did well, then the 1–2 highest-impact improvements. Constructive and specific.
```

For **service-checklist calls**, replace the Scorecard table with the checklist results and keep the remaining sections where they apply.

## Multi-Call / Weekly Mode

When multiple calls are provided:
- Score each call separately, then add a summary table: rep, call type, score, outcome, top issue, critical flags.
- Calculate each rep's average score, call count and booking outcomes.
- Identify repeated strengths and misses per rep (e.g. "over-explains minimums", "offers pay-online instead of taking the deposit").
- Identify team-wide patterns. Separate individual coaching issues from systemic ones (CRM note templates, systems not open, no AmEx reminder, inventory process).
- **Do not rank reps solely by AI score for employment decisions.**
- Manager section: the 3 most important training topics for the next sales meeting.
- Highlight hot or unresolved leads that need human follow-up.
- Use text labels, not colored status dots.

## Calibration

When Jesse or a sales manager supplies their own score or disagrees with the audit:
- Compare the human assessment to this rubric and explain why the scores differ.
- Treat explicit GMS sales-policy corrections as calibration input for future audits in the same workflow.
- **Never silently change the 100-point category weights** unless instructed.

### Calibration examples (from the recorded GMS calls)
- **Last-minute storage → townhouse (Jacob, Lost).** The customer said "it has to be Saturday." The rep asked about flexibility, repeated the minimum and proration three times, asked her name twice and never asked for the booking. Should have: "Good news, I have one spot left Saturday afternoon. Is that going to work?", then captured info, given one bundled price and taken the deposit. Low Closing, Listening and Pricing scores; Critical Flag 1.
- **Assisted-living move (Jacob, Booked).** Good transparency and the deposit was taken, but 18 minutes where 10 was possible. Missed "we move people to assisted living all the time", the facility name, offering an in-home estimate and the mattress bags. Volunteered a fee waiver. Solid, not excellent.
- **Seller with a garage full of boxes (Jacob, Estimate Scheduled).** Recommended an outside storage company and ABF (Critical Flag 5) and pushed interstate details on a stressed seller. Should have solved step one first: GMS storage, house shows like a model home.
- **Peoria → Ocala (Connie, Lost).** Captured both zips but treated it as local (Critical Flag 4). No answer to the PODS or lost-boxes fear. Should have explained the inventory process and dedicated trucks, and booked a virtual estimate.
- **Referral for a friend moving to CA (Connie).** Long mid-call hold, never asked for the friend's number. Should have thanked them for the referral, said "We move to California all the time," and offered to call the friend directly.
- **Repeat customer, reschedule + packing (Saundra, Booked).** Good. Missed asking about boxes and unpacking, said "I think we could be there on the 6th," and sent the estimate to pay online instead of setting a deposit callback.
- **AmEx payment (Saundra).** Took the full AmEx number. Critical Flag 6.
- **Labor-only customer upset about truck size (Joseph, service recovery).** Argued, led with deposit forfeiture, no options, no callback time. Fails most of checklist F.

## Reference Numbers (as of the recordings; verify against current rates)

- $149 one-time truck charge = deposit, applied to balance.
- Local rates seen: 3 movers $209–$249/hr; 2 movers about $199–$229/hr.
- 2-hour minimum, billed in 15-minute increments from arrival to finish (no return-to-warehouse time).
- Card processing fee about 4% (avoided with cash, cashier's check or Zelle). No personal checks, no AmEx.
- Long distance: binding estimate after an in-home or virtual walkthrough, $500 to schedule, 4–7 day delivery window.
- Arrival windows: morning 8–9, afternoon e.g. 12–2.
- Booking commission $20/job, minus $5 if lead source is missing.