---
name: bug-wording
description: Checks Start and Done on wording for behavior that is already wrong. Use when the text reports broken behavior.
---

# Bug wording

Read `../task-quality/OUTPUT.md` and reply in that shape. Done when every failed check has a quote from the text, or both verdicts are READY and the reply is the two lines.

Score the text already in the conversation. A missing fact is a blank in square brackets. The tracker record stays as it is.

## Start

Start is READY when all of these hold:

- **Steps.** The text states the actions that show the failure.
- **Expected.** The text states the behavior that should have happened.
- **Actual.** The text states the behavior that did happen.
- **Environment.** The text states where it happened.
- **Logs.** The text includes a log line, an error string, or the words that there is no log. A pointer to a screenshot or an attachment is READY only alongside that text.
- **Single.** The text reports one failure. When it reports two, Start is NOT READY and the closing block is two separate wordings, one failure in each.

## Done

Done is READY when **Testable** holds for Expected: a test can assert that expectation. "Should work" and "Должно работать" are not that assertion. The broken behavior is the edge; Expected is the visible outcome of the fix.

The checks are exactly Steps, Expected, Actual, Environment, Logs, Single, and Testable.
