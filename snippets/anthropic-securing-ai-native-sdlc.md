# How Anthropic secures its AI-native software development lifecycle

- **Source:** https://claude.com/resources/articles/how-anthropic-secures-its-ai-native-software-development-lifecycle
- **Author:** Jason Clinton (Deputy CISO, Anthropic)
- **Published:** 2026-07-21
- **Supports:** the human role, review, keeping invariants

Walks through plan, code, test, deploy and monitor stages at Anthropic, where
Claude authors about 80% of merged code.

## Snippets

**The human role**

> More than half of all code is being merged by our internal version of Claude Tag while human engineers focus on directing, setting intent, and owning final approval.

> Today, multiple prototypes of major features can be created in hours, making detailed architectural review a less critical gate.

**Review by risk, with invariants called out**

> We tier our codebase by risk, and make deliberate decisions on what parts to automate.

> Another round of testing focuses on invariants like “user A can never read user B’s data,” and triggers additional manual reviews.

> Each review agent is designed and scoped to a specific, narrow focus and leverages RAG for additional context and memory surrounding past incidents.

**Closing the loop**

> Once an agent discovers a bug class, the relevant file is updated to prevent it recurring in future code.

**Hard boundaries**

> …this experience taught us to draw the boundary around access and actions, not around a model’s instructions or what we believe a model can do.

## Takeaways

- Another account of the human role: directing, setting intent, and final
  approval, with how much human review a change gets set by risk tier.
- Invariants are tested on their own and trigger extra human review.
- Up-front architectural review matters less when prototypes are cheap.
- Each bug class found should update CLAUDE.md or a skill so it doesn't recur.
- Hard limits belong in access controls, not instructions.
