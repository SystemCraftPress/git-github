# Exercise 2: Simulate and Resolve a Real Conflict

**Goal:** trigger an actual merge conflict on purpose, in a low-stakes setting, and resolve it correctly. The first time you see conflict markers shouldn't be during a real deadline.

**Time:** ~15 minutes

## Setup

Using the practice repo from Exercise 1 (or a fresh one):

```bash
echo "timeout: 3000" > config.txt
git add config.txt
git commit -m "chore: add default config"
```

## Task

**1. Create two branches from the same point:**

```bash
git checkout -b branch-a
echo "timeout: 5000" > config.txt
git commit -am "chore: increase timeout to 5000"

git checkout main
git checkout -b branch-b
echo "timeout: 8000" > config.txt
git commit -am "chore: increase timeout to 8000"
```

Both branches now change the same line in `config.txt`, differently.

**2. Merge branch-a into main:**

```bash
git checkout main
git merge branch-a
```

This should merge cleanly — nothing has diverged from `main` yet.

**3. Now merge branch-b into main:**

```bash
git merge branch-b
```

This is where the conflict happens. Git will tell you `config.txt` is conflicted.

**4. Open `config.txt`.** You'll see conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`). Identify which section is which branch's version.

**5. Resolve it.** Pick a final value, remove the markers entirely, and save.

**6. Stage and complete the merge:**

```bash
git add config.txt
git commit -m "Resolve merge conflict in config.txt"
```

## Checkpoints

- [ ] You saw real conflict markers, not a description of them
- [ ] You can explain what `<<<<<<< HEAD` and `>>>>>>> branch-b` each mean, from memory
- [ ] `config.txt` has no leftover markers after your commit
- [ ] `git log --oneline --graph` shows the merge in your history

## Stretch Goal

Run `git merge --abort` mid-conflict (before resolving) and confirm it fully undoes the merge attempt. Then redo the conflict and resolve it for real. Knowing the escape hatch removes most of the fear here.

## Reference

See the [worked conflict-resolution example](../../examples/04-resolving-a-merge-conflict.md) and the [conflict flow diagram](../../diagrams/merge-conflict-flow.md) if you get stuck.
