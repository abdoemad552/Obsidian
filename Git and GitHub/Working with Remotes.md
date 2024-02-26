**Remote repositories** are _versions of your project_ that are hosted on the Internet or network somewhere. You can have several of them, each of which generally is either **read-only** or **read/write** for you.

Managing remote repositories includes knowing **how to add remote repositories**, **remove remotes that are no longer valid**, **manage various remote branches** and define them as being tracked or not, and more.

Remote repositories can be on your local machine. It is entirely possible that you can be working with a “remote” repository that is, in fact, on the same host you are. The word “remote” does not necessarily imply that
the repository is somewhere else on the network or Internet, only that it is elsewhere. Working with such a remote repository would still involve all the standard pushing, pulling and fetching operations as with any other remote.

In dealing with remotes, we usually use `git remote` command.

To clone a remote repo in your machine, we use the following command:
```bash
$ git clone <remote-repo-url-or-path> <local-repo-name>
```

In case you remote repo is in your local machine, you should provide its **path information**. In case it is on the network, you should provide its **URL**.

If you didn't provide a name, the cloned repo's name will the same as remote repo's name.

To show the remotes that you are dealing with, we use the following command:
```bash
$ git remote
```

This command lists the remotes that you are dealing with.

To show more details about the remotes such as their URL and the ability to push and pull, we use the following command:
```bash
$ git remote -v
```

To show the branches that are in the remote repository we use the following command:
```bash
$ git branch -r
```

```bash
abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/local-repo (master)
$ git branch -r
  origin/HEAD -> origin/master
  origin/master
```

The above result shows us that the remote repo has only the master branch and the head is pointing at the master branch.

`git fetch` is a command used in the Git version control system **to retrieve updates from a remote repository without merging them into your local branch**. When you run `git fetch`, Git contacts the remote repository specified (usually, the origin remote by default) and downloads any new branches or commits that exist there. However, it doesn't integrate these changes into your working branch.

`git clone` command **implicitly** adds the origin remote for you.

To add a new remote repository with a given name:
```bash
$ git remote add <remote-name> <remote-url>
```

This name can be used in lieu of the whole URL.
```bash
$ git remote add pb https://github.com/paulboone/ticgit
$ git fetch pb
```

To get data from your remote projects:
```bash
$ git fetch <remote>
```

The command goes out to that remote project and pulls down all the data from that remote project that you don’t have yet. After you do this, you should have references to all the branches from that remote, which you can merge in or inspect at any time.

`git fetch origin` fetches any new work that has been pushed to that server since you cloned (or last fetched from) it.

You can use the git pull command to automatically fetch and then merge that remote branch into your current branch.

When you have your project at a point that you want to share, you have to push it upstream. The command for this is simple:
```bash
$ git push <remote> <branch>
```

If you and someone else clone at the same time and they push upstream and then you push upstream, **your push will rightly be rejected**. You’ll have to fetch their work first and incorporate it into yours before you’ll be allowed to push.

If you want to see more information about a particular remote:
```bash
$ git remote show <remote>
```

To rename a remote's short name, we use `git remote rename <old> <new>`.
To remove a remote we use `git remote remove` or `git remote rm`.

To remove any remote tracking references from the local repo:
```bash
$ git fetch --prune
```

To show all branches (Local and Remote):
```bash
$ git branch -a
$ git branch --all
```

**Remote references** are references (pointers) in your remote repositories, including branches, tags, and so on.

To show the full list of remote references:
```bash
$ git ls-remote <remote>
$ git remote show <remote>
```

**Remote-tracking branches** are references to the state of remote branches.

Remote-tracking branch names take the form `<remote>/<branch>`.

If you have a branch and you want to add this branch to the remote repository:
```bash
$ git push <remote> <branch>
$ git push <remote> <local-name>:<remote-name>
```

Git automatically expands the `branch` branch name out to `refs/heads/<branch>:refs/heads/<branch>`, which means, “Take my `<branch>` local branch and push it to update the remote’s `<branch>` branch”.

when you do a fetch that brings down new remote-tracking branches, you don’t automatically have local, editable copies of them. You have only `origin/<branch>` pointer that you can't codify.

You can merge that branch using:
```bash
$ git merge <remote>/<branch>
```

Or if you don't want to merge it and want to do some work in it:
```bash
$ git checkout -b <branch> <remote>/<branch>
```

Or
```bash
$ git branch <branch> <remote>/<branch>
$ git switch <branch>
```

Or
```bash
$ git checkout --track <remote>/<branch>
```

Both of the above commands creates the branch and sets up tracking.

Checking out a **local branch** from a **remote-tracking** branch automatically creates what is called a “**tracking branch**” (and the branch it tracks is called an “**upstream branch**”).

When you clone a repository, it generally automatically creates a `master` branch that tracks `origin/master`.

If you want to see what tracking branches you have set up, you can use the -vv option to git branch.
This will list out your local branches with more information including what each branch is tracking
and if your local branch is ahead, behind or both.
```bash
$ git branch -vv
```

To delete a remote branch:
```bash
$ git push <remote> --delete <branch>
```

Basically all this does is to remove the pointer from the server.

When you type `git fetch` it fetches the changes in all branches.
If you want only to fetch changes from a specific branch you follow the known command.

