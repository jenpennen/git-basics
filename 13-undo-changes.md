# Undoing Changes in Git

## git checkout

In the [branching page](8-more-about-branching.md), I covered how `git checkout` can be used to switch branches. `git checkout` is an older command with many uses -- many developers use it to create branches, switch branches, restore files, and roll back to previous versions of the codebase.

## Using Checkout

To view a specific previous commit, use `git checkout <commit-hash>`. If you're unsure of the commit hash, run `git log` to list recent commits. You only need the first 7 characters of the hash.

```
> git checkout d819345
```

Doing this will put you in a **detached HEAD** state. This means HEAD is pointing to a specific commit rather than to the latest commit on a branch. In this state, you're free to explore or make experimental changes without affecting the branch history. Any commits you make here won't affect the branch, and you can return to a branch to exit this state.
When you check out an older commit, Git also shows only the commit history up to that commit, so you can review how the project looked at that point in time.

### What exactly is deteched HEAD?

Typically, HEAD points to a **branch** reference rather than a particular commit. When you make a new commit, the branch pointer moves to reflect this new state, but HEAD remains attached to the branch reference itself. When you switch branches, HEAD updates to follow the reference of the branch you switched to.

When you check out an older commit, however, HEAD points directly to that commit instead of to a branch pointer. You can verify this by using `cat .git/HEAD`, which will show the commit hash.
Example:

```
> cat .git/HEAD
Example Output: 6da7cab4fcdd1ad8c2130359620ccd5f08285fce
```

This is what it means to be in a detached HEAD state.
If HEAD is pointing to a branch reference, then it would look something like:

```
> cat .git/HEAD
Example Output: ref: refs/heads/main
```

### Uses of the Detached HEAD

#### 1. Review past code.

In a detached HEAD state, you can explore the contents of a previous commit. Simply use the following command to navigate to an older commit:

```
> git checkout <commit-hash>
```

#### 2. Return to the latest codebase.

To return to the latest version of your project and **reattach HEAD** to the branch, switch back to your branch:

```
> git switch main
```

#### 3. Create a new branch and switch to it.

You can also make a new branch from the old commit, which reattaches HEAD to this new branch. This lets you make changes on the new branch without affecting the original.

```
> git checkout <commit-hash>
> git switch -c <feature-name>
```
