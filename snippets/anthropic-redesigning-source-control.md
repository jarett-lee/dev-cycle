# Redesigning source control at Anthropic

- **Source:** https://www.anthropic.com/research/redesigning-source-control
- **Author:** Nick G. and the Anthropic source control team
- **Published:** 2026-10-13 (updated 2026-10-15)
- **Supports:** the engineer's role, code review, YAGNI, be consistent, DRY

Anthropic moved its monorepo off git onto an in-house system, Scion, in five
months with a team of seven. The "What we learned" section describes how
working with Claude changed the engineers' role.

## Snippets

**The engineer's role**

> Engineers are no less valuable, but their work is changing. All of the engineers who worked on this system would now rate Claude as better at writing code than them. But our engineers still supplied the invaluable understanding of the high-level inter-system components and the design-level tradeoffs, making informed choices around the problems we wanted to solve and the scale we knew we needed to achieve. Very often, we found that the role of the engineers was to tell Claude “no.” Agents will sometimes violate core system constraints to satisfy a pattern that should never have been allowed in the first place. This was particularly common in our migration. For example, there were multiple systems that tried to brute force looking up when a change merged to main by linearly reading the commit log instead of asking our code review tool. Anthropic also makes extensive use of adversarial review, and, while this is incredibly effective in many ways, it can also be myopic, so skilled engineers needed to steer Claude away from over-engineering parts of the system in response to hypothetical concerns. For example, one such review was overly defensive about trusting another internal service, which resulted in Claude adding excessive validation and complexity. Our team members still review every change request for the system, but they now examine the intent of the change as opposed to reading every line of code.

**Testing is what makes this safe**

> By virtue of Claude’s ability to write immense amounts of code much faster than we could ourselves, Scion is among the most well-tested and well-defended codebases we have ever worked on.

> Even on our tight timeline, we were able to build hermetic simulations of every non-trivial infrastructure and source control interaction we’ve ever encountered, as well as fuzzing and sophisticated rate limiting.

**Rethinking the merge process**

> We haven’t been able to effectively replicate the industry standard of a global repository lock on the merge queue, so instead, we’ve invested in post-merge and pre-deploy automated testing. This does mean that concurrent changes can conflict, but Claude can typically fix these conflicts faster than humans can even identify them.

## Takeaways

- Claude writes the code; the engineer owns the system-level design and
  tradeoffs.
- Saying "no" is core engineering work. Claude will extend a bad pattern if it
  sees one, so the cycle needs a point where a human checks changes against
  system constraints.
- Use the system of record (here, the code review tool) instead of re-deriving
  its data.
- Adversarial review finds real problems but also invents hypothetical ones.
  Its findings need human or explicit judgment before they turn into code.
- Review shifts from reading lines to checking intent. That only works when
  each change states its intent clearly and is backed by heavy automated
  testing.
