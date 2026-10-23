# Patterns and problems in multiagent systems

- **Source:** https://www.anthropic.com/research/multiagent-systems
- **Author:** Anthropic Frontier Red Team (corresponding author: Carolyn Zou)
- **Published:** 2026-08-13
- **Supports:** running agents in parallel, telling Claude "no"

Experiments with swarms of agents finding vulnerabilities, building a game
together, and pursuing conflicting goals in the same codebase.

## Snippets

**Building software together**

> Models have poor taste in this arena and currently require significant human direction.

> More recent models (in particular, Opus 4.8 and Mythos Preview) have “solved” this problem, but only by hardly working together at all: the median agent maintained very high ownership of each of its files, reducing the potential for conflict.

**Correlated mistakes**

> And, by implication, this means that when one agent makes a bad decision, it is likely that many agents will make that same bad decision.

**Knowing when to stop**

> But AI agents might interpret directives literally, myopically pursuing them at the expense of broader objectives.

> We want to empower agents to make important decisions and execute tasks unsupervised, yet we also want them to have the better judgment to stop and defer to a human, or otherwise resolve conflicts, when things are ambiguous.

## Takeaways

- Parallel agents avoided conflicts mostly by each owning separate files.
  Clear ownership boundaries matter (related to `TODO.md`).
- Several copies of the same model with the same context are not independent
  reviewers; they tend to make the same mistakes.
- Product taste and direction still came from humans.
- The cycle needs defined points where Claude stops and defers.
