Here's my method for removing an unwanted commit from a branch that's already been pushed:

0. Checkout the last commit that you want to keep (the commit before the offending commit)
0. Create a new temp branch off of that commit
0. [Cherry-pick](https://git-scm.com/docs/git-cherry-pick) any commits that are after the offending commit that you want to keep
0. Delete the original branch
0. Create a new branch with the original branch name.
Delete the temp branch. Now everything should be how you want it to be on your local.
0. Push up your cleaned up branch with `git push -fu origin <branch-name>`. This should overwrite your remote branch so that it no longer has the offending commit, and it will also set your upstream.