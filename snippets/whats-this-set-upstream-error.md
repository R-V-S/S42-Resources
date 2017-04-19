# What's with this message I keep getting about setting an upstream?

Yeah, this is a pretty common issue of confusion among students.

The upstream error means that git doesn't know which remote branch it's supposed to push to. It doesn't assume that the remote branch and the local branch are going to have the same name (even though that's what we want 99.9% of the time). 

Use the command:

```
git push -u origin name-of-current-branch
```

So if you're on master:

```
git push -u origin master
```

If you're on a branch named `cp-2`:

```
git push -u origin cp-2
```

The `-u` is short for `--set-upstream`.

You only have to set your upstream **once per branch**, so the next time you want to push from that branch, you can just run `git push`.

Also, if you're having trouble with a git command, `git help` is always there. The format is:

```
git help name-of-command
```

Try `git help push`, for example.
