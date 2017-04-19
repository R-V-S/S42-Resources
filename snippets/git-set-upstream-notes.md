# In git, what's the `--set-upstream` or `-u` option for?

When you push up from a branch, git doesn't automatically make the assumption that the remote is the one named "origin", or that the remote branch has the same name on the remote that it does on your local. That's why you have to specify the remote and the remote branch name when pushing via `git push <remote> <branch-name>`, e.g. `git push origin master`.

Set upstream tells git to remember your setting for the current branch, so that after you've set the upstream, you can simply type `git push`, and git will know which remote and what remote branch name to push to.

