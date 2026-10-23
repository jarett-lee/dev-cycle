# Snippets

Verbatim excerpts from articles relevant to Claude's development cycle, one
file per source, newest first. Quotes are copied from the source; takeaways
are ours. See `../CLAUDE.md` for the conventions.

| File | Published | Supports |
| --- | --- | --- |
| [anthropic-formal-verification.md](anthropic-formal-verification.md) | 2026-10-22 | keeping invariants, make it work, review |
| [anthropic-fold-subagents-into-main-agent-loop.md](anthropic-fold-subagents-into-main-agent-loop.md) | 2026-10-22 | KISS, context and chunking |
| [anthropic-redesigning-source-control.md](anthropic-redesigning-source-control.md) | 2026-10-13 | the human role, intent review, YAGNI, consistency, DRY |
| [anthropic-investigating-unintended-model-actions.md](anthropic-investigating-unintended-model-actions.md) | 2026-10-09 | telling Claude "no", hard limits |
| [anthropic-opus-5-5-longer-coding-sessions.md](anthropic-opus-5-5-longer-coding-sessions.md) | 2026-09-24 | context and chunking |
| [anthropic-scaling-test-impact-analysis.md](anthropic-scaling-test-impact-analysis.md) | 2026-09-14 | YAGNI (counterpoint), make it work |
| [anthropic-multiagent-systems.md](anthropic-multiagent-systems.md) | 2026-08-13 | parallel agents, telling Claude "no" |
| [anthropic-verification-loops-with-skills.md](anthropic-verification-loops-with-skills.md) | 2026-07-22 | make it work, the dev loop |
| [anthropic-securing-ai-native-sdlc.md](anthropic-securing-ai-native-sdlc.md) | 2026-07-21 | the human role, review, keeping invariants |
| [anthropic-effective-harnesses-for-long-running-agents.md](anthropic-effective-harnesses-for-long-running-agents.md) | 2025-11-26 | make it work, incremental progress |
| [anthropic-building-effective-agents.md](anthropic-building-effective-agents.md) | 2024-12-19 | KISS, YAGNI, review |
| [claude-code-best-practices.md](claude-code-best-practices.md) | living doc | make it work, explore / plan / code, review |
| [google-code-review-standard.md](google-code-review-standard.md) | living doc | review, over-engineering, consistency |
| [pep-20-zen-of-python.md](pep-20-zen-of-python.md) | 2004-08-19 | KISS, clean code |
| [pep-8-consistency.md](pep-8-consistency.md) | 2001-07-05 | be consistent, clean code |

## To collect

Relevant sources that haven't been captured yet.

From the second half of 2026:

- Addy Osmani, Morgan Westlee Lunt and Qing Wang, "How the Claude Code team
  does code review" (October 2026): risk-tiered human approval for code that
  is mostly Claude-written.
  https://claude.dev/blog/solving-code-review-at-anthropic/
- Birgitta Böckeler, "TDD inside the agent loop - theater or actual value?"
  (August 2026): https://martinfowler.com/articles/exploring-gen-ai/tdd-in-the-agent-loop.html
- "Beyond Code Generation: Reliability, Verification, and Cost Economics in
  the Agentic Software Development Lifecycle" (arXiv, September 2026):
  https://arxiv.org/abs/2609.04681
- "Humans are Missing from AI Coding Agent Research" (arXiv, August 2026):
  https://arxiv.org/abs/2608.12355

Classics behind the principles:

- Martin Fowler, "Yagni": https://martinfowler.com/bliki/Yagni.html
- Kent Beck, "Make it work, make it right, make it fast":
  https://wiki.c2.com/?MakeItWorkMakeItRightMakeItFast
- Sandi Metz, "The Wrong Abstraction" (DRY's limits):
  https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction
- Robert C. Martin, "The Single Responsibility Principle" (SOLID):
  https://blog.cleancoder.com/uncle-bob/2014/05/08/SingleReponsibilityPrinciple.html
- Dan McKinley, "Choose Boring Technology" (KISS):
  https://mcfunley.com/choose-boring-technology
- Simon Willison, "Vibe engineering" (practices for AI-assisted development):
  https://simonwillison.net/2025/Oct/7/vibe-engineering/
