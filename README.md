# Task quality

Spelling out the work does not make the wording ready. The text never says who it is for, two outcomes share the story, and one sentence holds three assertions.

These three skills score that wording. They reply with a verdict and a rewrite, and they leave the tracker alone. Paste the text, or point at a body the chat already has. GitHub, GitLab, Jira, and a local file all work the same way, because the skills never call the tracker.

## Install

On this machine, for every project:

```bash
npx skills add redb0/skills -g
```

The installer asks which agents to use. Pass `-a` when you already know. Drop `-g` to commit the skills inside one repo. The installer looks in `skills/`.

To pick up later edits, run `npx skills update -g`.

## Run

Type `/task-quality` and put the wording in the same message.

New behavior goes to `change-wording`. Something already broken goes to `bug-wording`. Both in one text, or neither, and it asks once and does not score.

Call `/change-wording` or `/bug-wording` yourself when you already know which it is.

A login method and a CLI that creates the account are two stories. Score them apart.

## Reference

User-invoked skills run when you type them. Model-invoked skills can be typed too, and another skill can open them.

### User-invoked

- **[task-quality](./skills/task-quality/SKILL.md)**: routes the wording. The reply shape is [OUTPUT.md](./skills/task-quality/OUTPUT.md).

### Model-invoked

- **[change-wording](./skills/change-wording/SKILL.md)**: Start checks Outcome, Dependency, and Size. Done checks Observable and Testable.
- **[bug-wording](./skills/bug-wording/SKILL.md)**: Start checks Steps, Expected, Actual, Environment, Logs, and Single. Done checks that Expected is Testable.

## Example

The body is a "What to build" story. It asks for new behavior and never says anything is broken, so `change-wording` scored it.

```text
Ready to start: NOT READY
Clear when done: NOT READY

- "gRPC method `Auth.Login(login, password)`: returns an access token (JWT ES256, TTL 15 minutes) and a refresh token (opaque, TTL 24 hours)"
  Check: Outcome
  The text says what to build. It never says who it's for, or why they need it.

- "What to build:"
  Check: Dependency
  No other work is named, and the text never says this waits on nothing.

- "CLI `add-user` creates an account"
  Check: Size
  Two outcomes share the story: the gRPC method `Auth.Login`, and the CLI command `add-user`. One story delivers one of them.

- "The access token is a JWT using ES256, signed with the private key, TTL 15 minutes"
  Check: Testable
  One sentence asserts the algorithm, the private-key signature, and the 15-minute TTL. One sentence carries one assertion.

Wording that makes both verdicts READY:
[Who] needs this so that [why]. This waits on [other work], or it waits on nothing. This story delivers one outcome, either `Auth.Login` or `add-user`. The access token is a JWT using ES256, signed with the private key. It expires after 15 minutes.
```
