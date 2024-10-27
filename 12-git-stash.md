# Git Stash

the `git stash` command **temporarily stores changes that are in your working directory and/or in the staging area**, allowing you to switch branches or work on another task without losing your progress. This can be incredibly useful if you're working on a feature midway and realize you need to quickly address a different issue in your code. Stashing "pauses" your current work, removes it from your working directory, and allows you to return to it later.

## Why Git Stash is Useful

If you have unstaged changes in your working directory and try to switch branches, Git will sometimes carry over your changes without a warning if those changes don't conflict with the target branch. This means:

- Git assumes the changes are compatible across branches and carries them into the new branches working directory.
- This might seem convenient, but this can become confusing since changes can unintentionally span different branches and blur the lines between distinct tasks/goals of each branch.

Using `git stash` ensures your changes are isolated to a specific context, keep each branch's purpose clear, and your work organized.

## Basic Stashing Workflow

### Save your work with `git stash`

When you run `git stash , Git saved any modifications (both staged and unstaged) and clears your working directory. Here's the command to stash changes:

```
> git stash
```

You can also add a message to descrive the stash.

```
> git stash push -m "Work on feature x"
```

### View your stash with `git stash list`

To see a list of stashed changes, use:

```
> git stash list
```

This will show each stash along with its description, if provided, so you can identify saved changes more easily.

### Apply stashed changes with `git stash apply`

To reapply the most recent stash, use:

```
> git stash apply
```

If you want to apply a specific stash (eg, stash@{2}), specific it by its index:

```
> git stash apply stash@{2}
```

### Remove stashes with `git stash drop`

After you've successfully reapplied a stash, you can delete it:

```
> git stash drop stash@{2}
```

Alternatively, you can clear all stashes with:

```
> git stash clear
```

### Pop stashed changes with `git stash pop`

`git stash pop` re-applies the most recent stash, similar to `git stash apply` but it also **removes it from the stash list automatically**.

```
> git stash pop
```

## Additional `git stash` Options

### Stashing Only Unstaged Changes

If you want to stash only the unstaged changes and leave staged changes as they are, use:

```
> git stash --keep-index
```

### Stashing Specific Files

Use the `--path` flag to specific changes to stash:

```
> git stash push -p
```

## Example Workflow

Imagine you're working on a feature but need to quickly switch to another branch:
**1. Stash your changes:**

```
> git stash -m "Saving progress on feature x"
```

**2. Switch to another branch:**

```
> git switch feature-branch
```

**3. After resolving the urgent issur, return to your original branch:**

```
> git switch your-feature-branch
```

**4. Retrieve your saved work:**

```
> git stash pop
```

Through `git stash`, you can temporarily set aside work without committing unfinished changes to the repository.
