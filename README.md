# Ghost debt

How influence outlives you, and the debt it leaves behind.

Ghost debt is a decision that still operates after it lost its owner.

In a company it sounds like "we do this because he said so." In code it looks the same: after this method you need to call this method, and nothing in the type system says so. The rule stayed. The why left with the person.

The essay is [here](https://github.com/Bellangelo/ghost-debt/blob/main/article.md).

## Exorcism

The skill is called **exorcism**. It names the ghost. It does not cast it out.

Copy [`.agents/skills/exorcism/`](https://github.com/Bellangelo/ghost-debt/tree/main/.agents/skills/exorcism) into a project, or open [this repo](https://github.com/Bellangelo/ghost-debt) in an agent that loads `.agents/skills`. Ask for an exorcism on a path, a PR, or the whole tree.

It should return candidates, not a verdict: keep with a why and an owner, encode the contract, retire it, or say we need more context. It ends with **Questions for the living**. Do not delete code until a living person answers.
