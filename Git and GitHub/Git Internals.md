Git is fundamentally a **content-addressable** filesystem with a VCS user interface written on top of it.

But because Git was initially a toolkit for a version control system rather than a full user-friendly VCS, it has a number of subcommands that do low-level work and were designed to be chained together UNIX-style or called from scripts.

When you run `git init` in a new or existing directory, Git creates the .git directory, which is where almost everything that Git stores and manipulates is located.

The files which are in `.git` file can show as following:
```bash
$ cd .git
$ ls -F1
HEAD
config
description
hooks/
info/
objects/
refs/
```

The `objects` directory stores all the content for your database.
The `refs` directory stores pointers into commit objects in that data (branches, tags, remotes and more).
The `HEAD` **file** points to the branch **you currently have checked out**.
The `index` file is where Git stores your staging area information.

