# Git Branching Overview

## Branches

When you make a commit in Git, each commit gets a unique hash that identifies it, along with some other information. Each commit also points to at least one preceding commit, called its parent.

Branches play a crucial role in Git. In collaborative coding projects, it's common to work on different features or aspects of the project at the same time. This is where branches become useful.

A branch acts like an alternate timeline within the project. It allows us to create isolated environments to experiment and develop multiple ideas simultaneously. Most importantly, **changes made in one branch won't affect others unless they are merged together**.

## What's the Master Branch?

In Git, you are _always_ working on a branch. If you've seen this:

```
On branch master
nothing to commit
```

The default branch is called `master` or `main` (more on this later). When you initialize a repository using `git init`, you automatically start on this branch. However, the `master` branch isn't special - it's just like any other branch.

Many developers use the `master` branch as the "source of truth" or the main branch of their codebase, but that's entirely up to you. From Git's perspective, `master` is just another branch and doesn't have to hold the definitive working version of your project.

## Master vs Main?

In 2020, Github changed the default branch from `master` to `main`. As of 2023, the default branch name in Git is also `main`. However, depending on your setup, the default branch name on your device might still be `master`.

While this isn't a huge change, you'll notice older projects using `master` as the default branch name, and newer projects using `main`. To keep things simple, I'll refer the default branch as `main` moving forward.

## The Importance of Branching

Many developers treat the `main` branch as the stable version of their codebase, where everything should work properly. You can create a new branch to experiment or make changes, then merge those changes back into the `main` branch if they're successful - or abandon the branch and continue working on `main`.

## A Common Workflow: Feature Branching

A popular Git workflow is called `feature branching`. In this approach, the `main` branch serves as the stable source of truth, while you create separate feature branches for new work. Once the feature is complete, you merge the branch back into `main`.

## What is HEAD?

In Git, `HEAD` is a pointer that refers to your current position in the respository. More specifically, it points to a branch reference. Normally, `HEAD` points to the latest commit on the `main` branch, but as you create more branches, it will point to the current branch you're working on.

When you run `git log` on the `main` branch, you might see something like this:

```
commit 722b18450c7599ad7ea084285d96e0e1b4ef2750 (HEAD -> main, origin/main, origin/HEAD)
Author: jenpennen <name@gmail.com>
Date:   Sat Oct 19 02:25:44 2024 -0700

    modified old file descriptions

commit f7d26198676046b2f70740f3866bb33b8c2d5654
Author: jenpennen <name@gmail.com>
Date:   Sat Oct 19 01:31:54 2024 -0700

    modified history of git and terminal basics

commit 5966383e04b45ff32779e6ce52b3a386a7fe0b23
Author: jenpennen <name@gmail.com>
...
```

Here, `HEAD` points to `main`, and `main` points to the most recent commit. When you make a new commit, `main` will point to the new commit, and `HEAD` will stay aligned with `main` since it's still pointing to the latest commit on that branch.

If you create a new branch, like `songs`, the `main` branch will continue to point to its latest commit, but `HEAD` will switch to `songs`. As you make new commits on `songs`, `HEAD` will follow those commits.

When you switch back to `main`, `HEAD` will once again point to the latest commit on the `main` branch.

### Conceptually

You can think of `HEAD` like bookmarks in a book. You can have multiple bookmarks for different places, but you can only be on one page at a time. `HEAD` is the bookmark that shows where you're currently working.
