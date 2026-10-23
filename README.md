# dev-cycle

Defining a good software development cycle for Claude: how an engineer and
Claude split the work from idea to merged change, and which design principles
Claude holds itself to along the way.

## What we're exploring

Which parts of the cycle humans should own when working with Claude. Current
candidates:

- high-level design
- tradeoffs
- the judgment to tell Claude "no"
- reviewing the intent of a change
- keeping invariants

The [snippets](snippets/) collect what others have reported so far.

## Layout

| Path | What it holds |
| --- | --- |
| [`principles.md`](principles.md) | General design principles: make it work, KISS, YAGNI, be consistent, DRY, clean code, SOLID |
| [`snippets/`](snippets/) | Verbatim excerpts from relevant articles, one file per source, with takeaways |
| [`CLAUDE.md`](CLAUDE.md) | Conventions for Claude when editing this repo |

## Status

Collecting source material. Next step: draft the cycle itself from the
snippets and principles.
