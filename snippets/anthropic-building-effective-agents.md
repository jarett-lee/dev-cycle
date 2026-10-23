# Building effective agents

- **Source:** https://www.anthropic.com/engineering/building-effective-agents
- **Author:** Erik S. and Barry Zhang (Anthropic)
- **Published:** 2024-12-19 (the page notes its tooling advice has since aged)
- **Supports:** KISS, YAGNI, make it work, review

## Snippets

**Simplicity first**

> When building applications with LLMs, we recommend finding the simplest solution possible, and only increasing complexity when needed.

> To repeat: you should consider adding complexity only when it demonstrably improves outcomes.

**Evaluator-optimizer loop**

> In the evaluator-optimizer workflow, one LLM call generates a response while another provides evaluation and feedback in a loop.

> This workflow is particularly effective when we have clear evaluation criteria, and when iterative refinement provides measurable value.

**Ground truth and human review**

> During execution, it's crucial for the agents to gain “ground truth” from the environment at each step (such as tool call results or code execution) to assess its progress.

> However, whereas automated testing helps verify functionality, human review remains crucial for ensuring solutions align with broader system requirements.

## Takeaways

- Complexity needs evidence that it helps. That applies to the code Claude
  writes, not only to agent design.
- A generate-then-review loop pays off when the review criteria are clear.
  Vague criteria invite the hypothetical concerns seen in the source control
  article.
- Tests verify that the code works; humans verify that it fits the system.
