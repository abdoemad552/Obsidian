To show the current configuration:
```
$ git config --list
```

========================================================================================
To show all files (hidden and un-hidden):
```
$ ls -al
```

========================================================================================
To convert the current directory into a repository:
```
$ git init
```

========================================================================================
To show the current status of the files:
```
$ git status
```

========================================================================================
To show the current status of the files briefly:
```
$ git status -s
```

========================================================================================
Adding a file into the index (staging area) changes its state from untracked to tracked. This can be done by the following command:
```
$ git add fileName
```

========================================================================================
To show the content of the index:
```
$ git ls-files
```

========================================================================================
To show the file in the repository:
```
$ find .git/objects/ -type f
```

========================================================================================
To show the files in the index along with its sha1 value:
```
$ git ls-files -s
```

========================================================================================
To output the contents or other properties such as size, type or delta information of one or more objects:
```bash
$ git cat-file -t 56266... // To show the type
$ git cat-file -s 56266... // To show the size
$ git cat-file -p 56266... // To show the content
```

========================================================================================
To commit changes to the repository with a message:
```bash
$ git commit -m "Changes are made"
```

========================================================================================
To show commit history:
```bash
$ git log
```

========================================================================================
Any file you update and commit, at least three files will be created for this file. These files are the blob, the tree, and the commit object (rapper).

========================================================================================
Branch is a linear sequence of commits.

========================================================================================
The difference between the two commands
```bash
$ echo "Hello" >> info.txt
$ echo "Hello" >  info.txt
```
lies in how they handle the content of the file `info.txt`:

1. `echo "Hello" > info.txt`: This command will write the string "Hello" to the file `info.txt`. If the file already exists, it will be overwritten with the new content. If the file does not exist, a new file will be created with the specified content.
    
2. `echo "Hello" >> info.txt`: This command appends the string "Hello" to the end of the file `info.txt`. If the file does not exist, it will be created. If the file already exists, the content will not be overwritten; instead, the new content will be added to the end of the existing content.
    

In summary, the `>` operator overwrites the content of the file, while the `>>` operator appends content to the end of the file.


========================================================================================
If you have modified a file that has been in the staging area, and you want to discard these changes, you can use the following command:
```bash
$ git restore file.txt
```

If you have modified and added it to the staging area, and you want to undo this add, you can use the following command:
```bash
$ git restore --staged file.txt
```

Untracking file means removing it from staging area. This can be done using the following:
```bash
$ git rm --cached file.txt
```

========================================================================================
In the output of `git status -s`, the "AM" indicates a modification that has been both added to the staging area and modified in the working directory. Specifically:

- "A" stands for Added to the staging area.
- "M" stands for Modified in the working directory.

So, "AM" together means that the file has been modified, and the changes have been staged (added to the index) in preparation for a commit.

========================================================================================
`git add` is a multipurpose command — you use it to begin tracking new files, to stage files, and to do other things like marking merge-conflicted files as resolved.

========================================================================================
If you run `git status -s` or `git status --short` you get a far more simplified output.

========================================================================================
`git diff` shows you the exact lines added and removed — the patch, as it were.
That command compares what is in your working directory with what is in your staging area. **The
result tells you the changes you’ve made that you haven’t yet staged**.

If you want to see what you’ve staged that will go into your next commit, you can use `git diff --staged`. This command compares your staged changes to your last commit.

`git diff` by itself doesn’t show all changes made since your last commit — only changes that are still un-staged. If you’ve staged all of your changes, git diff will give you no output.

========================================================================================
To show each commit in one line, we use `git log --oneline`.

When you use `git show <commit-hash>`, the command displays information about the specified commit, including the details of the changes introduced in that commit. It effectively compares the specified commit **with its parent commit** (the commit immediately before it) to show what was added, modified, or deleted.

The output of `git show` for a commit typically includes:

- Commit details (commit hash, author, date, and commit message).
- Changes to each file in the commit, including the specific lines that were added, modified, or deleted.

The comparison is made against the commit's immediate parent, so you can see the specific changes introduced by that commit.

If you want to see the differences between any two arbitrary commits, you can use the `git diff` command, specifying the commit hashes of the two commits you want to compare. For example:

```bash
git diff <commit-hash-1> <commit-hash-2>
```

This will show the differences between the two specified commits. The `git show` command is more focused on displaying information about a specific commit rather than comparing it with a previous one, although the changes displayed inherently involve a comparison with the commit's parent.

========================================================================================
To remove a file from the staging area back to working tree (undo) we write `git rm --cached fileName`.

`git restore <file>...` to discard changes in working directory. In other words, if you have a file that you have committed previously, and you have changed it content and you want to back to the content of the previous commit.

`git restore --staged <file>...` to un-stage.

========================================================================================
To `add` and `commit` at the same time we use `git commit -am "Some message"`.

========================================================================================
To edit the commit message of the last commit we use `git commit --amend`.

