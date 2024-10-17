# Advice on Commits

## Keep commits atomic.

When possible, a commit should contain a single feature, change or fix. **Don't try to keep each commit focused on a single thing**
This makes it much easier to undo or rollback on changes later on, and also easier to review.

## Use Present tense imperative style commit messages (according to git docs)

Examples:

```
- make xyz do something
- change xyz to do something
```

I don't do this. And most people I know don't either. Most people I know, myself included, prefer to use past tense.

Examples:

```
- changed xyz on/to [thing/action]
- resolved zyx on/to [thing/action]
```

Personally, this makes the most sense, since you make a commit with the work you've already modified.

_BUT_
Git uses the same imperative style and it shows when you do merges with commit messages: `Merge pull request`
It tells someone what applying that commit will do, so it reads something like: `"If I apply this commit, it will [make xyz do something]"` But again, using present tense, imperative isn't mandatory. Just keep the messages consistent with whatever style you prefer or what the org/project you work for prefers.
