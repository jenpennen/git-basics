# Merging

## Overview

Branching makes it easier to work within self-contained contexts, but we will often want to incorporate changes from one branch to another. **Git merging** is used to integrate changes from one branch into another. It allows you to combine the work done in different branches into a unified history without losing any changes. We can do this using the `git merge` command.

## How Git Merging Works

When you merge two branches, Git takes the changes from the source branch (the branch you want to merge) and applies them to the target branch (the branch you're on). This process involves comparing the commits from both branches and creating a new commit on the target branch to combine the changes.

## Beware...

The merge command can be a little confusing at first, Remember these concepts:

- **We merge branches, not specific commits**.
- **We always merge to the current HEAD branch**.

## How to Merge Branches

1. Switch to or checkout the branch you want to merge the changes into (the target branch).
2. Use the `git merge` command to merge changes from a specific branch (the source branch) into the current branch.
   Example:

```
> git switch main
> git merge hobbies
```

In the case above, Git takes the commits from hobbies and merges them into the `main` branch. This type of merging is called a **fast forward merge**, since for main branch simply fast forwards to a couple commits to catch up with the hobbies branch, with no additional work on the main branch.

## Types of Merges

### Fast Forward Merge

- Occurs when there have been no changes on the target branch since the source branch was created.
- Git simply moves the target branch pointer forward to the latest commit of the source branch. No new merge commit is created.

```
> git merge feature-xyz
```

### Three-Way Merge

- Occurs when there have been changes in both the source and target branches since the source branch was created.
- Git compares the base commit (the common ancestor of both branches), the latest commit on the target branch, and the latest commit on the source branch. It combines the differences and creates a new "merge commit" to reflect the integration of changes.
