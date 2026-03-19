# Cold Email Personalizer Pro

> A complete outbound sales system — not just an email writer. Research, sequence, test, adapt.

## What It Does

Produces a **complete outbound campaign package** for any B2B prospect:

1. **Prospect Research Brief** — Analyzes the prospect's role, company, priorities, pain points, and trigger events to find the strongest personalization angle
2. **Full 4-Email Sequence** — Opener → Quantitative → Objection Killer → Breakup, each with a unique angle that builds a coherent narrative arc
3. **3 Subject Line Variants** — Different hooks for A/B testing Email 1 (trigger event, pain/challenge, curiosity/result)
4. **ICP Alignment Analysis** — Scores how well the prospect matches your ideal customer profile and calibrates language accordingly
5. **Tone Adaptation** — Supports 5 tone profiles (Direct, Consultative, Casual, Executive, Challenger) to match your brand and audience

**This is not a template filler.** The agent builds a research-backed campaign that could only be sent to one person — with every email designed to drive replies, not just opens.

## Who It's For

- SDRs and BDRs sending 50-100 emails per day
- Founders doing their own outbound sales
- Account Executives personalizing for high-value targets
- Sales managers building sequence playbooks for their team
- Lead generation agencies running campaigns for clients

## What You Get

### Universal Format (Works with Any AI)
- `system-prompt.md` — The core agent prompt (paste into Claude, ChatGPT, Gemini)
- `user-guide.md` — Step-by-step usage instructions
- `config.json` — Recommended model settings
- `examples/` — 2 complete input/output examples
- `portfolio/` — Full campaign showcase demonstrating all 5 features

### Claude Code Native Format
- `.claude/commands/cold-email.md` — Run `/cold-email` directly in Claude Code
- `CLAUDE.md` — Agent instructions loaded automatically (includes web research capability)
- `examples/` — Same examples as universal

## Quick Start

**Universal:** Copy `universal/system-prompt.md` into your AI's system prompt → provide prospect info + what you sell → get a complete campaign package.

**Claude Code:** Copy `claude-code/` contents to your project → run `/cold-email [prospect details]` → get a complete campaign with live web research.

## What You Get Per Campaign

| Element | Details |
|---|---|
| Prospect Research Brief | Priorities, pain points, trigger events, communication style, best hook |
| ICP Alignment Score | High/Medium/Low match with reasoning (if ICP provided) |
| 3 Subject Line Variants | Trigger hook, pain hook, curiosity hook — with A/B test recommendation |
| 4-Email Sequence | Day 0, Day 3, Day 7, Day 14 — each adds new value |
| Tone Calibration | Auto-adapts to Direct, Consultative, Casual, Executive, or Challenger |
| Strategy Notes | Why these angles, objections addressed, narrative arc explained |

## Example Output (Excerpt)

**Input:** VP of Finance at a logistics company, 450 employees, using QuickBooks, hiring AP staff. Selling AP automation.

**Research Brief finds:** Growth from 280→450 employees in 18 months, actively hiring AP coordinator, processing 2,000+ invoices/month on manual spreadsheets — classic automation-ready signal.

**Subject Line Variants:**
```
A — meridian's ap team is growing again (trigger hook)
B — 2,000 invoices and spreadsheet matching (pain hook)
C — 14 days to 4 on invoice processing (result hook)
```

**Email 1 (74 words):**
```
David, noticed Meridian posted for an AP Coordinator last week — and
you're looking to bring on another AP specialist. That's two hires to
handle what a 3PL your size typically processes: 2,000+ invoices monthly.

A logistics company with similar volume automated their matching and
cut processing from 14 days to 4 — without adding headcount.

Would 20 minutes to see how they did it be useful?

Alex
```

*Plus 3 more follow-ups, each with a unique angle (ROI math → implementation speed → discount capture revenue).*

## What Makes This Pro

| Feature | Basic Email Writer | Cold Email Personalizer Pro |
|---|---|---|
| Research | None | Full prospect analysis before writing |
| Emails per run | 1 | 4-email sequence (always) |
| Subject lines | 1 | 3 variants for A/B testing |
| ICP awareness | None | Scores prospect fit, calibrates language |
| Tone options | One size fits all | 5 profiles (Direct/Consultative/Casual/Executive/Challenger) |
| Word discipline | No limits | 50-90 words enforced, 15+ banned phrases |
| Follow-up strategy | "Just following up" | Each email adds new value with unique angle |
| Quality control | None | Built-in compliance checklist |

## Pricing

| Format | Price |
|---|---|
| Universal (any AI) | $79 |
| Claude Code Native | $119 |
| Complete Bundle | $149 |

## Version History

See [CHANGELOG.md](./CHANGELOG.md) for version history.
