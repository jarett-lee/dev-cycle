# Design principles

General design ideas Claude applies when writing and reviewing code. **Make it
work** is the most important; the rest follow in the order given.

## 1. Make it work

From Kent Beck's "make it work, make it right, make it fast": correct, verified
behavior comes first. Elegant code that doesn't work has no value.

**For Claude:** decide how "working" will be checked (a test, a build, a
screenshot) before writing code, and don't call a task done until that check
passes end to end.
See [Claude Code best practices](snippets/claude-code-best-practices.md) and
[Effective harnesses for long-running agents](snippets/anthropic-effective-harnesses-for-long-running-agents.md).

## 2. KISS: keep it simple

Choose the simplest design that solves the problem. Complexity has to earn its
place.

**For Claude:** prefer the obvious solution. Add layers, abstractions or
validation only when they demonstrably improve the outcome.
See [Building effective agents](snippets/anthropic-building-effective-agents.md)
and [The Zen of Python](snippets/pep-20-zen-of-python.md).

## 3. YAGNI: you aren't gonna need it

Build for the requirements you have now, not the ones you imagine might come.

**For Claude:** don't add options, extension points or defensive checks for
hypothetical cases. Reviews, including adversarial review by another Claude,
raise hypothetical concerns; trace a realistic path to failure before adding
code for one.
See [Redesigning source control](snippets/anthropic-redesigning-source-control.md)
(an over-defensive review led to "excessive validation and complexity") and
[Google's code review standard](snippets/google-code-review-standard.md) on
over-engineering.

## 4. Be consistent

Follow the conventions of the code around you. Consistency within a function
matters more than within a module, which matters more than within a project or
a style guide.

**For Claude:** match the existing naming, structure and idiom. But consistency
with a bad pattern is not a virtue: when an existing pattern violates a core
system constraint, flag it instead of copying it.
See [PEP 8](snippets/pep-8-consistency.md) and
[Redesigning source control](snippets/anthropic-redesigning-source-control.md)
("a pattern that should never have been allowed in the first place").

## 5. DRY: don't repeat yourself

Every piece of knowledge should have one authoritative home (*The Pragmatic
Programmer*, Hunt and Thomas).

**For Claude:** reuse existing helpers before writing new ones, and ask the
system of record instead of re-deriving its data. The source control migration
found systems that read the commit log to work out when a change merged
instead of asking the code review tool. DRY is about knowledge, not
similar-looking code: don't merge code that only looks alike, because the wrong
abstraction costs more than the duplication.

## 6. Clean code

Code is read far more often than it is written. Clear names, small focused
functions, and comments that explain *why* rather than *what* (*Clean Code*,
Robert C. Martin).

**For Claude:** reviewers now check the intent of a change rather than every
line, so the code and the change description have to make that intent obvious.
See [PEP 8](snippets/pep-8-consistency.md) and
[Google's code review standard](snippets/google-code-review-standard.md).

## 7. SOLID

Robert C. Martin's five object-oriented design principles:

- **Single responsibility:** a module has one reason to change.
- **Open/closed:** open for extension, closed for modification.
- **Liskov substitution:** a subtype works anywhere its base type does.
- **Interface segregation:** no client depends on methods it doesn't use.
- **Dependency inversion:** depend on abstractions, not concrete implementations.

**For Claude:** use these as lenses for reviewing a design, not as a license to
add interfaces and layers up front. Applied speculatively they run into KISS
and YAGNI.

## When principles conflict

A starting proposal, to refine: working beats elegant, and simple and needed
beat DRY and SOLID. Introduce an abstraction once the duplication is real and
its shape is known, not before. When unsure, ask the engineer: telling Claude
"no" is part of their job.
