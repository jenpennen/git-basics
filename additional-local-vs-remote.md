# Local vs Remote in Git

In Git, the terms **local** and **remote** refer to different environments for managing repositories, branches, and commits.

- **Local** environments are **isolated and exist on your personal machine**.

- **Remote** environments are **hosted on a server and are shared among multiple collaborators/contributors**. It's great for working on projects with other people and also for storing your own work.

Let's go deeper into each one.

## Local vs Remote Repository

### Local Repository

A **local repository** exists on your personal computer. It contains the **complete history of the project, including all branches and commits**. You can freely create, modify, and delete branches, make commits, and test changes without affecting anyone else.

If you're working on a local repository, you will probably using commands like `git add`, `git commit` and `git branch` pretty often.

### Remote Repository

A **remote repository** is hosted on a server (e.g. Github, GitLab, Butbucket) and is accessible over the internet. It acts as a shared source for collaboration.

**Changes made in local repositories can be pushed to the remote repository**, allowing multiple contributors to collaborate. **It holds the collective history of a project as it is shared among collaborators**.

You will probably be using commands like `git push`, `git pull`, and `git fetch` pretty often when working with remote repositories.

## Local vs Remote Branch

### Local Branch

A **local branch** exists within your local repository. It represents the current state of your work and is **isolated from others until you choose to share it**. Local branches can be created and modified freely. They are typically used for feature development, bug fixes, or experimentation.

### Remote Branch

A **remote branch** refers to a branch in a remote repository. It shows the last known state of the branch based on your last fetch or pull. **Remote branches are read-only from your local repository and are updated when you fetch or pull from the remote**. They serve as a reference for the state of branches in shared repositories.

That said, you will probably use commands like `git fetch`, `git pull`, and `git push`.

## Local vs Remote Commit

### Local Commit

A **local commit** is a snapshot of your changes saved in your local repository. **It is not yet shared with others until pushed to a remote repository**. Local commits allow you to save your progress incrementally and experiment without affecting the shared project. You commit changes using the command `git commit -m "your commit message"`

### Remote Commit

A **remote commit** is a commit that exists in the remote repository. It is **the result of pushing one or more local commits to the remote branch**. Remote commits are visible to all collaborators and form part of the shared project history.

That said, you need to `git push` your commits to the remote repository for others to see it.
