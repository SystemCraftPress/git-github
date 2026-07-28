# Git Quick Reference

Command tables and lookup references for daily Git use. From the [Git & GitHub Companion Guide](../README.md).

## Common Commands

| Task                            | Command                                |
| -------------------------------- | --------------------------------------- |
| Clone a repository              | `git clone <url>`                      |
| Check status                    | `git status`                           |
| Pull latest changes             | `git pull`                             |
| Pull from specific branch       | `git pull origin main`                 |
| Create and switch to new branch | `git checkout -b feature/name`         |
| Switch to existing branch       | `git checkout branch-name`             |
| List all branches               | `git branch -a`                        |
| Stage all changes               | `git add .`                            |
| Stage specific file             | `git add filename.ext`                 |
| Commit staged changes           | `git commit -m "message"`              |
| Push branch to remote           | `git push origin branch-name`          |
| Delete local branch             | `git branch -d branch-name`            |
| Delete remote branch            | `git push origin --delete branch-name` |
| View commit history             | `git log --oneline`                    |
| View changes not yet staged     | `git diff`                             |
| View staged changes             | `git diff --staged`                    |

## What Command Do I Use For...?

| I want to...                       | Command                                |
| ------------------------------------ | ----------------------------------------- |
| See what has changed               | `git status`                           |
| Get the latest code                | `git pull`                             |
| Start new work                     | `git checkout -b feature/name`         |
| Save my progress                   | `git add . && git commit -m "message"` |
| Share my work                      | `git push origin branch-name`          |
| See what I committed               | `git log --oneline`                    |
| Undo last commit (keep changes)    | `git reset --soft HEAD~1`              |
| Undo last commit (discard changes) | `git reset --hard HEAD~1`              |
| Discard changes to a file          | `git checkout -- filename.ext`         |
| See all branches                   | `git branch -a`                        |
| Merge another branch into mine     | `git merge branch-name`                |

## Reset and Undo

> Reset and undo commands can be destructive. Understand what each does before using it.

| Command                        | What it does                                                               |
| --------------------------------- | ------------------------------------------------------------------------------ |
| `git reset --soft HEAD~1`      | Undoes last commit, keeps changes staged                                   |
| `git reset --mixed HEAD~1`     | Undoes last commit, keeps changes unstaged                                 |
| `git reset --hard HEAD~1`      | Undoes last commit, discards all changes                                   |
| `git checkout -- filename.ext` | Discards unstaged changes to a specific file                               |
| `git revert <commit-hash>`     | Creates a new commit that undoes a previous one — safe for shared branches |
| `git stash`                    | Temporarily shelves uncommitted changes                                    |
| `git stash pop`                | Restores the most recently stashed changes                                 |

> Prefer `git revert` over `git reset` on shared branches. Reset rewrites history — revert adds to it safely.

## Git Status Meanings

| Symbol | Meaning                               |
| -------- | ---------------------------------------- |
| `M`    | Modified — file has been changed      |
| `A`    | Added — new file staged for commit    |
| `D`    | Deleted — file has been removed       |
| `U`    | Untracked — file not yet known to Git |
| `??`   | Untracked in `git status` output      |
| `MM`   | Modified both staged and unstaged     |

## Branch Naming Quick Reference

| Type          | Pattern               | Example                       |
| --------------- | ------------------------ | -------------------------------- |
| Feature       | `feature/description` | `feature/user-authentication` |
| Bug fix       | `bugfix/description`  | `bugfix/login-null-reference` |
| Hot fix       | `hotfix/description`  | `hotfix/security-patch`       |
| Chore         | `chore/description`   | `chore/update-dependencies`   |
| Documentation | `docs/description`    | `docs/update-readme`          |

## Commit Type Quick Reference

| Type       | When to use                             |
| ------------ | ------------------------------------------ |
| `feat`     | Adding new functionality                |
| `fix`      | Fixing a bug                            |
| `chore`    | Maintenance, dependencies, config       |
| `docs`     | Documentation only                      |
| `refactor` | Code restructuring, no behavior change  |
| `test`     | Adding or updating tests                |
| `style`    | Formatting, whitespace, no logic change |

---

For the "why" behind these commands — plus scenario-based troubleshooting for when things go wrong — see the [Git & GitHub Companion Guide](../README.md#get-the-full-companion-guide).
