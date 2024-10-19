# Git Basics

## What is Git?

A (very popular) version control system (vcs).

## What's a Version Control System?

Version control is a type of software that monitors and manages changes to files over time. It's an essential tool that allows us to revert to previous versions, compare differences between versions, undo modifications, and much more.

Git is just one of _many_ version control systems (VCS) available. Others include Subversion, CVS, and Mercurial, though Git is by far the most widely used. To be honest, I don't know anyone still using the other systems as of 2023.

## What is a Git Repo?

A Git "repository" (or repo for short) is a workspace that tracks and manages files within a folder. Whenever we want to use Git for a project, app, or similar, we need to create a new Git repository. You can have as many repos as needed on your machine, each with its own history and content.

I like to think of Git as a system of checkpoints. As you work on a project, you make gradual changes, and Git helps track those changes step by step.

# Some git commands

You'll be using this constantly, so it's important to remember. But don't worry -- you probably won't forget, since all your projects will be stored in Git anyway. Just in case, though...

## git status

`git status` provides information about the current state of a Git repository and its contents. It shows any changes made to files, whether they have been stages for commit, or if there are any untracked files.

## git init

`git init` is used to create a new Git repository. Before working with Git on a project, you must initialize the repository, which only needs to be done once per project. It's typically intialized in the top level folder of your project.

This command creates an empty Git repository, including a hidden `.git` directory with subdirectories for objects, refs/heads, refs/tags, and template files. To view the `.git` directory, since it's hidden, you can use the following command:

```
ls -a
```

### Git tracks a directory and all its nested directories

It's important not to initialize a Git repository inside an existing one! Before running `git init`, use `git status` to verify that you are not currently inside a Git repo.

_If_ you accidentally initialize a repository within another, you can remove it by deleting the corresponding `.git` folder. Here's how you can do it:

```
 > ls -a # List all files, including hidden ones
 > # Output will show: . .. .git
 > rm -rf .git # Remove the .git folder to delete the repository
```

## The Basic Git Workflow

1. **Work on your project** - create new files, modify existing ones, or delete files as needed.
2. **Stage your changes** - Group the specific changes you want to commit by adding them to the staging area.
3. **Commit your changes** - Commit all the staged changes as a snapshot of your work.

## git add

Use `git add` to add specific files to the staging area in preparating for committing. You can add multiple files at once by separating them with spaces.

```
> git add file1 file2 file3
```

To stage all changes at once, use:

```
> git add .
```

## git commit

**A commit is essentially a checkpoint in the progress of something you're working on**

After staging, use the `git commit` command to save your changes to the repository. Each commit requires a message to summarize the changes:

```
> git commit -m "your commit message here"
```

The `-m` flag allows you to include the commit message directly without opening a text editor.

You can also just type `git commit`, which will commit all staged changes and open a text editory to write your message. However, using the `-m` flag to write the message inline is quicker and more convenient in most cases.