========================================================================================
When i was using git terminal, there was a problem that i can't see all the output especially when its big.
The solution for this is the following:
If you don't want to read the output in a pager and want it to be just printed to the terminal define the environment variable `GIT_PAGER` to `cat` or set `core.pager` to `cat` (execute `git config --global core.pager cat`).

========================================================================================
One of the more helpful options is `-p` or `--patch`, which shows the difference (the patch output)
introduced in each commit.

This option displays the same information but with a diff directly following each entry. This is very
helpful for code review or to quickly browse what happened during a series of commits that a
collaborator has added.

========================================================================================
If i want to use a previous version that is previously committed, we can either pull it from the repository to that staging area or to both working and staging area (**YOU SHOULD BE CAREFUL**).

The head is file that contains a reference to a file contains the hash value of the current commit (the commit which the head points to).
```bash
$ cd .git
$ cat HEAD
ref: refs/heads/master
$ cd refs/heads/
$ cat HEAD
3267ea03c0941aada76e3c6dff75d324527e6988
```

========================================================================================
To back to the previous commit:
```bash
$ git reset HEAD~1 // Changes applied to the staging area
$ git reset --hard HEAD~1 // Changes applied to both the staging area and the working directory.
```

The 1 indicates that we back only one version backward.

Applying `git log` after changing the current version will show only the commits till the current one even if there are other commits that was done after it.

We can use `HEAD~n` to point to the nth commit before the current commit.
```bash
$ git diff 222052a..HEAD~2
```
The above shows the difference between the commit with hash prefix `22fdvfd` and the 2nd commit before the current commit.

========================================================================================
To see references log we use the following commands:
```bash
$ git reflog
```

Using references log we can move between versions. When you back to an older version and then use `git log --oneline`, you won't be able to see versions which are subsequent to that version.

In order to see them, we use references log which behaves as a history for the HEAD reference. From which you can see all versions which the HEAD was pointing at for some period of time.

`HEAD@{n}` references the version which was pointing before n times of moves.

========================================================================================
To stage and commit at the same time:
```bash
$ git commit -am "Commit message"
```

========================================================================================
# BRANCHING
To create new branch we use:
```bash
$ git branch branch_name
```

Now, you have created a new branch. Before switching to this new branch, the HEAD is pointing to the master branch:
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git log --oneline --graph
* f255734 (HEAD -> master, testing) Third line added to file
* b89a44d Second line added to file
* d24cc7f Initial commit
```
After switching to the new branch, the HEAD points to it.
To switch to a new branch we can use any of the following:
```bash
$ git checkout testing
$ git switch testing
```
This can be shown:
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git switch testing
Switched to branch 'testing'

abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (testing)
$ git log --oneline --graph
* f255734 (HEAD -> testing, master) Third line added to file
* b89a44d Second line added to file
* d24cc7f Initial commit
```

After performing changes and commits in this branch, we can go back to the master branch and then merge these changes. This can be done as following:
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git merge testing
Updating f255734..746118b
Fast-forward
 file.txt | 1 +
 1 file changed, 1 insertion(+)
```
To merge branch `A` into branch `B` we should be standing at branch `B` and then use `git merge A`.

The process of moving forward is called `Fast forward`.

To show the branches which have been merged into the current branch we can use:
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git branch --merged
* master
  testing
```

To delete a branch, we can use:
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git branch -d testing
Deleted branch testing (was 746118b).
```

Assume that you created a branch and worked on that branch, and then **back to the master branch and created new commits to the master branch**.

Now you need to merge the previous branch.

The result will be as following:
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git log --oneline --graph --all
* e0e85cc (HEAD -> master) New file added in master branch
| * 0f86cb7 (testing) Fifth line added in testing
|/
* 746118b Fourth line added in testing
* f255734 Third line added to file
* b89a44d Second line added to file
* d24cc7f Initial commit
```

This is called **divergent history**. Merging the branch in this case will result in **Three way merge**.
```bash
abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git merge testing
Merge made by the 'ort' strategy.
 file.txt | 1 +
 1 file changed, 1 insertion(+)

abdoe@DESKTOP-NLKPCRC MINGW64 ~/gitwork (master)
$ git log --oneline --graph --all
*   b23ba3b (HEAD -> master) Merge branch 'testing'
|\
| * 0f86cb7 (testing) Fifth line added in testing
* | e0e85cc New file added in master branch 
|/
* 746118b Fourth line added in testing
* f255734 Third line added to file
* b89a44d Second line added to file
* d24cc7f Initial commit
```

Now after merging we can delete the branch safely.
```bash
$ git branch -d testing
```


# Working with Remotes
To clone a remote repository, we use `git clone` command as following:
```bash
$ git clone ./remote-repo/ newName
```

After applying this command, a copy of that repository will be created in the current directory. If the remote repo is not in the current directory, you should specify its full directory. You can also use links for cloning on the internet.

