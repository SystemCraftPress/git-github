# Example: Resolving a Real Merge Conflict

A full walkthrough, start to finish, using a realistic scenario: two developers both touched the app's timeout configuration.

## The Setup

You're on `feature/retry-logic`, adding retry behavior to an API client. While you were working, a teammate merged a change to `main` that also touched the timeout value.

## Step 1: Pull main into your branch

```bash
git checkout feature/retry-logic
git pull origin main
```

Git stops and reports a conflict:

```
Auto-merging src/config/network.js
CONFLICT (content): Merge conflict in src/config/network.js
Automatic merge failed; fix conflicts and then commit the result.
```

## Step 2: See what's conflicted

```bash
git status
```

```
On branch feature/retry-logic
You have unmerged paths.
  both modified:   src/config/network.js
```

One file. Manageable.

## Step 3: Open the file and read the markers

```js
const config = {
<<<<<<< HEAD
  timeoutMs: 8000,
  maxRetries: 3,
=======
  timeoutMs: 5000,
>>>>>>> main
};
```

Your branch (`HEAD`) set `timeoutMs` to 8000 and added `maxRetries`. `main` independently changed `timeoutMs` to 5000. Both changes are real and neither is simply "wrong."

## Step 4: Decide the correct final state

You check with the teammate who changed `main`: the 5000ms value came from a load-testing finding. Your `maxRetries` addition is unrelated and should stay. The correct resolution combines both:

```js
const config = {
  timeoutMs: 5000,
  maxRetries: 3,
};
```

## Step 5: Remove the markers, save, stage

```bash
git add src/config/network.js
```

## Step 6: Finish the merge

```bash
git commit -m "Resolve merge conflict in network.js: keep main's timeoutMs, keep retry addition"
```

## Step 7: Verify before moving on

Run the app or test suite. A conflict resolution that "looks right" but doesn't actually work is worse than the conflict itself — it merges silently and ships.

```bash
npm test
```

## What Made This Go Smoothly

Nobody guessed. The timeout value in question had a specific, checkable reason behind it, and a two-minute conversation resolved it correctly. See the [merge conflict diagram](../diagrams/merge-conflict-flow.md) for this same decision process as a flowchart.
