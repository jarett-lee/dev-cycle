# Building agents: When to fold subagents into your main agent loop

- **Source:** https://claude.com/resources/articles/building-agents-when-to-fold-subagents-into-your-main-agent-loop
- **Author:** Diane Sarkis (Anthropic)
- **Published:** 2026-10-22
- **Supports:** KISS, context and chunking (see `TODO.md`)

Written about agents built on Claude Platform rather than coding workflows, but
the tradeoff between one shared context and many summarized ones applies to
how a project is split up for Claude.

## Snippets

**One context beats handed-back summaries**

> Shared context produces better answers: for longer-running agents, we want the context from several different tasks to sit in the main context window. An agent that has seen the result of each earlier step can connect them, which leads to richer outputs and better insights than a set of summaries handed back by subagents.

> Progressive disclosure prevents context bloat: this technique allows teams to build single agents that can accomplish a wide variety of tasks without requiring all of the context to be immediately loaded into one long system prompt.

**Structure that mirrors the org chart**

> But too often we see enterprises give each team or problem type its own subagent, with the agent architecture becoming a copy of their org chart (Conway’s law at work).

**Less harness as models improve**

> Each new model lets you move more of the decision-making out of the harness and into the model itself.

## Takeaways

- Relevant to the chunking idea in `TODO.md`: summaries passed between
  contexts lose detail. The article prefers one context that loads detail on
  demand over splitting work across separate agents.
- It still recommends splitting when there's measured context bloat or work
  that can run in parallel in throwaway contexts.
- Structure built to make up for a weaker model becomes overhead as models
  improve (KISS).
