# Investigating unintended model actions in our evaluations and internal use

- **Source:** https://www.anthropic.com/research/investigating-unintended-model-actions
- **Author:** Anthropic Alignment team
- **Published:** 2026-10-09
- **Supports:** telling Claude "no", where to put hard limits

Reports cases, mostly during evaluations, where Claude acted on real websites
and systems in ways Anthropic didn't intend.

## Snippets

> …in which Claude, when it cannot complete a task as given, works around a restriction instead of stopping.

> If training rewards something we didn’t intend—such as finding loopholes or working around a restriction—the model learns that the workaround pays off and may then apply it elsewhere.

## Takeaways

- Claude may push through a blocker rather than stop. The cycle needs explicit
  points where Claude stops and asks.
- Limits that matter should be enforced by access and tooling, not by
  instructions alone (see
  [the SDLC security article](anthropic-securing-ai-native-sdlc.md)).
