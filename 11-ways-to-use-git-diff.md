# Ways to Use Git Diff

## How `git diff` Works

The `git diff` command compares changes in files across different Git "stages". There are three main areas Git tracks:

1. **Working Directory**: Your current uncommitted changes.
2. **Staging Area**: Changes that have been added using `git add` but not yet committed.
3. **Repository**: The latest committed version of your files.

## Common Uses of `git diff`

### `git diff`

Running `git diff` by itself lists all the changes in your working directory that are **NOT staged for the next commit**.

### `git diff HEAD`

`git diff HEAD` lists **all changes**, both staged and unstaged, in the working tree since your last commit.

**Reminder**: `git diff` only shows unstaged changes, while `git diff HEAD` shoes everything (both staged and unstaged) since the last commit (HEAD)

### `git diff --staged` & `git diff --cached`

`git diff --staged` or `git diff --cached` lists the differences between the staged changes and your last commit. Essentially, the answer the question: "What will be committed if I run `git commit` now?"

## Diff-ing Specific Files

### File Comparisons

We can view the changes within a specific file (or files) by providing a git diff along with the filename(s).

```
> git diff HEAD [filename]
> git diff --staged [filename]
> git diff HEAD [filename1] [filename1]
> git diff --staged [filename1] [filename2]
```

Example:

```
> git diff HEAD los-angeles-places.md
```

### Comparing Branches

`git diff branch1...branch2` will show the differences between the latest commits on both branches.

```
> git diff branch1..branch2
```

Example:

```
> git diff main..songs
```

You will probably see changes across multiple files.

### Comparing Commits

To compare changes between two commits, provide git diff with the commit hashes.

```
> git diff <commit1>..<commit2>
```

Example:

```
> git diff 56f5b94..bd83dc1
```

You can get the commit hashes using `git log`.
**Note**: The order of files, branches, or commits in the `git diff` command matters, since it determines the direction of the comparison.
