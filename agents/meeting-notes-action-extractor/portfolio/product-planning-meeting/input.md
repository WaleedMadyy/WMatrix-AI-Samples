# Portfolio Input: Product Planning Meeting Transcript

## Context
This is a full 45-minute product planning meeting for a B2B SaaS company called "CloudSync" that makes data integration software. The meeting covers Q2 roadmap decisions, a major customer escalation, and team capacity allocation.

## Transcript

**Meeting:** Q2 Product Planning & Roadmap Review
**Date:** March 14, 2026
**Duration:** 48 minutes
**Location:** Zoom (recorded)
**Attendees:**
- Amanda Rodriguez (VP Product)
- David Kim (Engineering Director)
- Rachel Foster (UX Lead)
- Chris Patel (Customer Success Director)
- Nina Vasquez (Product Marketing Manager)
- Ben Okafor (Data Engineering Lead)

---

[00:00] Amanda: Good morning everyone. We have a packed agenda — three big topics today. First, Q2 roadmap finalization. Second, the Meridian Financial escalation that Chris brought to my attention yesterday. Third, we need to talk about the data pipeline performance issues Ben's team has been investigating. Let's jump in.

[00:30] Amanda: For context — we're heading into Q2 with 340 customers, $5.8M ARR, and a growth target of 15% this quarter. The board approved two additional engineering hires, so David, you'll have those by mid-April hopefully. Our Q1 NPS was 42, which is up from 38, but we need it above 50 by year-end. The biggest detractor theme in NPS comments? Performance. Users say syncs are too slow and error handling is confusing. That should inform what we prioritize.

[01:15] David: Before we get into roadmap, I want to flag something. We've been running at 92% engineering capacity for 3 months straight. My team is showing burnout signals — two engineers have mentioned it in 1:1s, and our code review quality has dropped. I'm not raising this to block anything, but we need to be realistic about what we can commit to this quarter. I'd rather commit to less and deliver it well than overcommit and ship buggy features.

[02:00] Amanda: That's a fair and important flag, David. Let's keep that front and center as we prioritize. How much capacity should we plan around?

[02:15] David: I'd say plan for 75% capacity. That gives us slack for bugs, on-call rotation, and the inevitable mid-quarter fire drill. With the current team of 8 engineers plus the 2 hires arriving mid-April, that's roughly equivalent to 7.5 engineer-months of focused feature work for Q2.

[02:45] Amanda: Noted. Okay, so here's what's on the roadmap candidate list based on customer feedback, sales requests, and our strategic goals:

Item 1: Real-time sync engine — our current batch processing runs every 15 minutes. Customers want real-time. This is our #1 feature request. Estimated effort: 4 engineer-months.

Item 2: Enhanced error handling and retry logic — when syncs fail, users get cryptic error messages and have to manually retry. We need clear error messages, auto-retry with exponential backoff, and an error dashboard. Estimated effort: 2 engineer-months.

Item 3: Salesforce bi-directional sync — currently we only support one-way sync from Salesforce. Customers want to write back to Salesforce. This unlocks a $2M pipeline of deals waiting on this feature. Estimated effort: 2.5 engineer-months.

Item 4: SOC 2 compliance automation — we're getting SOC 2 certified. Some of this is process, but the engineering team needs to implement audit logging, encryption-at-rest improvements, and access control tightening. Estimated effort: 1.5 engineer-months.

Item 5: Custom field mapping UI — users currently have to use our API to map custom fields. A UI would reduce onboarding friction significantly. Estimated effort: 1 engineer-month.

Item 6: Webhook notifications — customers want webhooks when syncs complete or fail so they can trigger downstream workflows. Estimated effort: 1 engineer-month.

[04:30] Amanda: So that's 12 engineer-months of work and we have 7.5 available. We need to cut roughly 40%. I want to hear from everyone before I make the call. David, engineering perspective first.

[04:50] David: Real-time sync is the right strategic investment, but it's also the riskiest. We'd need to rebuild the core sync architecture. I've been prototyping with Ben's team, and there are some gnarly concurrency issues. My honest assessment: it's a 4-month project if everything goes well, 6 months if we hit the concurrency wall. I'd rather split it — Phase 1 this quarter reduces batch interval from 15 minutes to 1 minute. Phase 2 in Q3 delivers true real-time. Phase 1 is about 2 engineer-months.

[05:30] Amanda: That's a pragmatic approach. What's the customer impact of 1-minute sync vs. real-time?

[05:40] Chris: Honestly? For 90% of use cases, 1-minute sync is indistinguishable from real-time. The customers screaming about real-time are mostly comparing us to competitors who advertise real-time but actually run 30-second batches. A 1-minute interval would satisfy most requests. The remaining 10% are truly real-time use cases — event-driven architectures, live dashboards — and those can wait for Phase 2.

[06:10] Amanda: Okay, that's really helpful. Chris, customer success perspective on the full list?

