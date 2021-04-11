# How to apply a `.gitignore` file?

> What if you add `.gitignore` later and find that it does not apply to old files?

Ref: [stackoverflow](https://stackoverflow.com/questions/19663093/apply-gitignore-on-an-existing-repository-already-tracking-large-number-of-file)

1. First of all, **commit all pending changes.**

Then run this command:

```
git rm -r --cached .
```

This removes everything from the repository index, but keep it untouched _locally_.

2. Then run:

```
git add .
```

to add all files including the just created `.gitignore` file. This works because it's just like the first time we initiated a git repo and added a `.gitignore` file.

3. Then commit it:

```
git commit -m ".gitignore is now working"
```

4. Push
