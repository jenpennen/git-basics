# Git Stash

the `git stash` command **temporarily stores changes that are in your working directory and/or in the staging area**, allowing you to switch branches or work on another task without losing your progress. This can be incredibly useful if you're working on a feature midway and realize you need to quickly address a different issue in your code. Stashing "pauses" your current work, removes it from your working directory, and allows you to return to it later.

## Why Git Stash is Useful

If you have unstaged changes in your working directory and try to switch branches, Git will sometimes carry over your changes without a warning if those changes don't conflict with the target branch. This means:

- Git assumes the changes are compatible across branches and carries them into the new branches working directory.
- This might seem convenient, but this can become confusing since changes can unintentionally span different branches and blur the lines between distinct tasks/goals of each branch.

Using `git stash` ensures your changes are isolated to a specific context, keep each branch's purpose clear, and your work organized.

```

```

If your uncommitted changes don't conflict with files on the branch you're switching to, Git will allow the switch without warning. It assumes that the changes are compatible with both branches and just "carries over" your uncommitted changes into the other branch's working directory. This means that your modifications are still present, even though you've switched branches. This may sound good, but it will get confusing in the long run, since branches are often used to work on entirely separate tasks/objectives.
