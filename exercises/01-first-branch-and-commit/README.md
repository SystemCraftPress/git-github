# Exercise 1: Your First Branch and Commit

**Goal:** run the full daily loop once, deliberately, so it stops feeling like a sequence of memorized commands.

**Time:** ~10 minutes

## Setup

Create a throwaway practice repo — don't use a real project for this.

```bash
mkdir git-practice && cd git-practice
git init
echo "# Practice Repo" > README.md
git add README.md
git commit -m "chore: initial commit"
```

## Task

1. Create a branch named `feature/add-notes-file`.
2. Create a file called `notes.md` with any content you like.
3. Check `git status` — confirm you can explain every line it prints before moving on.
4. Stage only `notes.md` (not everything — practice being selective).
5. Commit with a message that follows the `type(scope): description` pattern.
6. Run `git log --oneline` and confirm your commit is there with a clear message.

## Checkpoints

Stop and verify at each step — don't run ahead:

- [ ] `git branch` shows you're on `feature/add-notes-file`, not `main`
- [ ] `git status` before staging shows `notes.md` as untracked
- [ ] `git status` after staging shows it under "Changes to be committed"
- [ ] `git log --oneline` shows two commits total

## Stretch Goal

Undo your commit *without* losing the file (hint: `git reset --soft`), then redo it with a better message. This is a safe, common recovery move — practice it while the stakes are zero.

## Reference

If you get stuck, the [cheat sheet](../../cheatsheet/git-github-cheatsheet.md) and [quick reference](../../reference/quick-reference.md) cover every command used here.
