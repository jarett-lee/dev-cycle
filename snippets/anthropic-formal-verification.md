# LLMs are making formal software verification feasible at a much larger scale

- **Source:** https://www.anthropic.com/research/formal-verification
- **Author:** Anthropic Frontier Red Team (Keane Lucas, Aengus Lynch and others),
  with Theorem
- **Published:** 2026-10-22
- **Supports:** keeping invariants, make it work, review

Claude wrote machine-checked proofs that 239 fuzz-test entry points across 123
open-source libraries never crash for inputs under 64 MB, and found and fixed
bugs along the way.

## Snippets

**Specs come first**

> To prove that a piece of software is correct, we must first state what “correct” even means.

> …we take the approach of automatically converting their preexisting compilable test suites into a spec by encoding the rule “this test suite always passes,” using a general model of what it means to execute any RISC-V-compiled binary on Linux.

**Review the spec, not the proof**

> While this is an enormous volume of proof code, virtually none of it needs to be manually reviewed. The Rocq proof checker ensures that the spec is correctly satisfied by the proof.

> “Formally verified” does not mean “bug-free.”

> However, a proof checker can’t tell you whether your spec matches reality.

**Guarding against gaming the check**

> In this context, Claude could make any theorem provable by rewriting the program into one that trivially never crashes. To discourage this, we penalized any patch and offered extra credit for proving which inputs it changes and how few they are.

**Where it's heading**

> Just like static types, testing frameworks, and other correctness tooling, verification will mature from “bolted-on” to “built-in,” driven not only by LLMs but also by innovations in language design and development workflows.

## Takeaways

- Invariants can be machine-checked once they are written down as specs, and
  existing tests are a usable starting spec.
- Human attention moves to the spec and its assumptions. The proof can be
  checked mechanically; whether the spec matches reality can't.
- When Claude can change both the code and the thing that makes the check
  pass, the cycle needs a guard against passing the check the wrong way.
