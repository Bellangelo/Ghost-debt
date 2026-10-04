# Example findings

These are shapes, not real files. Match the report format in SKILL.md.

## Temporal coupling

Code:

```text
user.save()
user.syncPermissions()  # every other call site does this; the type does not require it
```

Candidate: after `save` you need `syncPermissions`. Confidence high if 8 of 9 call sites pair them and one bug report matches the ninth.

Question for the living: If we save without `syncPermissions`, what breaks? Should `save` do this itself, or is the split still required?

## Cited authority

```text
# Do not remove this sleep. Maria said the payment provider needs it.
time.sleep(2)
```

Candidate: the sleep is a decision whose owner may have left. Confidence medium until someone says the provider still needs it.

Question for the living: Is Maria's constraint still true? Who owns this timeout now?

## Not ghost debt

```text
# Retry up to 3 times; Stripe webhooks can duplicate (see docs/payments.md, owned by billing).
```

Has a why and a living owner. Skip, or mention only as a contrast.

## Living ADR (not ghost debt)

```text
# ADR 00013: Cross-database operations go through DomainIterator.
# See docs/engineering/database-access.md (owned by platform).
```

A why, a current doc, no departed name as the spec. Skip.

## Ownerless ADR

```text
# ADR 0014: Never call BillingService from Checkout.
# Alice, 2019. Do not revisit.
```

Candidate: the boundary may still be right. The spec is a name and a date. Confidence medium until someone current owns the constraint.

Question for the living: Is this still required? Who owns this boundary now? Keep it in a current ADR, encode it in the module graph, or retire it?

## Tests as the only spec

A test asserts that `close()` after `open()` without `flush()` loses writes. Production `close()` does not flush. The test is the priest.

Question for the living: Should `close` flush, or must callers keep calling `flush` first?
