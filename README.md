# dev-cycle

Defining a good software development cycle for Claude: how an engineer and
Claude split the work from idea to merged change, and which design principles
Claude holds itself to along the way.

## Starting point

The engineers who built Anthropic's new source control system rate Claude as
better at writing code than they are. They still own the high-level design, the
tradeoffs, and the judgment to tell Claude "no", and they review the *intent* of
a change rather than every line
([Redesigning source control at Anthropic](snippets/anthropic-redesigning-source-control.md)).
A good cycle makes that division of labor work.

## Layout

| Path | What it holds |
| --- | --- |
| [`principles.md`](principles.md) | General design principles: make it work, KISS, YAGNI, be consistent, DRY, clean code, SOLID |
| [`snippets/`](snippets/) | Verbatim excerpts from relevant articles, one file per source, with takeaways |
| [`CLAUDE.md`](CLAUDE.md) | Conventions for Claude when editing this repo |

## Status

Collecting source material. Next step: draft the cycle itself from the
snippets and principles.
