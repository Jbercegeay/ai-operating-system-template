# Shared Business AIOS Expansion

Use this workflow when a client who already has a single-operator AIOS wants to add another person or make the AIOS available to the team.

This is a separate paid next step after the initial AI Workflow Setup Session.

## When To Use This

Use this when the client says something like:

- "Can my office manager use this too?"
- "Can my team access the AIOS?"
- "Can this live somewhere shared?"
- "I want another employee set up."

Do not use this during the first $150 setup unless explicitly scoped.

## Goal

Move from:

```text
One folder on one computer
One primary operator
```

to:

```text
One shared business repo
Multiple cloned workspaces
Operator profiles for each user
Shared business context
```

## Expansion Workflow

### 1. Confirm The Shared Source Of Truth

Decide where the shared AIOS repo will live.

Recommended default:

```text
Private GitHub repo owned by the client or managed by JB Automations
```

Record:

- repo owner
- repo name
- who needs access
- who owns billing/security decisions

### 2. Clean The Existing Single-Operator AIOS

Before sharing:

- remove secrets and credentials
- remove personal notes that should not be shared
- review `context/`
- review `references/voice.md`
- review `connections.md`
- confirm no raw exports or private files were dropped into the repo

### 3. Create Operator Profiles

Add:

```text
context/operators/
```

Create one file per operator:

```text
context/operators/jane-office-manager.md
context/operators/owner.md
```

Each profile should include:

- name
- role
- responsibilities
- tools they use
- workflows they own
- decisions they can make
- AI comfort level
- recurring tasks
- voice notes, if they draft customer-facing messages

### 4. Push The Shared Repo

Initialize or connect the repo, then push the clean AIOS.

Recommended branch:

```text
main
```

Do not push with secrets in the remote URL. Use GitHub auth, a credential manager, or a clean HTTPS/SSH remote.

### 5. Add The New Operator

On the new operator's computer:

1. Install or open Claude Code or Codex.
2. Clone the shared repo.
3. Open the repo folder.
4. Confirm they can read the business context.
5. Confirm which operator profile applies to them.

### 6. Define Their First Use Case

Do not give a new operator the whole system at once.

Pick one recurring task:

- customer follow-up
- appointment reminders
- quote drafting
- inbox triage
- SOP lookup
- weekly report prep

Create or update a workflow note under:

```text
references/sops/
```

or, when it becomes repeatable:

```text
skills/
```

### 7. Train The Operator

Show them:

- where the AIOS lives
- what it knows
- what it does not know
- when to ask it
- what not to paste into it
- how to ask for sources from local files
- when to escalate to the owner

### 8. Decide The Next Build

After the new operator has one real use case, decide whether the next step is:

- another operator profile
- a documented SOP
- a custom skill
- a workflow automation
- a lightweight app or portal

## Completion Checklist

- [ ] Shared repo exists.
- [ ] Sensitive files removed.
- [ ] New operator profile created.
- [ ] New operator has repo access.
- [ ] Repo cloned on new operator's computer.
- [ ] First use case chosen.
- [ ] Training completed.
- [ ] Next step documented.

## Positioning Note

The initial setup sells the single-operator foundation. This expansion sells team access and role-specific use.

Plain-English explanation:

> "We set up the first AIOS for one primary operator. Now we are turning it into a shared business AIOS so another person can use the same company context from their own computer."
