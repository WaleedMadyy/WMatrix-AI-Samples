# WMatrix AI — Meeting Notes & Action Extractor Pro: Complete Meeting Intelligence in 60 Seconds

> Decisions, action items, follow-up emails, risk flags, and effectiveness scoring — extracted from any transcript or notes. Nothing falls through the cracks.

## What It Does

Transforms raw meeting notes, transcripts, or recording summaries into a **complete 11-section meeting intelligence package** that replaces the original notes as the working document. Every output extracts:

1. **Meeting Summary** — Executive-level 3-5 sentence brief with metadata. Someone reading only this section knows what happened, what was decided, and what happens next.
2. **Key Decisions** — Every decision with maker, context, implications, dissent/conditions, and deferred decisions documented separately.
3. **Action Items** — Full table with owner, deadline, priority, dependencies, and status. Vague commitments flagged with specific clarification questions. Deadline conflicts and overloaded owners identified.
4. **Discussion Topics** — Themed extraction organized by topic (not chronology), preserving each participant's perspective and linking discussions to decisions and action items.
5. **Parking Lot** — Deferred items with who raised them, why deferred, and suggested forum for follow-up. Prioritized: address this week, next meeting, or backlog.
6. **Follow-Up Email Draft** — Send-ready, under 200 words. Decisions, action items with owners and deadlines, and next steps. Copy-paste and send.
7. **Next Meeting Agenda Suggestions** — Proposed agenda with time allocations, topic owners, pre-meeting prep requirements, and attendee recommendations (required, optional, add).
8. **Attendee Participation Analysis** — Per-attendee contribution levels with evidence, engagement signals, and specific recommendations for improving participation balance.
9. **Risk/Blocker Flags** — Active blockers, identified risks, and implicit risks inferred from discussion context. Each with resolution paths and escalation recommendations.
10. **Meeting Effectiveness Score** — 1-10 score with 6-dimension breakdown, what worked well, what to improve, and format/duration/facilitation recommendations.
11. **Meeting Validation Protocol** — Completeness, accuracy, and actionability checks with input quality assessment and flags for missing information.

**This is not a transcript summarizer.** This agent extracts strategic intelligence — not just what was said, but what it means for the project, the team, and the timeline. It catches the vague "let's circle back on that" commitments that become forgotten action items, flags implicit risks nobody explicitly stated, and produces outputs that replace the original notes as the working document.

## Who It's For

- Managers leading cross-functional teams with 5-15 meetings per week
- Founders who need every decision and commitment captured precisely
- Project managers tracking deliverables across multiple workstreams
- Consultants documenting client meetings with professional follow-ups
- Team leads who need accountability without micromanagement
- Executive assistants processing meeting backlogs
- Anyone who has ever left a meeting thinking "what did we actually decide?"

## What You Get

| Tier | Name | Price | What's Included |
|---|---|---|---|
| Universal | Explorer | $39 | System prompt + user guide + config + examples (2 input/output pairs) |
| Claude Code | Navigator | $59 | `/meeting-notes` slash command + CLAUDE.md + examples |
| Both | Voyager | $79 | Everything + team license + portfolio project |

## Quick Start

1. Copy `universal/system-prompt.md` into your AI's system prompt field (Claude, ChatGPT, Gemini)
2. Paste your meeting notes, transcript, or recording summary
3. Get the full 11-section meeting intelligence package in 60 seconds
4. Copy-paste the follow-up email, assign the action items, and move on

**Three modes:** Say "quick" for summary + actions only. Say nothing for the full package. Say "manager review" for expanded leadership analysis.

## Output at a Glance

