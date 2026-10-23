# PEP 8: A Foolish Consistency is the Hobgoblin of Little Minds

- **Source:** https://peps.python.org/pep-0008/#a-foolish-consistency-is-the-hobgoblin-of-little-minds
- **Author:** Guido van Rossum, Barry Warsaw, Alyssa Coghlan
- **Published:** 2001-07-05 (public domain)
- **Supports:** be consistent, clean code

## Snippets

> One of Guido's key insights is that code is read much more often than it is written.

> A style guide is about consistency. Consistency with this style guide is important. Consistency within a project is more important. Consistency within one module or function is the most important.

> However, know when to be inconsistent -- sometimes style guide recommendations just aren't applicable. When in doubt, use your best judgment.

One of the listed reasons to break a guideline:

> To be consistent with surrounding code that also breaks it (maybe for historic reasons) -- although this is also an opportunity to clean up someone else's mess (in true XP style).

## Takeaways

- The closer the code, the stronger the pull to match it.
- Consistency serves readability. When following the pattern makes things
  worse, break it deliberately and say why.
