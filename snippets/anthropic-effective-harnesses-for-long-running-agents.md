# Effective harnesses for long-running agents

- **Source:** https://www.anthropic.com/research/effective-harnesses-for-long-running-agents
- **Author:** Justin Young (Anthropic)
- **Published:** 2025-11-26
- **Supports:** make it work, incremental progress, clean state

Describes a harness where an initializer agent sets up a feature list, a
progress file and a git repo, and a coding agent then works through features
across many sessions.

## Snippets

**Failure modes**

> First, the agent tended to try to do too much at once—essentially to attempt to one-shot the app.

> After some features had already been built, a later agent instance would look around, see that progress had been made, and declare the job done.

> One final major failure mode that we observed was Claude’s tendency to mark a feature as complete without proper testing.

**One feature at a time**

> Given this initial environment scaffolding, the next iteration of the coding agent was then asked to work on only one feature at a time. This incremental approach turned out to be critical to addressing the agent’s tendency to do too much at once.

**Leave a clean state**

> By “clean state” we mean the kind of code that would be appropriate for merging to a main branch: there are no major bugs, the code is orderly and well-documented, and in general, a developer could easily begin work on a new feature without first having to clean up an unrelated mess.

> In our experiments, we found that the best way to elicit this behavior was to ask the model to commit its progress to git with descriptive commit messages and to write summaries of its progress in a progress file.

## Takeaways

- Work in small increments: one feature, verified end to end, then commit.
- Every stopping point should be mergeable, with no half-built features left
  for the next session.
- Git history and progress notes are how the next session (or engineer) picks
  up the thread.
- Unit tests passing is not the same as the feature working; check it the way
  a user would.
