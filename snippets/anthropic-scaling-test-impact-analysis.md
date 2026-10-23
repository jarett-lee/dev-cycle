# Agentic coding is straining CI. Here's how we scaled test impact analysis at Anthropic

- **Source:** https://claude.com/resources/articles/agentic-coding-is-straining-ci-heres-how-we-scaled-test-impact-analysis-at-anthropic
- **Author:** Sachin Malhotra (Anthropic)
- **Published:** 2026-09-14
- **Supports:** YAGNI (counterpoint), make it work

Anthropic's CI job volume grew 25x in six months. Three quick patches bought
less time each, and a redesign by one engineer took three weeks.

## Snippets

**Code is no longer the bottleneck**

> Writing code is no longer the constraint, and once PR review gets accelerated, CI starts feeling the pressure.

> On the other hand, overhauling and completely redesigning a service also takes a fraction of the time and is much more sustainable now that writing code is no longer the bottleneck.

**Agents need precise tests**

> Additionally, humans are great at determining which test failures don’t apply to them while agents will require more context and direction. When they get a specific set of valid tests, they can self-verify and iterate more effectively.

**Over-engineering, reconsidered**

> Over-engineering as a concept is starting to slightly fade away, or at least the bar is moving much higher. You can now start to account for 10-20x the perceived scale in your v0 designs as long your budget allows for it.

**Observability for Claude**

> Instrument your services to act as Claude’s eyes and ears. It allows Claude to hill-climb and fix problems incrementally much better and faster than we could manually.

## Takeaways

- A direct counterpoint to YAGNI in `principles.md`: when code is cheap,
  designing for much larger scale up front, or redesigning instead of
  patching, may pay off. This sits in tension with the source control
  article's warning about over-engineering for hypothetical concerns.
- Agents verify better against a small, trustworthy set of relevant tests than
  against a noisy full suite.
- Instrumentation is part of the cycle: it's how Claude sees whether a change
  worked.