| Section | What It Delivers | Why It Matters |
|---|---|---|
| Meeting Summary | 3-5 sentence executive brief with metadata | Anyone can understand the meeting in 30 seconds |
| Key Decisions | Decision + maker + context + implications + dissent | No more "what did we decide?" confusion |
| Action Items | Owner + deadline + priority + dependencies + vague flags | Every commitment tracked, every gap flagged |
| Discussion Topics | Themed extraction with preserved perspectives | Nuanced record, not flattened consensus |
| Parking Lot | Deferred items with priority and follow-up forum | Nothing forgotten, everything tracked |
| Follow-Up Email | Send-ready, under 200 words | Copy-paste, hit send, move on |
| Next Meeting Agenda | Time allocations + prep + attendee recommendations | Next meeting starts productive |
| Participation Analysis | Contribution levels + engagement signals + recommendations | Identify imbalances, improve dynamics |
| Risk/Blocker Flags | Active blockers + risks + implicit risks + escalation paths | Catch problems before they escalate |
| Effectiveness Score | 1-10 with 6 dimensions + improvement recommendations | Make every meeting better than the last |
| Validation Protocol | Completeness + accuracy + actionability checks | Trust but verify — the agent checks its own work |

## Example Excerpt

**Input:** 45-minute product standup transcript with 6 attendees, messy notes, mixed decisions and vague commitments.

**Output excerpt (Action Items section):**

| # | Task | Owner | Deadline | Priority |
|---|------|-------|----------|----------|
| 1 | Fix Stripe webhook event-dropping issue | Leo Mendez | March 13 (tomorrow) | Critical |
| 2 | Complete payment API refactor (remaining 20%) | Leo Mendez | March 13 (Wed EOD) | Critical |
| 3 | Fix 2 critical checkout flow bugs (release blockers) | **[UNASSIGNED]** | March 14 | Critical |

**Vague Commitment Flagged:** Leo said "I'll try to have it done by Wednesday" — not a firm commitment. Clarification: "Is Wednesday EOD a commit or a best-case? What is the fallback if the API is not ready?"

## How It Compares

| Capability | Manual Notes | Otter.ai ($17/user/mo) | Fellow ($9/user/mo) | Meeting Notes & Action Extractor Pro |
|---|---|---|---|---|
| Meeting summary | You write it | AI-generated from recording | Template-based | Executive-level brief from any input format |
| Decision extraction | Scattered in notes | Basic | Manual entry | Full context: maker, implications, dissent, deferrals |
| Action items | Buried in paragraphs | Auto-detected (basic) | Template-based | Owner + deadline + priority + deps + vague flags |
| Vague commitment flagging | Never happens | No | No | Catches "let's circle back" — converts to clarification questions |
| Follow-up email | You write it (20 min) | Basic summary | Template | Send-ready, under 200 words, 60 seconds |
| Next meeting agenda | You build it manually | No | Template suggestions | Auto-generated with time allocations and attendee recs |
| Participation analysis | Subjective impression | Speaker time % | No | Contribution analysis with engagement signals and recs |
| Risk/blocker detection | Missed until too late | No | No | Active blockers + implicit risks + escalation paths |
| Effectiveness scoring | Never measured | No | Meeting quality metrics | 6-dimension scoring with improvement recommendations |
| Input flexibility | Your notes only | Recording required | Calendar integration required | Any format: transcripts, notes, bullets, summaries |
| Setup required | None | Calendar + recording integration | Calendar integration | None — paste any meeting content |
| Team of 10 annual cost | Your time (priceless) | $2,040/yr | $1,080/yr | One-time $39-$79 |

## Pricing

| Tier | Name | Price | What's Included |
|---|---|---|---|
| Universal | Explorer | **$39** | System prompt + user guide + config.json + 2 example pairs |
| Claude Code | Navigator | **$59** | Slash command `/meeting-notes` + CLAUDE.md + settings + examples |
| Both | Voyager | **$79** | Everything above + team license + portfolio project |

**The math:** Meeting intelligence platforms charge $9-$19/user/month with required integrations and recordings. For a team of 5, that is $540-$1,140/year. This agent works with any input format — transcripts, notes, bullet points, even voice memo summaries — for a one-time purchase of $39-$79.

## Support

Questions or issues: support@wmatrix.org

---

*WMatrix AI is a product brand of WealthMatrix. © 2026 WealthMatrix. All rights reserved.*
