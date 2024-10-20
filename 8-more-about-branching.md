# Branching Commands

## Viewing Branches

To view your existing branches, use the command `git branch`:

```
> git branch
OUTPUT:
* main
(END)
```

The default branch in most git repository is `main`, but this can be configured (more on that later). The `*` (asterisk) represents the branch you're currently on. If you're in a text editor viewing branches, type `:q` to exit.

## Creating New Branches

To create a new branch based on the current `HEAD`, use `git branch <branch-name>`. This only creates the branch and doesn't switch you to it (`HEAD` stays the same).

```
> git branch songs
```

## Switching Branches

After creating a new branch, switch to it using `git switch <branch-name>`.
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

**NOTE:** If you've made changes on a branch, you need to **commit or stash** them before switching to another branch (more on this later).

## `git stash`

We'll cover this in more depth in the merging sections. If you don’t stash your changes, any files specific to that branch will carry over when you switch to another branch. In cases of conflicts, Git will alert you. As a best practice, always commit or stash your changes before switching branches.

```
> git stash
```

## Creating AND Switching

To create AND switch to a new branch in a single step, use the `-c` flag with `git switch`. The `-c` stands for "create".

```
# git switch -c <branch-name>
> git switch -c hobbies
```

## Another Way of Switching: `git checkout`

Historically, `git checkout <branch-name>` was used to switch branches, and it still works. However, since checkout has several other functions, the simpler `git switch` command was introduced specifically for switching branches. Older tutorials may use `git checkout`, but both commands work for this purpose.

While `git checkout` can be used for other tasks like restoring files, we'll focus on branch switching here. Personally, I prefer using `git switch` as it is more straightforward and intended specifically for switching branches.

## Deleting a Branch
