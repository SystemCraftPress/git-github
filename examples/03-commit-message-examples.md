# Example: Commit Messages, Before and After

Real commit messages, rewritten. The "before" versions aren't exaggerated — they're the kind of thing that shows up in real history all the time.

## Case 1: A Bug Fix

**Before:** `fix`

**After:** `fix(cart): prevent quantity from going negative on rapid clicks`

The rewrite tells you the area (`cart`), the actual bug (quantity going negative), and the trigger (rapid clicks) — searchable and useful six months from now.

## Case 2: A Feature

**Before:** `updates`

**After:** `feat(dashboard): add export-to-CSV button for transaction history`

## Case 3: A Mixed Commit (should have been split)

**Before:** `stuff` — turns out this commit touched three unrelated things:

```
- Fixed a typo in the footer
- Added a new API endpoint for user preferences
- Refactored the date formatting utility
```

**After — split into three commits:**

```
docs(footer): fix typo in copyright year
feat(api): add endpoint for user preferences
refactor(utils): simplify date formatting logic
```

If any one of these breaks something, you can revert exactly that change — not all three.

## Case 4: A Chore

**Before:** `wip`

**After:** `chore(deps): bump lodash to 4.17.21 to resolve CVE-2021-23337`

Including *why* (a specific CVE) turns a routine dependency bump into a self-documenting security fix.

## The Pattern

```
type(scope): what changed, specifically
```

Read it back to yourself. If it doesn't explain what changed and why someone would care, it's not done yet. See the [quick reference](../reference/quick-reference.md#commit-type-quick-reference) for the full type list.
