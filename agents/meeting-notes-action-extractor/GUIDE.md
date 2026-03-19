# WMatrix AI — Meeting Notes & Action Extractor Pro: Quick Start

You'll have structured meeting intelligence from messy notes in 60 seconds. Here's how.

---

## Step 1: Open Your AI Platform

| Platform | How to Load the Agent |
|---|---|
| **Claude** | Projects → Create Project → Custom Instructions → paste the system prompt |
| **ChatGPT** | Profile icon → Customize ChatGPT → Custom Instructions → paste the system prompt |
| **Gemini** | Settings → Gems → New Gem → paste the system prompt |

## Step 2: Paste the System Prompt

Open `universal/system-prompt.md` from this agent's folder. Copy the entire contents and paste it into the Custom Instructions field on your chosen platform.

**Checkpoint:** Start a new conversation and type "hello." The agent should respond with the Meeting Notes intake form — not a generic greeting. If it greets you normally, the system prompt was not loaded correctly.

## Step 3: Send This Input

Copy and paste the following into your conversation:

```
Meeting Type: Team Sync
Date: Monday, March 17, 2026
Duration: ~40 minutes
Attendees: Jake (Engineering Lead), Sarah (Head of Product), Mike (Senior Developer), Lisa (QA Lead)

Raw Notes:
Product sync Monday. Jake, Sarah, Mike, Lisa attended. ~40 min. Discussed the Q2 roadmap — Sarah wants to prioritize the API redesign but Mike thinks we should focus on the mobile app first. Jake mentioned the client demo is Thursday and we're not ready. Lisa said she'd "look into" the performance issues. Decided to push the feature freeze to March 28. Someone needs to update the changelog. Mike will handle the demo prep but needs design assets from Sarah by Wednesday. Also briefly talked about hiring — we need another frontend dev but nobody owns the job posting yet. Jake said budget is approved. Sarah mentioned that the analytics dashboard keeps crashing for enterprise users but didn't assign anyone to fix it. Mike suggested we move the standup to 10am instead of 9am, most people seemed fine with it but no final call was made.

Output Mode: Full Package
```

## Step 4: What You'll Get

```
┌─────────────────────────────────────────────────┐
│  MEETING INTELLIGENCE — FULL PACKAGE            │
├─────────────────────────────────────────────────┤
│                                                 │
│  ┌─ 1. Meeting Summary ─────────────────────┐   │
│  │  Purpose, context, key outcomes in        │   │
│  │  3-5 crisp sentences                      │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 2. Key Decisions ───────────────────────┐   │
│  │  What was decided, who approved,          │   │
│  │  what it affects                          │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 3. Action Items ────────────────────────┐   │
│  │  Owner, deadline, priority, status        │   │
│  │  + VAGUE COMMITMENT FLAGS for items       │   │
│  │  like "look into" or "someone needs to"   │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 4. Discussion Topics ───────────────────┐   │
│  │  Each topic with positions taken,         │   │
│  │  unresolved tensions, context             │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 5. Parking Lot ─────────────────────────┐   │
│  │  Items raised but not resolved,           │   │
│  │  needs follow-up in future meetings       │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 6. Follow-Up Email (Ready to Send) ─────┐  │
│  │  Professional recap email with decisions,  │  │
│  │  action items, and deadlines              │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 7. Next Meeting Agenda ─────────────────┐   │
│  │  Suggested agenda based on open items     │   │
│  │  and parking lot                          │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 8. Participation Analysis ──────────────┐   │
│  │  Who spoke, who was silent, balance       │   │
│  │  of input across attendees                │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 9. Risk Flags ──────────────────────────┐   │
│  │  Unassigned tasks, missed deadlines,      │   │
│  │  unresolved disagreements, blockers       │   │
│  └───────────────────────────────────────────┘  │
│  ┌─ 10. Meeting Effectiveness Score ────────┐   │
│  │  Rated on decision clarity, action        │   │
│  │  specificity, time usage, outcomes        │   │
│  └───────────────────────────────────────────┘  │
│                                                 │
└─────────────────────────────────────────────────┘
```

---

## That's It

You now have structured meeting intelligence — decisions, action items with accountability flags, a ready-to-send follow-up email, and risk flags — from raw, messy notes.

**Want more?** See `universal/user-guide.md` for all features, output modes, and troubleshooting.
**Need help?** support@wmatrix.org

*WMatrix AI — Intelligent agents that navigate your business forward.*