[06:20] Chris: Error handling is my #1. It's the top support ticket driver — 34% of all tickets are about sync failures. Users don't understand what went wrong, they can't fix it themselves, and they end up opening a ticket. If we fix error handling, I estimate we reduce ticket volume by 25-30%, which frees my team to focus on expansion and upselling instead of firefighting. The ROI on this is massive.

[06:50] Chris: Second priority for me is Salesforce bi-directional sync. I have 4 customers who specifically told me they'll expand their contract if we support write-back. That's $340K in expansion revenue sitting on the table. And Nina can speak to the sales pipeline.

[07:10] Nina: Yes — we have 6 deals in late-stage pipeline, totaling about $2M in ACV, where Salesforce bi-directional is the gating feature. Competitors Fivetran and Airbyte both support it. It's becoming table stakes. If we don't ship it by end of Q2, I think we lose at least 3 of those 6 deals.

[07:30] Rachel: From a UX perspective, I want to advocate for the custom field mapping UI. I know it's small compared to the other items, but it's the #1 onboarding friction point. New customers spend an average of 3 hours figuring out field mapping through our API docs. With a proper UI, that drops to 15 minutes. It directly impacts time-to-value, which impacts activation and retention.

[08:00] Rachel: I should also mention — I've been doing user research on the error handling UX and I have a design concept ready. I can share the Figma prototype after this meeting. The key insight from research is that users don't just want better error messages — they want the system to tell them exactly what to do to fix it. So the design includes a "resolution wizard" that walks users through fixing common sync errors step by step.

[08:30] Amanda: That's excellent, Rachel. The resolution wizard concept sounds powerful. Ben, anything from the data engineering side?

[08:40] Ben: Two things. First, on the real-time sync Phase 1 — David and I have been working on the near-real-time architecture. We've identified the main bottleneck in our current system. It's the transformation layer that runs after extraction. If we parallelize the transformation pipeline, we can get to 1-minute intervals without a full architectural rewrite. I'm confident in the 2-month estimate for Phase 1.

[09:10] Ben: Second, the performance issues I flagged last week. We have a growing problem with large-account sync times. Our top 10 accounts by data volume are experiencing sync times that have increased 40% over the last quarter. The root cause is that our sync jobs don't scale linearly — as data volume increases, sync time increases exponentially due to how we're doing deduplication. This isn't a feature request — it's a performance debt that will become a retention risk if we don't address it. I'd estimate 1 engineer-month to fix the deduplication algorithm.

[09:45] Amanda: Is that separate from the error handling work?

[09:50] Ben: Yes, completely separate. Error handling is about what happens when things fail. This is about making things not fail — or at least not slow to a crawl — in the first place. If our top 10 accounts start experiencing 2-hour sync times instead of 30 minutes, we'll have escalations from our highest-revenue customers.

[10:00] Amanda: Got it. That sounds like it belongs in Q2 regardless. David, does that fit?

[10:10] David: It fits. Ben can own the deduplication fix with one engineer. I'd classify it as infrastructure, not feature work, so it comes out of our 25% non-feature capacity allocation.

[10:20] Amanda: Perfect. Now let's talk about the Meridian Financial situation before I finalize the roadmap. Chris, give us the background.

[10:30] Chris: Meridian Financial is our third-largest customer — $95K/year contract, renews August 1. They've been using CloudSync for 2 years. Last week, their IT director, Margaret Chen, sent me an email that was...not great. She said their sync reliability has dropped from 99.5% to 96.2% over the last 2 months, their sync times have doubled, and they've had 3 critical failures in production that caused data discrepancies in their financial reporting system.

[11:00] Chris: She used the phrase "evaluating alternatives" and specifically mentioned Fivetran. They've already scheduled a Fivetran demo for next week. She wants a meeting with our VP of Product — that's you, Amanda — and a concrete remediation plan by Friday.

[11:20] Amanda: Okay, this is serious. $95K/year is significant, but more importantly, losing Meridian to Fivetran would be a reference customer loss in financial services — a vertical we're trying to grow in.

[11:35] David: The Meridian issues are likely related to the deduplication performance problem Ben just described. They're one of our top 10 accounts by data volume. The sync time degradation and reliability drop are symptoms of the same root cause.

[11:50] Amanda: Ben, if we prioritize the deduplication fix, how quickly would Meridian see improvement?

[12:00] Ben: If I start Monday, I can have the deduplication optimization deployed within 2 weeks. Meridian should see sync times drop by 50-60% and reliability should return to above 99%. But I'd want to set up dedicated monitoring for their syncs while we work on the fix so we can catch any failures in real-time and intervene before they hit production.

[12:20] Chris: That's the right approach. Can I also suggest we give Meridian a dedicated Slack channel with Ben's team for the next 30 days? Direct engineering access for a critical customer goes a long way.

[12:30] Amanda: Agreed. David, is Ben starting the deduplication fix Monday?

