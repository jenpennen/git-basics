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

`git diff HEAD` lists all changes in the working tree since your last commit.
