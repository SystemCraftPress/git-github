# Example: Branch Naming in Practice

The pattern is `type/short-description`. Here's how that plays out across real situations.

## Good Examples, by Type

| Situation | Branch name |
|---|---|
| Adding OAuth login | `feature/oauth-login` |
| Fixing a null reference on the profile page | `bugfix/profile-null-reference` |
| Patching a security issue in production, urgently | `hotfix/session-token-leak` |
| Bumping a dependency version | `chore/update-eslint` |
| Rewriting the setup docs | `docs/setup-instructions` |
| Removing dead code before a refactor | `chore/remove-legacy-auth` |
| Splitting a large component into smaller ones | `refactor/split-dashboard-component` |

## The Naming Test

Before creating a branch, ask: **could a teammate tell what this branch does from the name alone, without opening it?**

| Name | Passes? | Why |
|---|---|---|
| `feature/user-authentication` | Yes | Type and scope are both clear |
| `bugfix/checkout-total-rounding` | Yes | Specific enough to search for later |
| `fix2` | No | Which fix? Second attempt at what? |
| `johns-branch` | No | Says who, not what |
| `updates` | No | Every branch is "updates" |
| `test` | No | Ambiguous — a test of what, and should it even be merged? |

## A Note on Specificity

`feature/auth` is better than `feature/stuff`, but `feature/oauth-login` is better than `feature/auth` — it tells you which part of auth. When in doubt, err toward more specific. Branch names are free; ambiguity is not.

See the [quick reference](../reference/quick-reference.md) for the full naming table.