[12:35] David: Yes. I'll pull him off the sync engine prototype. The deduplication fix is now priority zero.

[12:40] Amanda: Chris, set up the Meridian meeting for me this week. I want to meet with Margaret Chen personally and present the remediation plan. Can you draft a talking points doc for me by Thursday?

[12:50] Chris: I'll have it to you Thursday morning. I'll include the specific reliability metrics, what we've identified as the root cause, the fix timeline, and the dedicated support plan.

[13:00] Amanda: Good. Now let me finalize the Q2 roadmap based on everything we've discussed. Given our 7.5 engineer-months of capacity, here's what I'm committing to:

Priority 1: Deduplication performance fix — 1 month (Ben, starts Monday)
Priority 2: Error handling with resolution wizard — 2 months (David's team + Rachel for UX)
Priority 3: Salesforce bi-directional sync — 2.5 months (David's team)
Priority 4: Near-real-time sync Phase 1 (1-minute intervals) — 2 months (Ben + David's team, starts after dedup fix)

That's 7.5 months. It fits.

[13:30] Amanda: What's NOT in Q2: SOC 2 engineering work moves to Q3. Custom field mapping UI moves to Q3. Webhooks move to Q3. Real-time sync Phase 2 is Q3/Q4.

[13:45] Rachel: I want to flag that the custom field mapping UI is a quick win that would help with onboarding. Can we at least do a simplified version?

[13:55] Amanda: How simplified?

[14:00] Rachel: Instead of the full drag-and-drop UI, we could ship a basic form-based field mapper that covers the 80% use case. I could design it in a week and it might only take 2 weeks of engineering.

[14:15] David: We could potentially fit that in if one of the new hires ramps up faster than expected. Let's keep it as a stretch goal — if we have capacity in June, we ship it. But it's not a commitment.

[14:25] Amanda: Agreed — stretch goal, not commitment. Rachel, have the design ready by end of April so we can move fast if capacity opens up.

[14:35] Nina: Quick question on sequencing — when will Salesforce bi-directional sync be demo-ready? I need to know so I can update those 6 deals in the pipeline.

[14:45] David: If we start it mid-April, demo-ready would be approximately June 1. Production-ready mid-June.

[14:55] Nina: That works. I'll tell the sales team June launch for Salesforce bi-directional. Can I get early access for 2 of the most critical deals so they can beta test in May?

[15:05] David: Beta access by mid-May is doable.

[15:10] Amanda: Nina, coordinate with David on the beta program. David, make sure we have a beta environment ready by May 15.

[15:20] Amanda: One last thing on SOC 2. Even though the engineering work is Q3, the compliance process itself is ongoing. Nina, where are we with the SOC 2 readiness assessment?

[15:30] Nina: We finished the gap analysis with the auditor last month. The big engineering items — audit logging and encryption — are the only blockers. Everything else on the process side is on track. If engineering delivers in Q3, we can be certified by end of Q4.

[15:45] Amanda: Good. Let's make sure SOC 2 is the #1 priority for Q3 engineering. David, start scoping the audit logging and encryption work now so we can hit the ground running in July.

[16:00] David: I'll assign one of the new hires to start the SOC 2 scoping in their first two weeks as a good onboarding project. Should have a scope doc by May 1.

[16:15] Amanda: Perfect. Okay, to summarize today's meeting:

Q2 roadmap is finalized. Dedup fix first, then error handling, Salesforce bi-directional, and near-real-time Phase 1. Custom field mapping is a stretch goal.

Meridian Financial — Ben starts the fix Monday, Chris sets up my meeting with Margaret, dedicated Slack support for 30 days, remediation plan by Thursday.

SOC 2 scoping starts with new hires, targeting Q3 engineering and Q4 certification.

Salesforce bi-directional beta in mid-May, production in mid-June. Nina manages the pipeline accordingly.

[16:45] Amanda: Does anyone have anything else?

[16:50] Rachel: Just one thing — I'd like to schedule user testing sessions for the error handling resolution wizard concept. Can I block time for the team to observe 3-4 user testing sessions in early April?

[17:00] Amanda: Absolutely. Schedule them and send calendar invites. I'd like to attend at least one.

[17:05] Ben: I also wanted to mention — we should probably start monitoring our sync performance metrics more proactively. The Meridian situation happened because we didn't catch the degradation early enough. I'd like to build an internal performance dashboard that alerts us before customers notice issues.

[17:20] Amanda: Great idea. Let's add that to your plate after the dedup fix ships. Target it for mid-April.

[17:25] David: One more thing — we still haven't decided on the Q2 engineering team offsite. People keep asking. Can we pick a date?

[17:35] Amanda: Let's do the last week of April. David, book a venue and send options by next Friday.

[17:45] Amanda: Alright, great meeting everyone. I feel good about the plan. Let's execute.

[17:48] End of meeting.
