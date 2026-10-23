# Building verification loops in Claude Code with skills

- **Source:** https://claude.com/resources/articles/building-verification-loops-in-claude-code-with-skills
- **Author:** Delba de Oliveira (Claude Code team)
- **Published:** 2026-07-22
- **Supports:** make it work, the dev loop

## Snippets

**The loop**

> Most agentic coding sessions follow a loop: you ask for a change, Claude gathers context, takes action, verifies the results, and if needed, loops back to gather additional context.

> Anything you keep having to enforce by hand as a manual check qualifies for capture as a loop.

**How the Claude Code team chains checks**

> Members of Anthropic's Claude Code team use this pattern in their day-to-day: /code-review hunts for bugs, /simplify cleans up the diff, a /verify skill confirms end-to-end behavior, and a custom /design skill checks against guidelines in a DESIGN.md file if the change touched UI.

> What started as a habit ("I always run /verify after /simplify") becomes a contract ("/simplify always runs /verify when it finishes"). The chain runs the whole dev cycle on its own. You only step in when something escalates back to you.

**Rolling it out**

> Hold off on PR-wide gates while the chain is still in flux; every adjustment becomes a team-visible event.

## Takeaways

- The cycle itself can be encoded: a repeated manual check becomes a skill,
  then part of a chain, then a gate on every PR.
- A concrete chain to start from: review for bugs, simplify, verify end to
  end, check against design guidelines.
- Humans step in on escalation rather than at every step.
