# Branching Commands

## Viewing Branches

You use `git branch` to view your existing branches.

```
> git branch
OUTPUT:
* main
(END)
```

The default branch in every git repo is `main`, but you can configure this (more on this later). The `*` (asterisk) represents the branch you are currently on. If you want to leave the text editor displaying your branches, type `:q`.

## Creating New Branches

Use `git branch <branch-name>` to make a new branch based on the current `HEAD`. This just creates the branch. It does not switch you to that branch (the `HEAD` stays the same).

```
> git branch songs
```

## Switching Branches

Once you have created a new branch, use `git switch <branch-name>` to switch to it.
Example:

```
> git branch songs # songs branch created
> git switch songs
OUTPUT: Switched to branch 'songs'
```

`HEAD` will now point to the `songs` branch, not `main`. You can check this by checking `git log` and `git status`. You will see something like:

```
> git switch songs
OUTPUT:
On branch songs
Your branch is up to date with 'origin/songs'.

> git log
OUTPUT:
commit 7ec8c8431b5c2cc0536f7be935efa834fb044be7 (HEAD -> songs, origin/songs)
```

**NOTE:** When you modify anything on a branch, you must commit it or stash it before switching to another branch. (We'll go more on this later)

## Another Way of Switching

Historically, we used `git checkout <branch-name>` to switch branches. This still works. The checkout command also does a ton of other things, so the decision was made to add a standalone switch command which is much simpler. You'll see older tutorials and docs using checkout rather than switch. Both now work.