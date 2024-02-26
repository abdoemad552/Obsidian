Dealing with remotes in Git involves interacting with repositories hosted on remote servers or on the same device but in different directory.

**Remote Repository**: A remote repository is a repository hosted on a server, typically accessed over a network. Examples include GitHub, GitLab, Bitbucket, or a repository hosted on another server.

A remote repository **can technically be located on the same machine** as the local repository, although it's less common than hosting the remote repository on a separate server. Hosting a remote repository on the same machine is often done for development or testing purposes, especially in scenarios where you want to simulate a distributed environment locally.

To set up a remote repository on the same local machine, you would typically use a **file system path** instead of a URL to reference the remote repository.

By setting up a remote repository on the same local machine, you can still benefit from Git's distributed version control features, such as:
* Collaboration,
* Version tracking
* Branching
but without the overhead of network operations.

To clone a repository we use `git clone` command.

To clone a repository which exists in your local device, we use the following:
```bash
$ git clone <repo-directory> [<new-name>]
```

This clones this remote repo into the current directory.
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 /c/git
$ git clone C:/git/remote-repo/ local-repo
Cloning into 'local-repo'...
done.
```

In the above code, I created a remote repo which is called `remote-repo` and created a file in it. Then I cloned that repo with a new name called `local-repo`.

To show all remotes that you have cloned, we use `git remote` command.
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/local-repo (master)
$ git remote
origin
```

`origin` is a short name for that remote repo that we have just cloned. To show more details about that remote repo, we use `git remote -v`.
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/local-repo (master)
$ git remote -v
origin  C:/git/remote-repo/ (fetch)
origin  C:/git/remote-repo/ (push)
```

These two lines shows that we can both fetch from and push to that remote. Some remotes allow only fetching which results only in one line.

