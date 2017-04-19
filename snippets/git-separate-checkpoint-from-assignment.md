>Question: I accidentally didn't create an assignment branch until after finishing the assignment.

>  In this scenario, what would be the best way to seperate the checkpoint branch and the assignment/feature branch?

>  How would you save the completed code (including assignment) to a new branch, then delete the newest added assignment code/feature so you could save the first bit of changes to the checkpoint branch?


You can checkout individual commits by copying and pasting the commit hash, and then branch off of that. So: 

First, save your branch as the assignment branch, if you haven't already done so:

```
git checkout -b <assignment-branch-name>
```

You should now have two branches that are exactly the same. You can delete the checkpoint branch:

```
git branch -D <checkpoint-branch-name>
```

Now, you want to find the commit that you want to branch off from:

```
git log
```

Find that last commit that you want to keep and copy its hash. Then:

```
git checkout <hash>
```

For example: 

```
git checkout baaa18fad44d74d5d48cc2b05561841bd43d080c
```

Then:

```
git checkout -b <checkpoint-branch-name>
```

And that's it. You should now have proper checkpoint and assignment branches.