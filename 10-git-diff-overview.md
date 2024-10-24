# Comparisons with Git Diff

`Git diff` is a command used to show the differences between various states of your repository. It compares changes in your working directory, the staging area, or between specific commits. This command helps you understand exactly what has been modified before committing changinges, during code reviews, or when troubleshooting merge conflicts. We often use `git diff` alongside commands like `git status` and `git log` to get a better picture of a repository and how it has changed over time.

## How to Read a `git diff` Output

When you run the `git diff` command, Git generates an output that shows the differences between two versions of your files. Below is a guide to how to interpret the output of `git diff`.

### Basic Structure of `git diff` Output

When `git diff` compares two versions of a file, it uses the following symbols and format to display the changes:

- Minus Sign (-): Indicates lines that were only in the old version of file.
- Plus Sign (+): Indicates lines that were only in the new version of file.
- Unchanged lines: Lines that haven't changed between versions are shown for context.

### Sample `git diff` Output

```
diff --git a/README.md b/README.md
index af42332..9463cc2 100644
--- a/README.md
+++ b/README.md
@@ -18,6 +18,7 @@ This repo exists solely for the purpose of me mastering Git like a pro.
Or at le
 - [x] More on Branching
 - [x] Merging Branches
 - [ ] Comparing Changes with Git Diff
+- [ ] Stashing

 ## How to Contribute

diff --git a/childhood-favorites.md b/childhood-favorites.md
index 8dc3c53..22e876c 100644
--- a/childhood-favorites.md
+++ b/childhood-favorites.md
@@ -9,4 +9,5 @@ How to Train Your Dragon 1&2
 Beauty and the Beast
 Shrek
 The Christmas Carol
-Pride and Prejudice
+Ten Things I Hate About You
+To All The Boys I've Loved
```

Let's break this down step by step.

#### Comparing Files

For each comparison, Git explains which files it is comparing. Usually, this is two versions of the same file. Git declares one file as `A` and the other as `B`

```
diff --git a/childhood-favorites.md b/childhood-favorites.md
```

#### File Metadata

This section contains file-specific metadata. The first two numbers are the commit hashes of the two files being compared. The last number is an internal file mode identifier.

```
index 8dc3c53..22e876c 100644
```

#### File Markers

The files being compared are assigned symbols:

- File A gets a minus sign (-)
- File B gets a plus sign (+)

```
--- a/README.md
+++ b/README.md
```

In the case above, `--- a/README.md` refers to file A (the original version). `+++ b/README.md` refers to file B (the new version).

#### Chunks of Changes

Instead of showing the entire file, `git diff` only shows the portions or "chunks" that were modified. A chunk also includes some unchanges lines before and after a change to provide some context.

#### Chunk Header

Each chunk starts with a chunk header, found between @@ and @@, and shows where the changes are located in the file.

```
@@ -18,6 +18,7 @@
```

- `-18, 6`: Shows that the changes occur starting from line 18 in file A, and affect 6 lines.
- `+18, 7`: Shows that the changes occur starting from line 18 in file B, and affects 7 lines.

You can separate each chunk by its header.

#### The Actual Changes

Each line that differs between the two files is marked with either a `+` or `-` symbol. Lines prefixed with `-` come from file A. Lines that begin with `+` come from file B.

```
 - [x] More on Branching
 - [x] Merging Branches
 - [ ] Comparing Changes with Git Diff
+- [ ] Stashing
```

The `+-` in the context above indicates that the line was modified in both files A and B. Let's take a look at another example:

```
 Beauty and the Beast
 Shrek
 The Christmas Carol
-Pride and Prejudice
+Ten Things I Hate About You
+To All The Boys I've Loved
```

In the context above, the line `-Pride and Prejudice` come from File A (indicated by minus sign) but is not in File B . The lines that begin with `+` come from File B but are not in File A. The lines with no signs indicate they exist on both files, also called **context lines**.

**Note:** Usually, Git selects File A to represent the older version of the file and B for the newer version, but **that is not always the case**.

### Special Cases

#### New Files

When a new file is added, the output looks like this:

```
new file mode 100644
index 0000000..b5fc6a2
--- /dev/null
+++ b/newfile.js
@@ -0,0 +1,5 @@
+console.log("This is a new file");
```

- `new file mode 100644`: Indicates that this is a new file with standard file permissions.
- `--- /dev/null`: The new file doesn't exist in File A
- `+++ b/newfile.js` : The new file exists in File B.

#### Deleted Files

When a file is deleted, the diff output looks like this:

```
deleted file mode 100644
index b5fc6a2..0000000
--- a/oldfile.js
+++ /dev/null
```

- `deleted file mode 100644`: Indicates that the file has been removed.
- `+++ /dev/null`: Shows that the file does not exist in the new version.
