```bash
abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL
$ git init
Initialized empty Git repository in C:/git/GIT-TUTORIAL/.git/

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello

nothing added to commit but untracked files present (use "git add" to track)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -m "version1"
[master (root-commit) 08acfc7] version1
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "version2" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "version2" > hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "version1" > hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "version2" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -m "version2"
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   hello

no changes added to commit (use "git add" and/or "git commit -a")

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -am "version2"
[master 17e9d34] version2
 1 file changed, 2 insertions(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "version3" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -am "version3"
[master f55821f] version3
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --graph --all
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch feature1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --graph --all
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> master, feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git switch feature1
Switched to branch 'feature1'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git log --graph --all
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> feature1, master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git status
On branch feature1
nothing to commit, working tree clean

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git status
On branch feature1
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        feature

nothing added to commit but untracked files present (use "git add" to track)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git commit -m "feature commit"
[feature1 ec2c7f2] feature commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git log --graph --all
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61 (HEAD -> feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git status
On branch feature1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   feature

no changes added to commit (use "git add" and/or "git commit -a")

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git commit -am "feature second commit"
[feature1 7771666] feature second commit
 1 file changed, 2 insertions(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (HEAD -> feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git branch
* feature1
  master

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git switch master
Switched to branch 'master'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -m "bug fix"
[master 89a6281] bug fix
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 bugfix

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 89a62818236987df1a85c19b2e48c694de527529 (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:33:00 2024 +0200
|
|     bug fix
|
| * commit 7771666586b114857c307cb04947653e24fe53b4 (feature1)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:24:26 2024 +0200
| |
| |     feature second commit
| |
| * commit ec2c7f28d02356dcba7393d0d886f07911e05d61
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:22:37 2024 +0200
|
|       feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git reflog
89a6281 (HEAD -> master) HEAD@{0}: commit: bug fix
f55821f HEAD@{1}: checkout: moving from feature1 to master
7771666 (feature1) HEAD@{2}: commit: feature second commit
ec2c7f2 HEAD@{3}: commit: feature commit
f55821f HEAD@{4}: checkout: moving from master to feature1
f55821f HEAD@{5}: commit: version3
17e9d34 HEAD@{6}: commit: version2
08acfc7 HEAD@{7}: commit (initial): version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git reset --hard HEAD@{5}
HEAD is now at f55821f version3

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch b1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch b2

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> master, b2, b1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git rest --hard 777166
git: 'rest' is not a git command. See 'git --help'.

The most similar commands are
        restore
        reset

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git reset --hard 777166
HEAD is now at 7771666 feature second commit

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (HEAD -> master, feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (b2, b1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git reset --hard f55821
HEAD is now at f55821f version3

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (HEAD -> master, b2, b1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch
  b1
  b2
  feature1
* master

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git switch feature1
Switched to branch 'feature1'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git log --all --graph
* commit 7771666586b114857c307cb04947653e24fe53b4 (HEAD -> feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:24:26 2024 +0200
|
|     feature second commit
|
* commit ec2c7f28d02356dcba7393d0d886f07911e05d61
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:22:37 2024 +0200
|
|     feature commit
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (master, b2, b1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git ref log
git: 'ref' is not a git command. See 'git --help'.

The most similar commands are
        grep
        reflog

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git reflog
7771666 (HEAD -> feature1) HEAD@{0}: checkout: moving from master to feature1f55821f (master, b2, b1) HEAD@{1}: reset: moving to f55821
7771666 (HEAD -> feature1) HEAD@{2}: reset: moving to 777166
f55821f (master, b2, b1) HEAD@{3}: reset: moving to HEAD@{5}
89a6281 HEAD@{4}: commit: bug fix
f55821f (master, b2, b1) HEAD@{5}: checkout: moving from feature1 to master
7771666 (HEAD -> feature1) HEAD@{6}: commit: feature second commit
ec2c7f2 HEAD@{7}: commit: feature commit
f55821f (master, b2, b1) HEAD@{8}: checkout: moving from master to feature1
f55821f (master, b2, b1) HEAD@{9}: commit: version3
17e9d34 HEAD@{10}: commit: version2
08acfc7 HEAD@{11}: commit (initial): version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git reset --hard HEAD@{4}
HEAD is now at 89a6281 bug fix

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ git log --all --graph
* commit 89a62818236987df1a85c19b2e48c694de527529 (HEAD -> feature1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:33:00 2024 +0200
|
|     bug fix
|
* commit f55821f59c28d56f919f2d4f77b920cdc1bcfead (master, b2, b1)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:49 2024 +0200
|
|     version3
|
* commit 17e9d341a61e247ad7f4ef3eb7b50926505e4985
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:17:41 2024 +0200
|
|     version2
|
* commit 08acfc783177c8032eb9a73b88f3ad0c2fae5b43
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:15:54 2024 +0200

      version1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ rm -ar .git
rm: unknown option -- a
Try 'rm --help' for more information.

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ rm -h
rm: unknown option -- h
Try 'rm --help' for more information.

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ rm --help
Usage: rm [OPTION]... [FILE]...
Remove (unlink) the FILE(s).

  -f, --force           ignore nonexistent files and arguments, never prompt
  -i                    prompt before every removal
  -I                    prompt once before removing more than three files, or                          when removing recursively; less intrusive than -i,
                          while still giving protection against most mistakes      --interactive[=WHEN]  prompt according to WHEN: never, once (-I), or
                          always (-i); without WHEN, prompt always
      --one-file-system  when removing a hierarchy recursively, skip any
                          directory that is on a file system different from
                          that of the corresponding command line argument
      --no-preserve-root  do not treat '/' specially
      --preserve-root[=all]  do not remove '/' (default);
                              with 'all', reject any command line argument
                              on a separate device from its parent
  -r, -R, --recursive   remove directories and their contents recursively
  -d, --dir             remove empty directories
  -v, --verbose         explain what is being done
      --help     display this help and exit
      --version  output version information and exit

By default, rm does not remove directories.  Use the --recursive (-r or -R)
option to remove each listed directory, too, along with all of its contents.

To remove a file whose name starts with a '-', for example '-foo',
use one of these commands:
  rm -- -foo

  rm ./-foo

Note that if you use rm to remove a file, it might be possible to recover
some of its contents, given sufficient expertise and/or time.  For greater
assurance that the contents are truly unrecoverable, consider using shred.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/rm>
or available locally via: info '(coreutils) rm invocation'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ rm --help
Usage: rm [OPTION]... [FILE]...
Remove (unlink) the FILE(s).

  -f, --force           ignore nonexistent files and arguments, never prompt
  -i                    prompt before every removal
  -I                    prompt once before removing more than three files, or
                          when removing recursively; less intrusive than -i,
                          while still giving protection against most mistakes
      --interactive[=WHEN]  prompt according to WHEN: never, once (-I), or
                          always (-i); without WHEN, prompt always
      --one-file-system  when removing a hierarchy recursively, skip any
                          directory that is on a file system different from
                          that of the corresponding command line argument
      --no-preserve-root  do not treat '/' specially
      --preserve-root[=all]  do not remove '/' (default);
                              with 'all', reject any command line argument
                              on a separate device from its parent
  -r, -R, --recursive   remove directories and their contents recursively
  -d, --dir             remove empty directories
  -v, --verbose         explain what is being done
      --help     display this help and exit
      --version  output version information and exit

By default, rm does not remove directories.  Use the --recursive (-r or -R)
option to remove each listed directory, too, along with all of its contents.

To remove a file whose name starts with a '-', for example '-foo',
use one of these commands:
  rm -- -foo

  rm ./-foo

Note that if you use rm to remove a file, it might be possible to recover
some of its contents, given sufficient expertise and/or time.  For greater
assurance that the contents are truly unrecoverable, consider using shred.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/rm>
or available locally via: info '(coreutils) rm invocation'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature1)
$ rm -rf .git

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL
$ ls
bugfix  hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL
$ rm -rf hello bugfix

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL
$ ls

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL
$ git init
Initialized empty Git repository in C:/git/GIT-TUTORIAL/.git/

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "commit1" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -m "commit 1"
[master (root-commit) f15ffe1] commit 1
 1 file changed, 1 insertion(+)
 create mode 100644 hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "commit 2" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ cat hello
commit1
commit 2

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "commit1" > hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "commit2" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   hello

no changes added to commit (use "git add" and/or "git commit -a")

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -am "commit 2"
[master 20f8aeb] commit 2
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --oneline
20f8aeb (HEAD -> master) commit 2
f15ffe1 commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ echo "commit3" >> hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -am "commit 3"
[master e375222] commit 3
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923 (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch feature

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git switch feature
Switched to branch 'feature'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git switch master
Switched to branch 'master'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923 (HEAD -> master, feature)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git switch feature
Switched to branch 'feature'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git commit -m "feature commit 1"
[feature 31c97b4] feature commit 1
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git commit -am "feature commit 2"
On branch feature
nothing to commit, working tree clean

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git log --all --graph
* commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2 (HEAD -> feature)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:54:29 2024 +0200
|
|     feature commit 1
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923 (master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git commit -am "feature commit 2"
[feature 08d0315] feature commit 2
 1 file changed, 2 insertions(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git log --all --graph
* commit 08d03157c381fc8067d8cbcfee2637eeb2d07710 (HEAD -> feature)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:55:33 2024 +0200
|
|     feature commit 2
|
* commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:54:29 2024 +0200
|
|     feature commit 1
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923 (master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git switch master
Switched to branch 'master'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ ls -al
total 6
drwxr-xr-x 1 abdoe 197609  0 Feb  8 20:55 .
drwxr-xr-x 1 abdoe 197609  0 Feb  8 20:13 ..
drwxr-xr-x 1 abdoe 197609  0 Feb  8 20:55 .git
-rw-r--r-- 1 abdoe 197609  6 Feb  8 20:56 bugfix
-rw-r--r-- 1 abdoe 197609 24 Feb  8 20:52 hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ cat bugfix
bugfix
abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        bugfix

nothing added to commit but untracked files present (use "git add" to track)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -m "bug fix commit"
[master 235cc34] bug fix commit
 1 file changed, 1 insertion(+)
 create mode 100644 bugfix

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 235cc341ce6c8965e031e1def3f604fd473cc765 (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:56:58 2024 +0200
|
|     bug fix commit
|
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:54:29 2024 +0200
|
|       feature commit 1
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git switch feature
Switched to branch 'feature'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git log --all --graph
* commit 235cc341ce6c8965e031e1def3f604fd473cc765 (master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:56:58 2024 +0200
|
|     bug fix commit
|
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710 (HEAD -> feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:54:29 2024 +0200
|
|       feature commit 1
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ ls
feature  hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git commit -am "feature commit 3"
[feature f439028] feature commit 3
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git log --all --graph
* commit f439028e9889463a9de8482b23a89c502fe5fd6b (HEAD -> feature)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 21:09:27 2024 +0200
|
|     feature commit 3
|
* commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:55:33 2024 +0200
|
|     feature commit 2
|
* commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:54:29 2024 +0200
|
|     feature commit 1
|
| * commit 235cc341ce6c8965e031e1def3f604fd473cc765 (master)
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git amend
git: 'amend' is not a git command. See 'git --help'.

The most similar command is
        imap-send

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git amand
git: 'amand' is not a git command. See 'git --help'.

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git --help
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--config-env=<name>=<envvar>] <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect    Use binary search to find the commit that introduced a bug
   diff      Show changes between commits, commit and working tree, etc
   grep      Print lines matching a pattern
   log       Show commit logs
   show      Show various types of objects
   status    Show the working tree status

grow, mark and tweak your common history
   branch    List, create, or delete branches
   commit    Record changes to the repository
   merge     Join two or more development histories together
   rebase    Reapply commits on top of another base tip
   reset     Reset current HEAD to the specified state
   switch    Switch branches
   tag       Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch     Download objects and refs from another repository
   pull      Fetch from and integrate with another repository or a local branch
   push      Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
See 'git help git' for an overview of the system.

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git commit --amend
[feature 7cb75de] feature done
 Date: Thu Feb 8 21:09:27 2024 +0200
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git log --all --graph
* commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (HEAD -> feature)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 21:09:27 2024 +0200
|
|     feature done
|
* commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:55:33 2024 +0200
|
|     feature commit 2
|
* commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:54:29 2024 +0200
|
|     feature commit 1
|
| * commit 235cc341ce6c8965e031e1def3f604fd473cc765 (master)
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ ls
feature  hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ vim

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (feature)
$ git switch master
Switched to branch 'master'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 21:09:27 2024 +0200
|
|     feature done
|
* commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:55:33 2024 +0200
|
|     feature commit 2
|
* commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:54:29 2024 +0200
|
|     feature commit 1
|
| * commit 235cc341ce6c8965e031e1def3f604fd473cc765 (HEAD -> master)
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph --oneline
* 7cb75de (feature) feature done
* 08d0315 feature commit 2
* 31c97b4 feature commit 1
| * 235cc34 (HEAD -> master) bug fix commit
|/
* e375222 commit 3
* 20f8aeb commit 2
* f15ffe1 commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git merge feature -m "feature merge commit"
Merge made by the 'ort' strategy.
 feature | 3 +++
 1 file changed, 3 insertions(+)
 create mode 100644 feature

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ ls
bugfix  feature  hello

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph --oneline
*   12226f0 (HEAD -> master) feature merge commit
|\
| * 7cb75de (feature) feature done
| * 08d0315 feature commit 2
| * 31c97b4 feature commit 1
* | 235cc34 bug fix commit
|/
* e375222 commit 3
* 20f8aeb commit 2
* f15ffe1 commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
*   commit 12226f07e576acee3708aa31e2219a9e91513108 (HEAD -> master)
|\  Merge: 235cc34 7cb75de
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:21:32 2024 +0200
| |
| |     feature merge commit
| |
| * commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:09:27 2024 +0200
| |
| |     feature done
| |
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:54:29 2024 +0200
| |
| |     feature commit 1
| |
* | commit 235cc341ce6c8965e031e1def3f604fd473cc765
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch conflict

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git branch
  conflict
  feature
* master

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git switch conflict
Switched to branch 'conflict'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (conflict)
$ git add .

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (conflict)
$ git commit -m "conflict 1 commit"
[conflict 585f6b4] conflict 1 commit
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (conflict)
$ git log --all --graph
* commit 585f6b4bb0b703c24ffbe76ad4f5658da6464bda (HEAD -> conflict)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 22:16:29 2024 +0200
|
|     conflict 1 commit
|
*   commit 12226f07e576acee3708aa31e2219a9e91513108 (master)
|\  Merge: 235cc34 7cb75de
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:21:32 2024 +0200
| |
| |     feature merge commit
| |
| * commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:09:27 2024 +0200
| |
| |     feature done
| |
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:54:29 2024 +0200
| |
| |     feature commit 1
| |
* | commit 235cc341ce6c8965e031e1def3f604fd473cc765
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (conflict)
$ git switch master
Switched to branch 'master'

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   feature

no changes added to commit (use "git add" and/or "git commit -a")

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit --help

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git commit -am "conflict 2 commit"
[master abdb120] conflict 2 commit
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit abdb120cd73cf9afb02d3b1c499f79693dec3f1a (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 22:18:40 2024 +0200
|
|     conflict 2 commit
|
| * commit 585f6b4bb0b703c24ffbe76ad4f5658da6464bda (conflict)
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 22:16:29 2024 +0200
|
|       conflict 1 commit
|
*   commit 12226f07e576acee3708aa31e2219a9e91513108
|\  Merge: 235cc34 7cb75de
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:21:32 2024 +0200
| |
| |     feature merge commit
| |
| * commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:09:27 2024 +0200
| |
| |     feature done
| |
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:54:29 2024 +0200
| |
| |     feature commit 1
| |
* | commit 235cc341ce6c8965e031e1def3f604fd473cc765
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git merge conflict -m "conflict merge commit"
Auto-merging feature
CONFLICT (content): Merge conflict in feature
Automatic merge failed; fix conflicts and then commit the result.

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master|MERGING)
$ git log --all --graph
* commit abdb120cd73cf9afb02d3b1c499f79693dec3f1a (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 22:18:40 2024 +0200
|
|     conflict 2 commit
|
| * commit 585f6b4bb0b703c24ffbe76ad4f5658da6464bda (conflict)
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 22:16:29 2024 +0200
|
|       conflict 1 commit
|
*   commit 12226f07e576acee3708aa31e2219a9e91513108
|\  Merge: 235cc34 7cb75de
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:21:32 2024 +0200
| |
| |     feature merge commit
| |
| * commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:09:27 2024 +0200
| |
| |     feature done
| |
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:54:29 2024 +0200
| |
| |     feature commit 1
| |
* | commit 235cc341ce6c8965e031e1def3f604fd473cc765
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master|MERGING)
$ cat feature
feature commit 1
feature commit 2
feature commit 2
<<<<<<< HEAD
conflict 2
=======
conflict 1
>>>>>>> conflict

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master|MERGING)
$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   feature

no changes added to commit (use "git add" and/or "git commit -a")

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master|MERGING)
$ git merge --abort

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
* commit abdb120cd73cf9afb02d3b1c499f79693dec3f1a (HEAD -> master)
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 22:18:40 2024 +0200
|
|     conflict 2 commit
|
| * commit 585f6b4bb0b703c24ffbe76ad4f5658da6464bda (conflict)
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 22:16:29 2024 +0200
|
|       conflict 1 commit
|
*   commit 12226f07e576acee3708aa31e2219a9e91513108
|\  Merge: 235cc34 7cb75de
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:21:32 2024 +0200
| |
| |     feature merge commit
| |
| * commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:09:27 2024 +0200
| |
| |     feature done
| |
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:54:29 2024 +0200
| |
| |     feature commit 1
| |
* | commit 235cc341ce6c8965e031e1def3f604fd473cc765
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git merge conflict
Auto-merging feature
CONFLICT (content): Merge conflict in feature
Automatic merge failed; fix conflicts and then commit the result.

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master|MERGING)
$ git commit -am "merge conflict resolved"
[master 99ea76d] merge conflict resolved

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$ git log --all --graph
*   commit 99ea76dee7aa0e1cb99d36a7eea77e7784ce1fe3 (HEAD -> master)
|\  Merge: abdb120 585f6b4
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 22:26:41 2024 +0200
| |
| |     merge conflict resolved
| |
| * commit 585f6b4bb0b703c24ffbe76ad4f5658da6464bda (conflict)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 22:16:29 2024 +0200
| |
| |     conflict 1 commit
| |
* | commit abdb120cd73cf9afb02d3b1c499f79693dec3f1a
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 22:18:40 2024 +0200
|
|       conflict 2 commit
|
*   commit 12226f07e576acee3708aa31e2219a9e91513108
|\  Merge: 235cc34 7cb75de
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:21:32 2024 +0200
| |
| |     feature merge commit
| |
| * commit 7cb75dedf9b1d44d0d64b9b55dea481a58535144 (feature)
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 21:09:27 2024 +0200
| |
| |     feature done
| |
| * commit 08d03157c381fc8067d8cbcfee2637eeb2d07710
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:55:33 2024 +0200
| |
| |     feature commit 2
| |
| * commit 31c97b4bfd491079229fc5ef5ce63b4a8f6042d2
| | Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| | Date:   Thu Feb 8 20:54:29 2024 +0200
| |
| |     feature commit 1
| |
* | commit 235cc341ce6c8965e031e1def3f604fd473cc765
|/  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
|   Date:   Thu Feb 8 20:56:58 2024 +0200
|
|       bug fix commit
|
* commit e375222d1a4396f7f66ec9b4eefdc91a386ae923
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:52:49 2024 +0200
|
|     commit 3
|
* commit 20f8aeb869ce771713a253c7aeef902561a38e5a
| Author: Abdelrahmen Emad <abdoemad552@gmail.com>
| Date:   Thu Feb 8 20:51:53 2024 +0200
|
|     commit 2
|
* commit f15ffe1d29150bbb288c3da963e684c1dba2a0ff
  Author: Abdelrahmen Emad <abdoemad552@gmail.com>
  Date:   Thu Feb 8 20:50:34 2024 +0200

      commit 1

abdoe@DESKTOP-NLKPCRC MINGW64 /c/git/GIT-TUTORIAL (master)
$
```
