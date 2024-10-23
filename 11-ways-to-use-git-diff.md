# Ways to Use Git Diff

## How `git diff` Works

The `git diff` command compares changes in files across different Git "stages". There are three main areas Git tracks:

1. **Working Directory**: Your current uncommitted changes.
2. **Staging Area**: Changes that have been added using `git add` but not yet committed.
3. **Repository**: The latest committed version of your files.

## Common Uses of `git diff`

### `git diff`

Without additional options, `git diff` lists all the changes in our working directory that are **NOT staged for the next commit**.

### `git diff HEAD`

`git diff HEAD` lists ALL changes in the working tree since your last commit.

**NOTE**: It's easy to confuse `git diff` and `git diff HEAD`. Remember that git diff shows the unstaged changes, while git diff HEAD shows all the changes (both staged and unchanged) in the working directory since HEAD.

### `git diff --staged` & `git diff --cached`

`git diff --staged` or `git diff --cached` will list the changes between the staging area and our last commit. "Show me what will be included in my commit if I run git commit right now".

## Diff-ing Specific Files

### Comparing Files

We can view the changes within a specific file by providing a git diff along with some filename(s).

```
> git diff HEAD [filename]
> git diff --staged [filename]
> git diff HEAD [filename1] [filename1]
```

Example:

```
> git diff HEAD los-angeles-places.md
```

### Comparing Branches

`git diff branch1...branch2` will list the changes between the tips of branch1 and branch2.

```
> git diff branch1...branch2
```
