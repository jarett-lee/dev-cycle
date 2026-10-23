# Google engineering practices: code review

- **Sources:**
  - "The Standard of Code Review":
    https://google.github.io/eng-practices/review/reviewer/standard.html
  - "What to look for in a code review":
    https://google.github.io/eng-practices/review/reviewer/looking-for.html
- **Author:** Google
- **License:** CC BY 3.0 (https://github.com/google/eng-practices)
- **Supports:** review, KISS, YAGNI, be consistent, clean code

## Snippets

**The senior principle**

> In general, reviewers should favor approving a CL once it is in a state where it definitely improves the overall code health of the system being worked on, even if the CL isn't perfect.

> A key point here is that there is no such thing as "perfect" code—there is only *better* code.

> Technical facts and data overrule opinions and personal preferences.

**Over-engineering**

> A particular type of complexity is **over-engineering**, where developers have made the code more generic than it needs to be, or added functionality that isn't presently needed by the system. Reviewers should be especially vigilant about over-engineering. Encourage developers to solve the problem they know needs to be solved *now*, not the problem that the developer speculates *might* need to be solved in the future.

> "Too complex" usually means **"can't be understood quickly by code readers."**

**Design and comments**

> Do the interactions of various pieces of code in the CL make sense? Does this change belong in your codebase, or in a library? Does it integrate well with the rest of your system? Is now a good time to add this functionality?

> Usually comments are useful when they **explain why** some code exists, and should not be explaining *what* some code is doing.

## Takeaways

- Approve changes that make the code better; don't hold them for perfection.
- Over-engineering is a review finding in its own right, which is the YAGNI
  check the source control article says adversarial review can miss.
- Design questions (does it fit the system, is now the time) are the
  intent-level review engineers keep.
