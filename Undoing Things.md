# Using amend

One of the most common undo takes place when you commit some too early and possibly **forgot to add some files** or you mess up your commit message.

If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the `--amend` option:
```bash
$ git commit --amend
```

The same commit-message editor fires up, but it already contains the message of your previous commit. You can edit the message the same as always, but it overwrites your previous commit. You can also use the following format if you don't want to use the editor:
```bash
$ git commit --amend -m "Amend Message"
```

# Using reset

Let’s say you’ve changed two files and want to commit them as two separate changes, but you accidentally type `git add *` and stage them both. How can you un-stage one of the two?

For this purpose we can use `reset` as following:
```bash
$ git reset HEAD <file-you-want-to-unstage>
```

The file **status** backs to the status it was at after the last commit (Changes not staged for commit or Untracked file).

Un-staging means it removes the file from staging area without making changes to the original file.

# Un-modifying a Modified File

If you staged some files and then made some changes to some files and you want to undo these changes. In other words you want to make the files as it was since the last commit.

For this purpose we can use the following command:
```bash
$ git checkout -- <file-name>
```

This command discards the changes that you make in `<file>` since the last commit (Changes it with the version in **staging area** or to the version in the last commit if you haven't staged the new changes).

It’s important to understand that git checkout `-- <file>` is a dangerous command. Any local changes you made to that file are gone — Git just replaced that file with the last staged or committed version. Don’t ever use this command unless you absolutely know that you don’t want those unsaved local changes.

# Undoing things with git restore

Git version 2.23.0 introduced a new command: `git restore`. It’s basically an alternative to `git reset` which we just covered. From Git version 2.23.0 onwards, Git will use `git restore` instead of `git reset` for many undo operations.

## Un-staging a Staged File with git restore

To un-stage a file, we use the following command:
```bash
$ git restore --staged <file>
```

## Un-modifying a Modified File with git restore

To un-modify a modified file, we use the following command:
```bash
$ git restore <file>
```

We can notice that `git rest HEAD <file>` is similar to `git restore --staged <file>` and `git checkout -- <file>` is similar to `git restore <file>`.

***
**What is the difference between** `git restore --staged <file>` **and** `git rm --cached <file>`**?**

`git restore --staged <file>` and `git rm --cached <file>` are both commands used in Git to manipulate changes and staging area, but they serve different purposes:

1. **`git restore --staged <file>`**:
    
    - This command is used to un-stage changes that have been previously staged using `git add`.
    - It moves changes from the staging area (index) back to the working directory, effectively "un-staging" them.
    - It does not affect the changes made to the file in the working directory; it only removes them from the staging area.
    - The changes remain in the working directory, allowing you to continue modifying them or discard them entirely.
2. **`git rm --cached <file>`**:
    
    - This command is used to remove a file from the staging area (index) while preserving it in the working directory.
    - It removes the specified file from the staging area, but the file itself remains in the working directory.
    - It's typically used when you've accidentally added a file to the staging area that you don't want to commit yet, or if you want to stop tracking a file without deleting it from your file system.
    - After using this command, the file will be untracked (not included in the next commit), but it will remain in your working directory so that you can continue working on it.

In summary, `git restore --staged <file>` is used to un-stage changes from the staging area, while `git rm --cached <file>` is used to remove a file from the staging area without affecting the working directory.

