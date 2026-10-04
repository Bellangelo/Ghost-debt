# Ghost debt

How leftover decisions keep running after the person is gone.

We had a conversation with an old colleague. At some point they told him that we keep doing things because "he" (the one who left) said so. One of them jokingly said, "your ghost is taking decisions." We all laughed.

I loved this metaphor. I searched immediately whether this had been said before, or whether there were relevant concepts. I found a few things. Nothing sat on the exact line of that joke.

My thoughts took two paths.

One path said: if being a ghost means you had influence in the company, then figuring out how someone becomes a ghost should help you in your career. You would have the steps for gaining influence that lasts after you leave the room.

The other path said: if we accept that ghosts exist, and ghosts take decisions, and each decision leaves something behind, then ghosts leave something behind. I call it ghost debt.

I still think both paths are useful. They also turned out to be the same job.

Staff work is encoding judgment so the organisation does not need you in the room. That encoding is the influence. Ghost debt is what happens when the encoding still votes and nobody left can recast it.

## Absence as a reason

The closest named idea is "organizational ghosts." In 2023, Jeffrey Bednar and Jacob Brown published [a paper with that title](https://doi.org/10.5465/amj.2022.0622). Former members become the picture of "who we are." People ask what they would have done.

That is close. Our joke was smaller.

Nobody in that conversation was asking what he would have wanted as our identity. They were using him as a reason. We do this because he said so. The ghost was not inspiring anyone. The ghost was occupying a chair.

> A ghost is not someone people remember. A ghost is someone whose absence is still treated as a reason.

There are two kinds.

- Identity ghost: "What would they have done?"
- Decision ghost: "We do this because they said so."

The first still has a question in it. The second is a closed vote. Architecture lives in the second.

## You already encode, or the system forgets you

Influence that lasts does not start at the goodbye lunch. It starts on the day people stop arguing with the idea and start invoking you. Then it only lasts if you put it somewhere other than your head.

You make a judgment others cannot easily reverse. A boundary. A hiring bar. A "we never do that." You encode it in language other people reuse. In defaults, interfaces, checklists, CI, taboos. Then you leave the room. A meeting, a team, a company. The encoding keeps voting.

Four things survive a person particularly well:

- Stories: "X would hate this."
- Practices: the review that still happens on Friday.
- Defaults: the template, the named meeting, the lint rule.
- Forbidden moves: the thing nobody tries because somebody once forbade it.

If people need to remember you for the thing to continue, it is fragile. If it is built into how work moves, it continues.

There is a tell that you are already a ghost on the payroll. People say your name instead of the why. It feels like respect. Sometimes it is. It is also the moment the decision starts to travel without you, which means it can stop being yours to change.

Wanting that is not a career hack. It is the job. Wanting it without a living why is how you occupy chairs you will never sit in again.

## Un-owned inheritance

[Technical debt](https://c2.com/doc/oopsla92.html) is a shortcut you took. You borrowed time, and you pay interest later. [Organizational debt](https://steveblank.com/2015/05/19/organizational-debt-is-like-technical-debt-but-worse/), as Steve Blank used it, is the people and culture compromise made to "just get it done." Process debt is a workflow that helped once and now slows things down. [Chesterton's fence](https://www.gkc.org.uk/gkc/books/The_Thing.html) is the pause: do not remove a rule until you know why it was put there.

Ghost debt sits next to these. It is a different object. It is the cost of a decision that kept operating after it lost its owner. The rule stayed. The context left with the person. The people who remain keep paying, because they cannot renegotiate with the author.

Chesterton's fence says the fence may have a good reason. Ghost debt is what happens when that may still be true, and nobody left can explain the fence, own it, or retire it. Inheritance is normal. Un-owned inheritance is expensive.

The interest is boring, which is why it hides. Extra process that no longer matches the constraint it was built for. Extra fear of touching a thing with someone's name on it. Extra meetings to decode a choice. Extra inability to change, because changing it feels like disloyalty rather than work.

I keep seeing it in four forms.

**Orphaned why.** "We always do it this way." The checklist survived. The original reason did not. Maybe the vendor is gone. Maybe the scale is different. Maybe the risk that created the rule is gone.

**Cited authority.** "He said so." A name ends the discussion. The name is doing the work a reason should do.

**Fossil process.** "We still have this meeting." A weekly call, a two-stage approval, a branching strategy. It made sense in their constraints: their team size, their incident, their regulator. The world moved. The process did not.

**Taboo without a priest.** "We don't do that here." Nobody ships on Fridays. Nobody talks to that customer. Nobody rewrites that service. The priest is gone. The taboo remains. You cannot test it without feeling like you are vandalizing something.

A person who left can leave a constraint that still saves you. Ghost debt is not an argument for deleting history. It is an argument for noticing when history is still voting, and whether anyone present can recast that vote.

## It looks the same in the codebase

After this method you need to call this method, and nothing in the type system says so. The comment says "always." The tests only pass if you know the order. The person who knew why has left. The compiler did not get the memo.

You already know the rest of the list.

A public `init()` after construction, because the object is a lie until a second call. A feature flag that has to stay off, or on, and nobody will own turning it the other way. A module everyone is told not to touch. A pairing of save and reindex that eight call sites remember and the ninth does not. An ADR with a name in it and no current owner. Tests that fail if you use the "official" API and pass if you use the back door.

Those are requirements the type system does not know. They are still deciding.

## Decide. Encode. Leave.

This is the part I did not see when we were still only laughing.

You decide. You encode it. You leave the room. The encoding keeps voting.

If the encoding still has a living owner and a living why, I would call that legacy. If it only has a name, it is ghost debt.

The way to leave useful influence is not to make yourself harder to remove. It is to make the decision easier to re-own.

Leave reasons, not only decisions. Leave owners, not only artifacts. Leave the conditions under which you would reverse the call, not only the default.

A decision that cannot be re-opened is not a strong decision. It is a decision that has lost the person who could still argue with it.

## Questions for the living

One pass over the decisions that still have a person in them is enough.

If you are about to encode something: would this still make sense if nobody could ask me? Did I write down the why, and when I would reverse it? Who owns this after I leave the room, not after I leave the company?

If you already live with someone else's encoding: whose name still ends debates? Which rules have a name and no owner? What would we have to know to retire this, and do we still know it?

Then pick one.

Keep it, because the fence is still doing work, and now it has an owner. Encode the contract into the work, because the constraint is real and a comment is not a type. Retire it, because the constraint left with the person.

I call that pass an exorcism. An exorcism here is naming a ghost, not casting it out. You collect candidates. A living person answers whether each one is ghost debt, leftover on purpose, or something that needs a why.

- Is this still required? If yes, what is the why, and who owns it now?
- If we stopped doing the ritual, what would break?
- Keep, encode the contract, or retire it?
- If this is not ghost debt, what is it?

A room can run that pass with [9 Whys](https://www.liberatingstructures.com/nine-whys) until you hit a living reason or silence, then [Min Specs](https://www.liberatingstructures.com/min-specs) to strip folklore from the constraint that still has to stay. An agent can hunt the codebase for candidates. It should stop at the questions. The living still decide.

That pass is a bit rude. It replaces loyalty to a name with loyalty to a reason. Most leftover decisions can survive that. The ones that cannot were already debt.

We laughed because it was funny. It was accurate because the chair was still occupied. If you mattered, you will leave a ghost. The useful question, for me, is whether the people after you inherit a reason, or only a name.

## References

- Jeffrey S. Bednar and Jacob A. Brown, ["Organizational Ghosts: How 'Ghostly Encounters' Enable Former Leaders to Influence Current Organizational Members,"](https://doi.org/10.5465/amj.2022.0622) *Academy of Management Journal* 67, no. 3 (June 2024). Published online 30 November 2023. DOI: [10.5465/amj.2022.0622](https://doi.org/10.5465/amj.2022.0622).
- Ward Cunningham, ["The WyCash Portfolio Management System,"](https://c2.com/doc/oopsla92.html) OOPSLA experience report, 1992. The source of the technical debt metaphor.
- Steve Blank, ["Organizational Debt is like Technical debt – but worse,"](https://steveblank.com/2015/05/19/organizational-debt-is-like-technical-debt-but-worse/) 19 May 2015.
- G. K. Chesterton, *The Thing* (London: Sheed & Ward, 1929), chapter ["The Drift from Domesticity."](https://www.gkc.org.uk/gkc/books/The_Thing.html)
- Henri Lipmanowicz and Keith McCandless, [9 Whys](https://www.liberatingstructures.com/nine-whys) and [Min Specs](https://www.liberatingstructures.com/min-specs), Liberating Structures. See also *The Surprising Power of Liberating Structures* (Liberating Structures Press, 2014).
