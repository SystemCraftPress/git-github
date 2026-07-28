# Example: The Daily Workflow, End to End

A worked example of the 8-step loop covered in the guide, applied to a realistic task: adding email validation to a signup form.

## Scenario

You've been asked to add email validation to the signup form. It's a small, self-contained change — a good candidate for the standard loop.

## Walkthrough

**1. Get the latest changes**

```bash
git checkout main
git pull
```

**2. Create a branch**

```bash
git checkout -b feature/signup-email-validation
```

**3. Make the change**

Edit the signup form validation logic. Keep it scoped to email validation only — resist the urge to also "fix" unrelated things you notice along the way. That's a separate branch.

**4. Check what you're about to stage**

```bash
git status
```

```
On branch feature/signup-email-validation
Changes not staged for commit:
  modified:   src/forms/signup.js
  modified:   src/forms/validation.js
```

Two files, both directly related to the change. Good sign.

**5. Stage and commit**

```bash
git add src/forms/signup.js src/forms/validation.js
git commit -m "feat(signup): add email format validation"
```

**6. Push the branch**

```bash
git push origin feature/signup-email-validation
```

**7. Open a Pull Request**

Title: `Add email format validation to signup form`

Description:

```
Adds client-side email format validation to the signup form.
Invalid addresses now show an inline error instead of failing
silently at submit time.

Tested manually with valid, invalid, and empty inputs.
```

**8. Review, address feedback, merge**

A reviewer asks whether empty input is handled. You check, confirm it is, and reply on the PR. Once approved, you merge and delete the branch.

```bash
git branch -d feature/signup-email-validation
```

## Why This Is the Whole Point

Nothing here was complicated. That's what a healthy Git workflow looks like — small, traceable, reviewable steps, not heroics. See the [cheat sheet](../cheatsheet/git-github-cheatsheet.md) for the loop in table form.
