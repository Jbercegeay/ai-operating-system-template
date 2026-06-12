# JB Automations AI Operating System Template

This is the private JB Automations client AIOS template.

Use it to set up a client's first AI Operating System during an **AI Workflow Setup Session**.

This repo is not Johnny's personal AIOS. It is not a public product page. It is the reusable starting point JB Automations clones for a client.

---

## The Offer This Supports

**Public offer:** AI Workflow Setup Session
**Internal name:** AIOS Setup Session
**Default scope:** single-operator AIOS setup

The first session sets up the foundation:

- Clone or set up this AIOS for one primary operator.
- Choose the operator mode: Claude Code, Codex, or both.
- Capture the client's business context, priorities, tools, voice, and pain points.
- Build the Day-1 AIOS files.
- Identify the first workflow or automation opportunity.

The first session does **not** promise a finished automation, a fully mapped complex workflow, or a team rollout.

---

## Standard Client Setup Flow

1. Create a client folder on the client's computer.
2. Clone this template into that folder.
3. Open the cloned folder in Claude Code or Codex.
4. Run `$onboard` or `/onboard`.
5. Complete the JB Automations preflight:
   - operator mode: Claude Code, Codex, or both
   - client/business name
   - primary operator name
   - primary operator role
6. Run the 7-question client onboarding interview.
7. Review the generated context, connections, voice, and operating manual files.
8. End with the recommended next step.

Default setup type: **single operator**.

If the client later needs team access, follow `references/sops/shared-business-aios-expansion.md`.

---

## Operator Modes

### Claude Code

Use when the client AIOS will be operated primarily in Claude Code.

- Primary operating manual: `CLAUDE.md`
- Skills folder: `.claude/skills/`

### Codex

Use when the client AIOS will be operated primarily in Codex.

- Primary operating manual: `AGENTS.md`
- Skills folder: `.agents/skills/`

### Both

Recommended default for JB Automations.

- Keep `CLAUDE.md` and `AGENTS.md` aligned.
- Keep `.claude/skills/` and `.agents/skills/` aligned.
- This makes the client AIOS portable between Claude Code and Codex.

---

## What Gets Customized Per Client

- Client/business name
- Primary operator name and role
- Business context
- 90-day priorities
- Voice samples
- Revenue and financial systems
- Customer communication systems
- Calendar, docs, notes, and task systems
- Biggest recurring manual task
- First workflow or automation opportunity

Do not put secrets, API keys, private credentials, or raw exports into the template.

---

## Repo Layout

```
ai-operating-system-template/
├── README.md
├── SETUP.md
├── CLAUDE.md
├── AGENTS.md
├── EXPANSIONS.md
├── LICENSE
├── .gitignore
├── aios-intake.md
├── connections.md
├── context/
├── references/
│   ├── 3ms-framework.md
│   └── sops/
│       └── shared-business-aios-expansion.md
├── decisions/
├── archives/
├── .claude/skills/
└── .agents/skills/
```

---

## Important Boundaries

Start with one operator. Do not overbuild the first setup.

The first setup lives on one computer and gives the business a working foundation. If the client wants multiple people using the AIOS later, convert it into a shared business repo and add operator profiles as a separate paid next step.
