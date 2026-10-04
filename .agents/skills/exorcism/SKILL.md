---
name: exorcism
description: >
  Runs an exorcism on a codebase: finds candidate ghost debt such as
  undocumented call order, implicit init protocols, "always/never" comments,
  unpaired methods, and fossil flags. Use when the user asks for an exorcism,
  ghost debt, implicit coupling, leftover constraints, rituals in code, or an
  audit of patterns a departed author may still be enforcing. Names candidates
  only. Ends every report with "Questions for the living". Does not delete or
  "fix" code until a living person answers. Do not treat ordinary technical
  debt as ghost debt.
---

# Exorcism

An exorcism here is naming a ghost, not casting it out. Ghost debt is a decision that still operates after it lost its owner. In code it is a requirement the type system does not know. Example: after this method you need to call this method, and nothing in the compiler says so.

You do not declare ghost debt and you do not banish it. You collect **candidates**. A living person answers whether each one is ghost debt, leftover on purpose, or something that needs a why.

Read [patterns.md](patterns.md) for the hunt list. Read [examples.md](examples.md) if a finding is ambiguous.

## Scope

If the user names a path, PR, or diff, stay there. Otherwise start at the repo root and skip vendor, generated code, lockfiles, and dependency directories.

Do not change code unless the user asks after answering the questions.

## Hunt

Comments that say always / never / must / don't, or that name a person, are the easy radar. Use them. They are not the whole hunt. The original example is call order with no English at all.

1. **Call order.** Method A is almost always followed by method B at call sites, with no type, assertion, or wrapper that forces the pair. Do not wait for a comment. Bound the hunt: one path, one PR, or a handful of hot methods (`save`, `persist`, `open`, `init`, `close`, `flush`, `commit`), not every `save` in a large tree. Sample those call sites. If most sites pair A with B and one does not, that pair is a candidate. Public `init()` after construction is the same shape. Paired side effects (save without reindex, open without close, start without stop) are this item, not a second hunt.
2. **Init and teardown protocols.** Objects that are unsafe until a second call (`init`, `setup`, `bind`, `load`, `commit`, `flush`, `close`).
3. **Always / never / must / don't comments.** Especially comments that name a person, a ticket, or "don't remove this."
4. **Tests as the only spec.** Tests that encode order or hidden invariants the production API does not.
5. **Fossil branches.** Feature flags, env vars, or dead config that still have to be set a certain way.
6. **Copy-paste setup.** The same three lines before every use of a type, never extracted, never documented as a contract.
7. **Ownerless decision records.** Only when the record still binds the tree *and* the spec is a person, a stale "do not revisit," or no current owner. A living ADR, RFC, or engineering guide that says "must not" with a why and no departed name is owned. Skip it.

If a first pass only found English comments, say that under Scope. Temporal coupling is then undercounted. Do not pad the report with living docs to look complete.

For each candidate, record evidence: file, symbol, call sites or comments, and what is missing (type, wrapper, assertion, written why, named owner).

Skip: ordinary complexity, named design patterns that are still owned, TODOs with a current owner, shortcuts that are technical debt with a known author still around, and current architecture docs. Ghost debt is **unowned inheritance**, not "this is messy," and not "this document is strict."

If git history is available and cheap, a last-touch author who has left is supporting evidence, not proof. Do not invent who left.

## Report

Use this shape. Keep findings as candidates.

```markdown
# Exorcism

## Scope
[paths or diff examined]
[If the hunt only found English comments, say temporal coupling is undercounted.]

## Candidates

### C1. [short name]
- Type: temporal coupling | orphaned why | cited authority | fossil process | taboo
- Where: `path` `symbol`
- What the code still requires: [the ritual]
- Why it looks unowned: [no living owner / no living why / comment is the only spec / a name in a comment]
- Evidence: [call sites or quotes]
- Confidence: low | medium | high

## Questions for the living
```

The last heading must be exactly `## Questions for the living`. Do not rename it, skip it, or put anything after it except the questions.

Each question maps to one candidate, is answerable by a person who still works here, and offers a way to classify it:

- Is this still required? If yes, what is the why, and who owns it now?
- If we stopped doing the ritual, what would break?
- Keep (write the why and an owner), rewrite the contract into code, or retire it?
- If this is not ghost debt, what is it?

Ask for clarification when you cannot tell. A living person may answer "need more context" rather than yes or no.

End the questions section with this line, verbatim:

A living person should answer whether these are ghost debts or we need clarifications about potential ghost debts.
