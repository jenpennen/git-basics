# More about Commits

## git log

Shows the commit logs. There's a lot you can do with git log, check the git docs about log to see for yourself. The one I use most is:

```
> git log --oneline
```

You can use the command above to get a shorter commit hash and a one line description of the commit you made.

## Amending Commits

If you made a commit and then relaized you forgot to include a file or made a typo in the commit message, and you want to correct it, you can "redo" the previous commit using the --amend option.

```
> git commit -m "some commit"
> git add forgotten_file
> git commit --amend
```
