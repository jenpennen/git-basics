# Lecture 0: Git Basics

## What is Git?

A (very popular) version control system (vcs).

## What's a Version Control System?

Version control is software that tracks and manages changes to files over time. It's a fundamental tool we need to revisit earlier versions of the files, compare changes between versions, undo changes, and a lot mmore.

Git is just one of _many_ vcs available. Others include Subversion, CVS, and Mercurial, but Git is the most popular. Honestly, I don't know anyone as of 2023 using the other version control systems I mentioned.

## What is a Git Repo?

A Git "Repo" is a workspace which _ tracks and manages files within a folder_ . Anytime we want to use Git with a project, app, etc, we need to create a new git repository. We can have as many repos on our machine as needed, all with separate histories and contents.

I like to think of git as checkpoints. You work on some project and make gradual changes on it.

# Some git commands

You''' use this everywhere. Don't forget it, but there won't be any forgetting bc you store all your projects in git anyway. Just in case tho...

## git status

gives information on the current status of a git repository and its contents.

## git init

used to create a git repository. Before doing anything git-related, we must initialize a repo first. This is only done ONCE per project. Initialize the repo in the top-level folder containing your project.

Creates an empty git repository, or a .gt directory with subdirectories for objects, refs/heads, refs/tags, and template files files. They're hidden so you don't mess around with it. You can use the following command to see the .git directory

```
ls -a
```

### Git tracks a directory and all its nested directories

We dont want to intialize a repo inside another repo!!

### A commit is essentially a checkpoint in time of something you work on

## The Basic Git Workflow

- Work on stuff - Make new files, edits files, delete files, etc
- Add changes - Group specific changes together, in prep of committing
- Commit - Commit everything that was previously added

## git add
