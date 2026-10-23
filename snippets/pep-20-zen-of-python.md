# PEP 20: The Zen of Python

- **Source:** https://peps.python.org/pep-0020/
- **Author:** Tim Peters
- **Published:** 2004-08-19 (public domain)
- **Supports:** KISS, YAGNI, clean code, make it work

## Snippets

Selected lines:

```text
Simple is better than complex.
Complex is better than complicated.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
In the face of ambiguity, refuse the temptation to guess.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
```

## Takeaways

- "If the implementation is hard to explain" is a useful test for a change
  that will be reviewed for intent rather than line by line.
- "Refuse the temptation to guess" means asking the engineer when
  requirements are ambiguous, rather than building for every reading.
