# Portfolio Brief: Product Planning Meeting

## Overview

This portfolio project demonstrates the Meeting Notes & Action Extractor Pro processing a realistic, full-length product planning meeting transcript for a B2B SaaS company. The scenario is designed to showcase all 11 output sections at their maximum depth, including complex decision chains, multi-person action item extraction, vague commitment flagging, implicit risk detection, and a high-stakes customer escalation handled mid-meeting.

## The Scenario

**Company:** CloudSync — a B2B data integration platform (340 customers, $5.8M ARR)
**Meeting:** Q2 Product Planning & Roadmap Review
**Duration:** 48 minutes
**Attendees:** 6 (VP Product, Engineering Director, UX Lead, Customer Success Director, Product Marketing Manager, Data Engineering Lead)

### Why This Scenario Was Chosen

This meeting was selected because it contains the exact complexity that the agent is built to handle:

1. **Multi-factor prioritization:** 6 feature candidates competing for 7.5 engineer-months of capacity. Decisions are influenced by revenue data ($2M pipeline), retention data (34% of support tickets), customer escalation ($95K account at risk), and engineering burnout signals. The agent must extract how each factor influenced the final roadmap.

2. **Critical customer escalation mid-meeting:** The Meridian Financial situation ($95K/year, evaluating Fivetran) introduces urgency that reshuffles priorities. The agent must capture the remediation plan, track the engineering resource reallocation (Ben pulled off prototype), and flag the cascading timeline impact.

3. **Complex dependency chains:** The deduplication fix, near-real-time sync Phase 1, and performance monitoring dashboard are sequentially dependent and all assigned to Ben Okafor. The agent must identify this single-point-of-failure risk without it being explicitly stated.

4. **Vague commitments mixed with firm commitments:** The meeting produces 18 specific action items alongside 3 vague commitments ("let's make sure SOC 2 is #1 for Q3" without scheduling a planning session, a stretch goal with no trigger criteria, and a casual "attend at least one" without a calendar commitment). The agent must distinguish between them.

5. **Deferred decisions with strategic implications:** SOC 2 engineering is deferred to Q3, but no one asked whether Q3 enterprise deals require SOC 2. The agent must infer this implicit risk.

6. **Cross-functional team dynamics:** Engineering flagging burnout, Customer Success driving urgency, Product Marketing providing pipeline data, UX advocating for onboarding improvements, and a VP making trade-off decisions. The participation analysis must capture each person's role and contribution quality.

## What the Output Should Demonstrate

### All 11 Sections at Full Depth

| Section | What This Scenario Tests |
|---------|------------------------|
| **Meeting Summary** | Can the agent distill a 48-minute meeting with 3 major topics into a 5-sentence executive brief that stands alone? |
| **Key Decisions** | 7 decisions plus 3 deferred — each with maker, context, implications, and dissent. Tests extraction of both unanimous and contested decisions. |
| **Action Items** | 18 items across 6 people with specific deadlines. Tests owner extraction, deadline parsing, dependency identification, priority classification, and vague commitment flagging (3 items). |
| **Discussion Topics** | 4 themes, 8 sub-topics. Tests ability to organize by theme (not chronology), preserve differing perspectives, and link discussions to decisions/actions. |
| **Parking Lot** | 5 deferred items — tests distinguishing between explicitly deferred (webhooks, SOC 2) and implicitly deferred (hiring beyond 2 approved positions). |
| **Follow-Up Email** | Under 200 words, covers 4 major topic areas. Tests conciseness, send-readiness, and correct attribution of action items. |
| **Next Meeting Agenda** | 5 topics with time allocations for a 30-minute follow-up. Tests ability to identify what needs checking in 2 weeks. |
| **Participation Analysis** | 6 attendees with varying contribution levels. Tests attribution accuracy, engagement signal detection, and constructive recommendations. |
| **Risk/Blocker Flags** | 2 active blockers, 4 identified risks, 3 implicit risks. Tests the critical distinction between stated risks and inferred risks (labeled [Inferred]). |
| **Effectiveness Score** | 9/10 with 6-dimension breakdown. Tests ability to score a well-run meeting fairly and still identify 3 specific improvements. |
| **Validation Protocol** | Full checklist with 3 minor flags. Tests honest self-assessment of extraction completeness and input quality. |

### Key Behaviors to Verify

- Ben Okafor is identified as a single point of failure across 3 critical deliverables (this is inferred, not stated)
- SOC 2 impact on Q3 enterprise pipeline is flagged as an implicit risk (nobody raised it)
- Rachel's stretch goal compromise is captured as a decision with dissent
- The deduplication fix is correctly classified as infrastructure (not feature work, from 25% non-feature capacity)
- The follow-up email is under 200 words and copy-paste ready
- The effectiveness score rewards the meeting's strong decision-making despite identifying process improvements
- Vague commitment #2 (stretch goal trigger) includes a specific clarification question about when the stretch goal converts to a real commitment

## Evaluation Criteria

A successful extraction of this transcript should score 4.8+ across all 5 dimensions:

| Dimension | What "Excellent" Looks Like |
|-----------|---------------------------|
| **Accuracy** | All 18 action items captured. All 7 decisions extracted with correct attribution. No fabricated information. Inferred risks clearly labeled. |
| **Relevance** | Every section adds value. No filler. The email is actually sendable. The agenda is actually useful for the next meeting. |
| **Formatting** | Consistent headers, clean tables, clear section separation. The document can be skimmed in 2 minutes or read in detail in 10. |
| **Completeness** | All 11 sections present. Validation protocol catches its own gaps. Parking lot includes implicit deferred items. |
| **Usability** | A project manager could take this output and immediately: send the email, create Jira tickets from the action items, set up the next meeting, and brief their VP — without returning to the original transcript. |
