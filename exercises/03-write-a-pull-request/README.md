# Exercise 3: Write a Real Pull Request

**Goal:** practice writing a PR description that actually helps a reviewer, using a template instead of guessing.

**Time:** ~10 minutes

## Setup

Use any small change you've made recently — in the practice repo from Exercise 1, or a real side project. Push a branch with at least one commit so you have something to open a PR against.

## Task

Fill out this template for your change. Don't skip sections — if one feels irrelevant, write "N/A" and move on; that's still more useful than silence.

```markdown
## What changed

(One or two sentences. What did you actually do?)

## Why

(What problem does this solve, or what prompted it?)

## How to review

(What should the reviewer pay attention to? Any tricky parts?)

## Testing

(How did you verify this works? Manual steps, tests run, etc.)

## Linked issue

(Closes #___, or N/A)
```

Open the PR on GitHub using this as the description. If you don't have a real repo to open it against, write it out in a markdown file and self-review it as if you were the reviewer.

## Self-Review Checklist

Before requesting review, check your own PR against this list:

- [ ] Title is specific — a stranger could guess what changed from the title alone
- [ ] Description explains *why*, not just *what* (the diff already shows what)
- [ ] No unrelated changes snuck in (check the file list)
- [ ] Commits are clean — no `wip` or `fix` messages left in
- [ ] You'd be comfortable if this were the only context a reviewer had

## Stretch Goal

Find a PR you (or a teammate) opened in the past without a template. Rewrite its description using the template above. Notice what was missing.

## Reference

See the [daily workflow example](../../examples/01-daily-workflow.md) for a full PR written in context. The full [Companion Guide](../../README.md#get-the-full-companion-guide) covers merge strategies and review etiquette in more depth.
