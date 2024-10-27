# Merging

## Overview

Branching makes it easy to work within self-contained contexts, but you'll often need to integrate changes from one branch into another. This is where **git merging** comes in, allowing you to combine changes from different branches into a single history without losing any work. This can be done with the `git merge` command.

## How Git Merging Works

When you merge two branches, Git takes the changes from the source branch (the branch you want to merge) and applies them to the target branch (the branch you're on). This process compares the commits from both branches and, if needed, creates a new commit on the target branch to bring everything together.

## Key Concepts

The merge command can be a little confusing at first. Remember:

- **Git merge branches, not specific commits**.
- **Merges always happen on the branch you are currently checked out on(the HEAD branch)**.

## How to Merge Branches

1. Switch to or checkout to the branch you want to merge into (the target branch).
2. Use the `git merge` command to merge changes from a specific branch (the source branch) into the current branch.
   Example:

```
> git switch main #target branch
> git merge hobbies #source branch
```

In this example, Git takes the commits from `hobbies` and merges them into the `main` branch. This is known as a **fast-forward merge**, becuase Git simply moves the `main` branch forward to catch up with the commits on `hobbies`.

## Types of Merges

### Fast-Forward Merge

- Occurs when there have been no changes on the target branch since the source branch was created.
- Git moves the target branch pointer forward to the latest commit on the source branch **without create a new merge commit**.

```
> git switch main # Target branch
> git merge childhood-favorites # Source branch
```

This brings the changes from `childhood-favorites` into `main` and moves the commit history forward. You can verify this `git log`.

**Note**: After the merge, any further changes to the source branch won't automatically appear on the target branch and vice versa - you'll need to merge again if needed. **To reiterate**, you can keep working on the source branch and any changes made to it will **not** exist on the target branch.

#### Beware ...

There will be instances when Git will attempt to perform a fast-forward merge but can't, likely due to conflicting changes between your local branch and the remote branch.You might see some error like this:

```
To https://github.com/jenpennen/git-basics.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/jenpennen/git-basics.git'
```

A fast-forward merge is only possible when your branch has **no new commits diverging from the remote branch's history**. You can address this by performing a regular merge:

```
> git pull --no-ff origin main
```

Use a regular `git pull`, which will perform a non-fast-forward merge (will go more into this later). This will create a merge cmmit if there are conflicts, allowing you to resolve them manually.

**You can also ...**

```
> git pull --rebase origin main
```

If you prefer to keep your commit history cleaner, rebase your changes on top of the remote branch. This applies your local changes after the latest changes from the remote branch. If there are any conflicts, Git will stop and prompt you to resolve them before continuing.

> [!Warning] Avoid rebasing branches that have been shared with others or that others might be working on. Merging in these cases will preserve the shared commit history. Similarly, if the branch history is complex, merging will be a safer approach.

### Three-Way Merge (or Merge Commit)

- Occurs when there have been changes in both the source and target branches since the source branch was created.
- Git compares the base commit (the common ancestor of both branches), the latest commit on the target branch, and the latest commit on the source branch. It **combines the differences and creates a new "merge commit" that combines the changes**.

```
> git switch main # Target branch
> git merge childhood-favorites # Source branch
```

Afterward, you'll see a new commit in `git log` shwoing the merge history.

Example:

```
commit 10efd9b7337c58cde150c8e4b2924c5451c9df22 (HEAD -> main, origin/main, origin/childhood-favorites, origin/HEAD, childhood-favorites)
Merge: b2cd61e 2339bdd
Author: jenpennen <name@gmail.com>
Date:   Mon Oct 21 18:35:29 2024 -0700

    Merge branch 'childhood-favorites'
```

This is an example of a non-fast forward merge where things are still automatically merged but you need to provide a message (or just keep Git's default message). There are no conflicting changes.

### Merge Conflicts

Sometimes, Git may not be able to automatically combine changes, resulting in **merge conflicts**, which you'll need to manually resolve. These can occur when both branches modify the same part of a file or when one branch deletes a file that the other branch modifies. In such cases, Git will stop the merge and indicate the conflicts:

```
CONFLICT(content): Merge conflict in [some file]
Automatic merge failed; fix conlicts and then commit the result.
```

Git will modify the conflicting file to show the differences, like this:

```
<<<<<<< HEAD
I did something here
=======
I have done something else here :0
>>>>>> childhood-favorites
```

Whenever you encounter merge conflicts, follow these steps to resolve them:

1. Open up the files with merge conflicts.
2. Edit the files to remove the conflicts. Decide which branch's content you want to keep in each conflict -- Or keep the content from both.
3. Remove the conflict markers in the document.
4. Stage the resolved files and commit the changes:

```
> git add [file]
> git commit -m "you commit message"
```

## Some Best Practices for Merging

- **Commit and push changes regularly**. This reduces the chance of conflicts by keeping changes small and easy to integrate.
- **Pull before merging**. Always make sure your local branch is up to date before merging to avoid unnecessary conflicts.
- **Test after merging**. Make sure the integration didn't introduce any issues.
