# Wording reply

Reply in the language of the work-item text. Check names stay in English. Verdict tokens are `READY` and `NOT READY`.

Russian labels:

- Start: Можно брать в работу
- Done: Понятно, когда сделано
- Field: Пункт
- Closing: Постановка, при которой оба вердикта READY

English labels:

- Start: Ready to start
- Done: Clear when done
- Field: Check
- Closing: Wording that makes both verdicts READY

A missing product fact is a blank in square brackets. The blank names the hole. A quote is copied from the text. One failed check, one quote. A check that passes does not appear. The number of bullets equals the number of failed checks. A NOT READY verdict with no bullet for that verdict is wrong.

## Both READY

The reply is these two lines:

```text
<Start label>: READY
<Done label>: READY
```

## A failed check

```text
<Start label>: READY | NOT READY
<Done label>: READY | NOT READY

- "<quote from the text>"
  <Field>: <check name>
  <one sentence: words from the text, or a blank in square brackets>

<Closing>:
<paragraph with a square-bracket blank for each fact the text does not contain>
```

When the reply is Russian, wrap the quote in «».
