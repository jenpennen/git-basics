# Lecture 0:  Git Basics

## What is a Git Repo?
A Git "Repo" is a workspace which * tracks and manages files within a folder* . Anytime we want to use Git with a project, app, etc, we need to create a new git repository. We can have as many repos on our machine as needed, all with separate histories and contents.

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

Work on stuff - Make new files, edits files, delete files, etc
Add changes - Group specific changes together, in prep of committing
Commit - Commit everything that was previously added

## git add


