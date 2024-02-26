Branching is the process of working on multiple thing at the same time and independently.

**HEAD branch**: is the currently active or checked out branch.

To create a new branch:
```bash
$ git branch <new-branch-name>
```

The new branch is created on the current revision.

If we want to create the branch on a specific revision,  we can add sha1 hash of that revision next to the branch name:
```bash
$ git branch <new-branch-name> <revision-hash>
```

To switch the current we use either of the following:
```bash
$ git switch <branch-name>
$ git checkout <branch-name>
```

A branch in Git is actually **a simple file that contains the 40 character SHA-1 checksum of the commit it points to**, branches are cheap to create and destroy. Creating a new branch is as quick and simple as writing 41 bytes to a file (40 characters and a newline).

To create new branch and switch to it at the same time:
```bash
$ git checkout -b <new-branch-name>
$ git switch -c <new-branch-name>
$ git switch --create <new-branch-name>
```

If your working directory or staging area has uncommitted changes that conflict with the branch you’re checking out, Git won’t let you switch branches.

Merging a branch to another branch is basically taking the changes from the two branches and combining them together in a new commit.

When you merge you merge two branches together, the result will go on the branch that you currently working on.

In case you created a branch and and performed some commits on that branch while the master branch has no new commits and then you want to merge that branch into the maser branch. In this case the branch will be merged with the master branch as if it was part of it. No new commits are created.

In this case, the master branch pointer is simply moved forward because there is no divergent work to merge together. This is called **fast-forward**.

To merge some branch into the current branch, we use the following command:
```bash
$ git merge <other-branch>
$ git merge <other-branch> -m "Merge commit message"
```

To delete a branch:
```bash
$ git branch -d <branch-name>
```

Now assume that you diverged your master branch from the other branch by creating new changes and then commit them. Now you have something called divergent history. Your development history ***has diverged from some older point***. 

Because the commit on the branch you’re on ***isn’t a direct ancestor*** of the branch you’re merging in, Git has to do some work. Instead of just moving the branch pointer forward (not a proper action), Git creates a new snapshot that results from this ***three-way merge*** and automatically creates a new commit that points to it. This is referred to as a merge commit, and is special in that it has more than one parent.

If you changed the same part of the same file differently in the two branches you’re merging, Git won’t be able to merge them cleanly. This is called **Merge conflict**.

If you want to see the file that has merge conflicts in it, we can use `git status` command.
Anything that has merge conflicts and hasn’t been resolved is listed as unmerged. Git adds standard conflict-resolution markers to the files that have conflicts, so you can open them manually and resolve those conflicts.

```
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
please contact us at support@github.com
</div>
>>>>>>> iss53:index.html
```

After you’ve resolved each of these sections in each conflicted file, run git add on each file to mark it as resolved. **Staging the file marks it as resolved in Git**.

After that you can commit these changes. This commit is considered to be the merge commit.

If you faced a merge conflict and you want to abort that merge, then you can use the following command:
```bash
$ git merge --abort
```

To see the last commit on each branch:
```bash
$ git branch -v
```

To show the branches that have been merged with the current branch:
```bash
$ git branch --merged
```

The output of this command is a list of branch names including the current branch. All branches except the current branch are safe to be deleted using `git branch -d <branch-name>`.

If you want to list branches that haven't been merged yet:
```bash
$ git branch --no-merged
```

You can always provide an additional argument to ask about the merge state with respect to some other branch without checking that other branch out first:
```bash
$ git branch --merged <branch-name>
$ git branch --no-merged <branch-name>
```

Deleting a branch that hasn't been merged yet can't be done using `git branch -d <branch-name>`. In order to enforce deletion of this branch:
```bash
$ git branch -D <branch-name>
```

To change the name of the current branch we can use the following command:
```bash
$ git branch -m <new-name>
$ git branch --move <new-name>
```

To change the name of a specific branch:
```bash
$ git branch -m <old-name> <new-name>
$ git branch --move <old-name> <new-name>
```

To show the current branches we use:
```bash
$ git branch
```

Changing the name of the branch in the local repo needed to pushed into the remote repo:
```bash
$ git push --set-upstream origin
```

To remove any remote tracking references from the local repo:
```bash
$ git fetch --prune
```

To show all branches (Local and Remote):
```bash
$ git branch -a
$ git branch --all
```

With the `rebase` command, you can take all the changes that were committed on one branch and replay them on a different branch.

To rebase a branch into the master branch (or any other branch), first we checkout the branch that we want to rebase it. Then, we rebase that branch into the master branch:
```bash
$ git checkout <branch>
$ git rebase master
```

This operation works by going to the common ancestor of the two branches (the one you’re on and
the one you’re rebasing onto), getting the diff introduced by each commit of the branch you’re on,
saving those diffs to temporary files, resetting the current branch to the same commit as the branch
you are rebasing onto, and finally applying each change in turn.

After rebasing, we switch back to the master branch and merge these two branches (fast forward).

The last commit after this rebasing process will be exactly the same as the merge commit resulted from using `merge`.

