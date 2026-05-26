---
name: onboard
description: Use during a JB Automations AI Workflow Setup Session or Day 1 of a client AIOS install. Runs JB preflight, conducts the 7-question client intake, and scaffolds the Day-1 file set. Idempotent — re-run any time after editing aios-intake.md.
---

## What this skill does

Single combined wizard for a JB Automations client AIOS.

It reads or writes `aios-intake.md`, runs a short JB Automations preflight if missing, conducts the 7-question client interview if needed, then scaffolds the Day-1 file set inline at the end of the run.

This template starts as a **single-operator AIOS**. Team/shared use is a later expansion documented in `references/sops/shared-business-aios-expansion.md`.

## Execution

### Step 1: Read the intake

Read `aios-intake.md`.

Check:

- JB Automations Preflight fields
- Q1-Q7 sections

If preflight is blank, ask the preflight questions before Q1-Q7.

If Q1-Q7 are all filled, skip the interview and jump to scaffold.

If some Q1-Q7 answers are filled, ask: "I see some intake answers are already filled. Want to fill the rest now, or scaffold from what's there?"

### Step 2: JB Automations Preflight

These questions are operator setup, not part of the 7-question client intake.

Ask one at a time and write each answer into `aios-intake.md`.

**P1 — Operator mode**

Ask:

> "Which operator mode should this client AIOS use: Claude Code, Codex, or both?"

Default recommendation: both.

Meaning:

- Claude Code: `CLAUDE.md` and `.claude/skills/`
- Codex: `AGENTS.md` and `.agents/skills/`
- Both: keep both manuals and both skill folders aligned

**P2 — Client/business name**

Ask:

> "What is the client or business name?"

Use this as the title label in `CLAUDE.md`, `AGENTS.md`, and generated context files.

**P3 — Primary operator name**

Ask:

> "Who is the primary operator using this AIOS?"

This is the person sitting at the computer for the first setup.

**P4 — Primary operator role**

Ask:

> "What is that person's role in the business?"

Examples: owner, office manager, operations manager, sales lead.

### Step 3: The client interview (7 questions, hard cap)

Ask one at a time. Write each answer into `aios-intake.md` as you go.

**Q1 — What is this business, what does it sell, and who does it serve?**

Business identity, offer, ideal customer.

**Q2 — Paste 1-2 things the operator or business has written recently. Don't edit them.**

Voice samples MUST be pasted, not typed fresh during the conversation.

If they start composing fresh prose, refuse:

> "Stop — paste it raw. If you type it here while we're talking, the sample is already shaped by our conversation. Open a recent email, post, proposal, or message and paste the unedited text. This is the one rule I can't bend."

Ask for two samples. One is acceptable if that is all they have.

**Q3 — What are the 2-3 biggest priorities for the next 90 days?**

Push for a number, deadline, or deliverable.

**Q4 — Where does revenue actually land, and where is it tracked?**

Map to Domain 1: Revenue / Financials.

**Q5 — Where does the business talk to customers, the team, and the outside world day-to-day?**

Map to Domains 2 + 4. Infer calendar from email provider.

**Q6 — Where do meeting recordings, notes, SOPs, and important docs live?**

Map to Domains 6 + 7.

**Q7 — What's the one task that eats the week, and where is work currently tracked?**

Capture top pain and Domain 5: Project / task tracking.

### Step 4: Scaffold the Day-1 file set

Once the intake is complete, generate or update these files. Back up originals to `archives/intake-{YYYY-MM-DD-HHMM}/` if any exist.

1. `context/about-operator.md` — from preflight primary operator + Q7 top pain. One short paragraph each.
2. `context/about-business.md` — from Q1 + Q4. One paragraph.
3. `context/priorities.md` — from Q3. Numbered list.
4. `references/voice.md` — from Q2. Paste samples verbatim with a short usage note.
5. `connections.md` — populate the 7-row table from Q4-Q7. Mechanism: `not yet connected`, auth: `—`, last checked: `—`.
6. `CLAUDE.md` — fill placeholders if operator mode is Claude Code or both.
7. `AGENTS.md` — fill placeholders if operator mode is Codex or both.
8. `decisions/log.md` — append a Day-1 setup decision.

Do not ask for API keys. Do not write `.env` files.

### Step 5: Closing screen

Print one short screen:

```
✓ Day 1 done. This single-operator AIOS knows the business, the primary operator, what matters this quarter, and how the business sounds.

Next: ask me — "what should we focus on this week?"
Later: if the team needs access, use references/sops/shared-business-aios-expansion.md.
Day 7: run $audit or /audit to see the Four-Cs score.
```

## Critical implementation rules

1. The client interview is capped at 7 questions.
2. Preflight is setup metadata and does not count against the 7 client questions.
3. Voice paste cannot be skipped.
4. One-shot scaffold after the interview ends.
5. Idempotent: re-running with edited intake refreshes context files and backs up originals.
6. Read-only on `references/3ms-framework.md`.
7. Preserve Nate Herk attribution in generated manuals.
8. Default setup is single-operator. Do not imply team access exists until shared repo expansion is completed.
