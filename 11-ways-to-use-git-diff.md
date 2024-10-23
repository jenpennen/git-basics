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

We can view the changes within a specific file by providing a git diff with a filename.

```
> git diff HEAD [filename]
> git diff --staged [filename]
```
