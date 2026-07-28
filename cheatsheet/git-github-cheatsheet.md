# Git & GitHub Cheat Sheet

A free, printable one-page reference for the Git workflow most developers use every day. Pulled straight from the [Git & GitHub Companion Guide](../README.md).

## The Daily Workflow Loop

| Step | Command |
|------|---------|
| 1. Pull latest | `git pull` |
| 2. Create branch | `git checkout -b feature/name` |
| 3. Make changes | *(edit files)* |
| 4. Stage changes | `git add .` |
| 5. Commit | `git commit -m "message"` |
| 6. Push | `git push origin feature/name` |
| 7. Open PR | *(via GitHub)* |
| 8. Review → Merge | *(via GitHub)* |

## Essential Commands

| Task | Command |
|------|---------|
| Check status | `git status` |
| View history | `git log --oneline` |
| View changes | `git diff` |
| Switch branch | `git checkout branch-name` |
| List all branches | `git branch -a` |
| Delete local branch | `git branch -d branch-name` |
| Undo last commit (keep changes) | `git reset --soft HEAD~1` |
| Safely undo a pushed commit | `git revert <hash>` |
| Shelve uncommitted changes | `git stash` |
| Restore shelved changes | `git stash pop` |
| Abort a merge in progress | `git merge --abort` |
| Find lost commits | `git reflog` |

## Branch Naming

| Type | Pattern | Example |
|------|---------|---------|
| Feature | `feature/description` | `feature/user-auth` |
| Bug fix | `bugfix/description` | `bugfix/null-reference` |
| Hot fix | `hotfix/description` | `hotfix/security-patch` |
| Chore | `chore/description` | `chore/update-deps` |
| Docs | `docs/description` | `docs/update-readme` |

## Commit Message Format

```
type(scope): short description
```

| Type | When to use |
|------|------------|
| `feat` | New functionality |
| `fix` | Bug fix |
| `chore` | Maintenance, config |
| `docs` | Documentation only |
| `refactor` | Restructuring, no behavior change |
| `test` | Adding or updating tests |
| `style` | Formatting, whitespace only |

## Golden Rules

> Always pull before you start working.

> One branch = one purpose.

> One commit = one logical change.

> Never push directly to main.

> A good commit message explains what changed and why.

> When in doubt, run `git status` first.

> Never guess when resolving a merge conflict. Ask.

> Green CI before merge. No exceptions.

---

Want the reasoning behind every one of these rules — plus branching strategy, PR etiquette, and a full merge-conflict walkthrough? See the [Git & GitHub Companion Guide](../README.md#get-the-full-companion-guide).
