# Commit Advice

## Keep commits atomic.

Whenever possible, make sure each commit addresses a single feature, change, or fix. **Avoid bundling multiple changes into one commit.** This approach simplifies reversing or undoing changes later and makes code reviews easier.

## Use Present tense imperative style commit messages (according to git docs)

Examples:

```
- make xyz do something
- change xyz to do something
```

However, I don't personally follow this, and neither do many people I know. Most of us prefer using past tense for commit messages.

Examples:

```
- changed xyz on/to [thing/action]
- resolved zyx on/to [thing/action]
```

This feels more natural since you're committing work that's already been completed.

_BUT_
Git defaults to the imperative style, which becomes noticeavle in merge commit messages like `Merge pull request`. It indicates what will happen when the commit is applied, reading something like: `"If I apply this commit, it will [make xyz do something]`.

That said, using the imperative form isn't a requirement. Just keep your commit messages consistent, either with your own style or the standards of the organization or project you're working on.
