# More about Commits

## git log

`git log` shows the commit logs. There's a lot you can do with git log, check the git docs about log to see for yourself. The one I use most is:

```
> git log --oneline
```

You can use the command above to get a shorter commit hash and a one line description of the commit you made.

## Amending Commits

If you made a commit and then realized you forgot to include a file or made a typo in the commit message, and you want to correct it, you can "redo" the previous commit using the --amend option.

**Note:** You can only amend a commit right after you've made the commit. You cannot amend a commit if you pushed the commit you want to amend!

```
> git commit -m "some commit"
> git add forgotten_file
> git commit --amend
```

The nasty part about following the exact steps above is you'll be taken to a new text editor where you can rewrite your commit message.
If you don't want to modify your commit message but you're stuck on that editor, just use the follow command to quit:

```
:wq
```

Or if you read up to this point (yay :D), you can write your new commit message inline using the following `git --amend` command:

```
> git commit --amend -m "did something new"
```

OR let's say you don't want to change the commit message but want to include a new file. You can add the new file and use the following `git --amend` command to not change the commit message:

```
> git commit -m "in this commit you forgot to stage a file"
> git add forgotten_file
> git commit --amend --no-edit
```
