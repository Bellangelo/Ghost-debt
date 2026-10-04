# Ghost debt patterns in code

Use this list while hunting. Each item is a candidate until a living person answers.

## Temporal coupling (the original example)

After this method you need to call this method. Nothing in the signature says so.

Signs:

- `start` / `finish`, `begin` / `commit`, `open` / `close`, `lock` / `unlock`
- `save()` then a separate `reindex()` / `notify()` / `touch()` at most call sites
- Open without close, start without stop, set flag A without flag B
- Builder or entity that explodes unless `build()` / `hydrate()` / `validate()` ran
- Public `init()` after construction
- Docs or comments: "always call X after Y", "must be called before", "don't forget"

Stronger candidate when some call sites omit the second call and tests or production only work by accident.

Grep for "always call" will miss most of these. Hunt from the method, not from the comment: bound the search to a path, a PR, or a handful of methods, list those call sites, read the next few lines, and count how often a second call appears.

## Orphaned why

A constraint remains. The original reason is gone or never written down.

Signs:

- Magic numbers, sleeps, retries, timeouts with no comment or a stale one
- `if (legacy)` / `compat` / `old` branches that every path still hits
- Columns, fields, or args that must be set together with no struct wrapping them
- Error swallowing with no recorded invariant

## Cited authority

A person or ticket is the spec.

Signs:

- Comments: "Alice said", "per Bob", "don't change this, [name] will be angry"
- Commit messages used as the only explanation and the author is gone
- "As discussed" with no link to a current owner
- ADRs or RFCs that still constrain the design and name a writer who has left, with no current owner

A ticket ID with a living owner is not ghost debt. A name in a comment with no current owner is.

A current ADR or RFC with a why, still maintained, and no departed name is not ghost debt. "Must not" in a living engineering guide is a contract until a living person says otherwise.

## Fossil process

A workflow that matched someone else's constraints.

Signs:

- Makefile / CI steps nobody can explain
- Required env vars missing from README
- Generate-then-hand-edit files
- Two ways to do the same thing, both still required
- Feature flags that cannot be removed because unknown callers exist

## Taboo

A forbidden move with no living priest.

Signs:

- "Never use X", "don't touch this file", "do not call this from Y"
- Deprecated APIs that are still the real API
- Tests that fail if you use the "official" method and pass if you use the back door

## What this is not

- Technical debt with an owner ("we know this is a shortcut, ticket in the backlog")
- An encoded contract (type, mutex, destructor, transaction, linter, assertion)
- Complexity that is still argued about in review
- Style disagreements
- Living architecture docs and decision records that still have a why and no leftover person as the spec
