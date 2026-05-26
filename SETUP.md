# JB Automations Client Setup

Use this checklist before and during a client's AI Workflow Setup Session.

## 1. Create The Client Folder

Create a client-specific folder on the client's computer.

Example:

```bash
mkdir -p ~/Documents/AIOS
cd ~/Documents/AIOS
```

Clone this template into a business-specific folder:

```bash
git clone https://github.com/Jbercegeay/ai-operating-system-template.git fort-payne-dental-aios
cd fort-payne-dental-aios
```

## 2. Open The Folder

Open the folder in the tool being used for the setup:

- Claude Code
- Codex
- both, if the client may use either

## 3. Run Onboarding

Run:

```text
$onboard
```

or:

```text
/onboard
```

The onboard skill should start with JB Automations preflight:

1. Operator mode: Claude Code, Codex, or both
2. Client/business name
3. Primary operator name
4. Primary operator role

Then it runs the 7 client onboarding questions.

## 4. Keep The First Setup Small

The first setup is a single-operator AIOS.

It should produce:

- filled `aios-intake.md`
- `context/about-operator.md`
- `context/about-business.md`
- `context/priorities.md`
- `references/voice.md`
- populated `connections.md`
- filled `CLAUDE.md` and/or `AGENTS.md`
- a first workflow or automation recommendation

It should not promise:

- a finished automation
- a team rollout
- a shared repo
- connected APIs
- credentials or `.env` setup

## 5. Close The Session

End by summarizing:

- what was set up
- what the AIOS now knows
- what is missing
- the first workflow opportunity
- the recommended next paid step

If the client wants team access later, use:

```text
references/sops/shared-business-aios-expansion.md
```
