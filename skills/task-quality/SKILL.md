---
name: task-quality
description: Routes work-item wording to the change or bug check.
disable-model-invocation: true
---

# Task quality

The wording under review is already in the conversation. When steps, expected behavior, actual behavior, or environment live in their own fields, those values are part of the wording. When that body is not in reach, ask for the text and stop.

`change-wording` and `bug-wording` are model-invoked so this skill can run the matching one. This skill is user-invoked so one name is enough to remember.

## Route

Ask one question and stop, with no verdict, when the text shows both broken behavior and new behavior, shows neither, or the kind is not visible. Ask which it is: new behavior, or behavior that is already wrong.

When the text only asks for new behavior, read and follow `../change-wording/SKILL.md`.

When the text only reports behavior that is already wrong, read and follow `../bug-wording/SKILL.md`.

The reply is that skill's verdict. The tracker record stays as it is.

Done when one of those skills has replied, or the one question is asked and no score is given.
