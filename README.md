# ghost-debt

Ghost debt is a decision that still operates after it lost its owner.

In a company it sounds like "we do this because he said so." In code it looks the same: after this method you need to call this method, and nothing in the type system says so. The rule stayed. The why left with the person.

The essay is [Ghost debt](article.md).

The skill is called **exorcism**. It names the ghost. It does not cast it out. It ends with **Questions for the living**, so someone who still works here can say "keep it, here is the why," "encode the contract," "retire it," or "we need more context."

## Use the skill

In this repo, or copy `.agents/skills/exorcism/` into another project.

Ask the agent to run an exorcism on a path, a PR, or the whole tree. It should return candidates, not a verdict, and finish with questions a person can answer.
