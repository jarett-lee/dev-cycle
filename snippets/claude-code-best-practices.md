# Best practices for Claude Code

- **Source:** https://code.claude.com/docs/en/best-practices
  (the older post at https://www.anthropic.com/engineering/claude-code-best-practices
  now redirects here)
- **Author:** Anthropic (Claude Code docs)
- **Retrieved:** 2026-10-23
- **Supports:** make it work, the explore / plan / code loop, review

## Snippets

**Context is the main constraint**

> Most best practices are based on one constraint: Claude's context window fills up fast, and performance degrades as it fills.

**Give Claude a way to verify its work**

> Give Claude a check it can run: tests, a build, a screenshot to compare. It's the difference between a session you watch and one you walk away from.

> Claude does the work, runs the check, reads the result, and iterates until the check passes.

**Explore first, then plan, then code**

> Separate research and planning from implementation to avoid solving the wrong problem.

> Planning is most useful when you're uncertain about the approach, when the change modifies multiple files, or when you're unfamiliar with the code being modified. If you could describe the diff in one sentence, skip the plan.

**Course-correct early and often**

> If you've corrected Claude more than twice on the same issue in one session, the context is cluttered with failed approaches. Run `/clear` and start fresh with a more specific prompt that incorporates what you learned.

**Add an adversarial review step**

> Before treating a task as done, have a subagent review the diff in a fresh context and report gaps.

## Takeaways

- "Done" means a check Claude can run has passed, not that the code looks
  right.
- Plan only when the change is uncertain or spans files; skip it for one-line
  diffs.
- Restart with a better prompt rather than piling corrections onto a long
  session.
- Review the diff in a fresh context before calling it done, and weigh that
  review's findings (see the source control article on over-engineering).
