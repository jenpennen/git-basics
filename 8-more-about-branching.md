# Branching Commands

## Viewing Branches

To view your existing branches, use the command `git branch`:

```
> git branch
OUTPUT:
* main
(END)
```

The default branch in most git repositories is `main`, but this can be configured (more on that later). The `*` (asterisk) represents the branch you're currently on. If you're in a text editor viewing branches, type `:q` to exit.

You can also use the following command:

```
> git branch -v
```

This will display the most recent commits including the commit message, the tip of the branch, and the branch name.

## Creating New Branches

To create a new branch based on the current `HEAD`, use `git branch <branch-name>`. This only creates the branch and doesn't switch you to it (`HEAD` stays the same).

```
> git branch songs
```

## Switching Branches

In Git, branches allow you to work on different features or fixes independently. Once you've created a branch, you can easily switch between them using simple Git commands.

### How to Switch Branches

To switch to an existing branch, use the `git switch` command followed by the branch name:

```
> git switch <branch-name>
```

Example:

```
> git branch songs # creates the 'songs' branch
> git switch songs # switches to the 'songs' branch
OUTPUT: Switched to branch 'songs'
```

Now, `HEAD` will now point to the `songs` branch instead of `main`. You can confirm this by checking `git log` and `git status`

```
> git switch songs
OUTPUT:
On branch songs
Your branch is up to date with 'origin/songs'.

> git log
OUTPUT:
commit 7ec8c8431b5c2cc0536f7be935efa834fb044be7 (HEAD -> songs, origin/songs)
```

> [!NOTE]
> If you've made changes on a branch, you need to **commit or stash** them before switching to another branch (more on this later).

### Stashing Changes Before Switching

We'll cover this in more depth in the merging sections. If you don’t stash your changes, any files specific to that branch will carry over when you switch to another branch. In cases of conflicts, Git will alert you. As a best practice, always commit or stash your changes before switching branches.

```
> git stash
```

After switching branches, you can reapply your stashed changes with:

```
> git stash pop
```

### Switching and Creating a New Branch

If you want to both create a new branch and switch to it immediately,
you can use the `-c` flag with `git switch`. The `-c` stands for "create".

```
> git switch -c <new-branch-name>
```

Example:

```
> git switch -c hobbies
```

### Using `git checkout` to Switch Branches

Historically, the `git checkout` command was used to switch branches, and it still works. However, since checkout has several other functions, the simpler `git switch` command was introduced specifically for switching branches. Older tutorials may use `git checkout`, but both commands work for this purpose.

```
> git checkout <branch-name>
```

Example:

```
> git checkout main
```

While `git checkout` can be used for other tasks like restoring files, we'll focus on branch switching here. Personally, I prefer using `git switch` as it is more straightforward and intended specifically for switching branches.

## Deleting a Branch

Once you've finished working on a branch and no longer need it, it's a good practice to delete it to keet your repository clean and organized. There are two main ways to delete branches in Git: locally and remotely.

### Deleting a Local Branch

To delete a branch locally (on your machine), use the `git branch -d` command followed by the branch name. Here's the syntax:

```
> git branch -d <branch-name>
```

Example:

```
> git branch -d feature-branch
```

This will delete the branch named `feature-branch`. However, Git will only allow you to delete a branch that has been fully merged into the branch you're currently on. If the branch contains unmerged changes, Git will warn you and prevent the deletion to avoid accidental data loss.

If you are sure you want to delete the branch and discard any unmerged changes, you can force-delete it by using the `-D` option instead of `-d`:

```
> git branch -D <branch-name>
```

Example:

```
> git branch -D experimental-branch
```

### Deleting a Remote Branch

To delete a branch from the remote repository (e.g., on Github or GitLab), use the following command:

```
> git push origin --delete <branch-name>
```

Example:

```
> git push origin --delete feature-branch
```

This removes the branch from the remote repositoru, meaning it will no longer be accessible to others.

**Best Practices**

- **Delete merged branches**: Once a feature or fix has been merged into `main` or another base branch, it's good practice to delete the related branch to avoid clutter.
- **Check before deleting**: Always double-check that your branch is no longer needed before deleting it, especially when force-deleting or removing from the remote repository.

## Renaming Branches

You can rename a branch if you decide that the current name no longer suits the work or context.

### Renaming a Local Branch

To rename a branch that you're currently on, you can use the following command:

```
> git branch -m <new-branch-name>
```

Example:

```
git branch -m favorite-songs
```

This will rename your current branch to `favorite-songs`. The `-m` flag stands for "move", but in this cause, it's used to rename the branch.

If you want to rename a branch you're **not currently on**, you can specify the old branch name and the new branch name:

```
git branch -m <old-branch-name> <new-branch-name>
```

Example:
git branch -m songs recent-songs

This renames the `songs` branch to `recent-songs` without switching to it.

### Renaming a Remote Branch

Renaming a remote branch involves a few extra steps:

1. Rename the local branch using the method described above.
2. Delete the old branch from the remote:

```
> git push origin --delete <old-branch>
```

3. Push the renamed branch to the remote:

```
> git push origin <new-branch>
```

4. Reset the upstream tracking if necessary:

```
> push --set-upstream origin <new-branch-name>
```

**Remember:** Make sure all changes are committed or stashed to avoid disruption.
