---
name: change-wording
description: Checks Start and Done on wording for a behavior the product does not have yet. Use when the text asks for new behavior.
---

# Change wording

Read `../task-quality/OUTPUT.md` and reply in that shape. Done when every failed check has a quote from the text, or both verdicts are READY and the reply is the two lines.

Score the text already in the conversation. A missing fact is a blank in square brackets. The tracker record stays as it is.

## Start

Start is READY when all three hold:

- **Outcome.** The text names who the outcome is for and why they need it. Who is written in the text: a person, or a named system such as a service, a probe, or an incident. An implied reader does not count.
- **Dependency.** The text names the other work this waits on, or says this work waits on nothing.
- **Size.** The text presents one outcome as one piece of work for one sprint. Steps of that one outcome are still one outcome. Size fails when the text promises more than one distinct outcome.

## Done

Done is READY when both hold:

- **Observable.** Somewhere in the text is an externally visible fact of this work. A fact that stays true when the work is not done does not count. A stated change of a named object — add X to Y, remove X from Y — names the visible fact: X is, or is no longer, visible in Y.
- **Testable.** The text contains at least one criterion, wherever it sits, and each criterion is one assertion a test can make. An empty word counts only beside an observable fact: fast, convenient, correct, works, быстро, удобно, правильно, корректно, работает. One sentence carries one outcome. Steps inside one criterion are not several outcomes. When the text names an edge, it says what is visible on that edge.

The checks are exactly Outcome, Dependency, Size, Observable, and Testable.
