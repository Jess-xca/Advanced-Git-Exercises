# Advanced Git Exercises

## Part1:

### Ex1 and Ex2:

```bash
user@_26026 MINGW64 /d/Advanced Git (master)
$ git branch -M main

user@_26026 MINGW64 /d/Advanced Git (main)
$ touch test{1..4}.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test1.md && git commit -m "chore: Create initial file"
[main (root-commit) ae8617c] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test2.md && git commit -m "chore: Create another file"
[main a9ee670] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main a24aaf1] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log
commit a24aaf1849bc617dc2d071f92c4909a488a597bc (HEAD -> main)
Author: Jessica Irakoze <jessicairakoze4@gmail.com>
Date:   Mon Mar 3 18:09:43 2025 +0200

    chore: Create third and fourth files

commit a9ee67079c37b0e672a7f4702acc5b5bf2ca33f3
Author: Jessica Irakoze <jessicairakoze4@gmail.com>
Date:   Mon Mar 3 18:09:42 2025 +0200

    chore: Create another file

commit ae8617c6a0aa32d9b85dfcd40d2821c066fc77c2
Author: Jessica Irakoze <jessicairakoze4@gmail.com>
Date:   Mon Mar 3 18:09:40 2025 +0200

    chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test4.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit --amend --no-edit
[main 1295381] chore: Create third and fourth files
 Date: Mon Mar 3 18:09:43 2025 +0200
pick a9ee670 chore: Create another file
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log
commit 129538124edf2cd83ed8a4e81387071df3fa9430 (HEAD -> main)
Author: Jessica Irakoze <jessicairakoze4@gmail.com>
Date:   Mon Mar 3 18:09:43 2025 +0200

    chore: Create third and fourth files

commit a9ee67079c37b0e672a7f4702acc5b5bf2ca33f3
Author: Jessica Irakoze <jessicairakoze4@gmail.com>
Date:   Mon Mar 3 18:09:42 2025 +0200

    chore: Create another file

commit ae8617c6a0aa32d9b85dfcd40d2821c066fc77c2
Author: Jessica Irakoze <jessicairakoze4@gmail.com>
Date:   Mon Mar 3 18:09:40 2025 +0200

    chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline
1295381 (HEAD -> main) chore: Create third and fourth files
a9ee670 chore: Create another file
ae8617c chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test2.md
warning: in the working copy of 'test2.md', CRLF will be replaced by LF the next time Git touches it
user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "initial file"
pick 4e0acbd initial file

[main 4e0acbd] initial file
 1 file changed, 1 insertion(+)

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test1
fatal: pathspec 'test1' did not match any files

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test1.md
warning: in the working copy of 'test1.md', CRLF will be replaced by LF the next time Git touches it

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "first initial file"
[main 71daf07] first initial file
 1 file changed, 1 insertion(+)

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline
71daf07 (HEAD -> main) first initial file
4e0acbd initial file
1295381 chore: Create third and fourth files
a9ee670 chore: Create another file
ae8617c chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git rebase -i HEAD~2
[detached HEAD 75e2abe] chore: Create second file
 Date: Mon Mar 3 18:16:56 2025 +0200
 1 file changed, 1 insertion(+)
a9ee670 chore: Create another file
ae8617c chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git rebase -i HEAD~2
[detached HEAD 75e2abe] chore: Create second file
 Date: Mon Mar 3 18:16:56 2025 +0200
 1 file changed, 1 insertion(+)
$ git rebase -i HEAD~2
[detached HEAD 75e2abe] chore: Create second file
 Date: Mon Mar 3 18:16:56 2025 +0200
 1 file changed, 1 insertion(+)
Successfully rebased and updated refs/heads/main.

```

### Ex3:

```bash
$ git log --oneline
75e2abe (HEAD -> main) chore: Create second file
4e0acbd initial file
1295381 chore: Create third and fourth files
a9ee670 chore: Create another file
ae8617c chore: Create initial file
pick 4e0acbd initial file
# This is a combination of 2 commits.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git rebase -i HEAD~2
[detached HEAD 8235562] chore: Create second file
 Date: Mon Mar 3 18:15:59 2025 +0200
 2 files changed, 2 insertions(+)
Successfully rebased and updated refs/heads/main.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline
8235562 (HEAD -> main) chore: Create second file
1295381 chore: Create third and fourth files
a9ee670 chore: Create another file
ae8617c chore: Create initial file

```

### Ex4:

```bash

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test3.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "chore: Create third file"
[main 522f4b4] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add test4.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "chore: Create fourth file"
[main bb48202] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline
bb48202 (HEAD -> main) chore: Create fourth file
522f4b4 chore: Create third file
a9ee670 chore: Create another file
ae8617c chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)

```

### Ex5:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git rebase -i HEAD~2
error: cannot rebase: Your index contains uncommitted changes.
error: Please commit or stash them.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git stash README.md
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'README.md'

user@_26026 MINGW64 /d/Advanced Git (main)
$ git stash
Saved working directory and index state WIP on main: bb48202 chore: Create fourth file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git rebase -i HEAD~2
[detached HEAD 98c5277] chore: Create third file
 Date: Mon Mar 3 18:51:22 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline
98c5277 (HEAD -> main) chore: Create third file
a9ee670 chore: Create another file
ae8617c chore: Create initial file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git  stash apply
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test1.md
        modified:   test2.md


user@_26026 MINGW64 /d/Advanced Git (main)
$
```

### Ex6:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ touch unwanted.txt

user@_26026 MINGW64 /d/Advanced Git (main)
$ echo "This is an unwanted commit" > unwanted.txt

user@_26026 MINGW64 /d/Advanced Git (main)
$ echo "This is an unwanted commit" > unwanted.txt

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add unwanted.txt
user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "Unwanted commit"
[main b9d8441] Unwanted commit
 2 files changed, 212 insertions(+)
 create mode 100644 README.md
 create mode 100644 unwanted.txt

$ git log --oneline
b9d8441 (HEAD -> main) Unwanted commit
98c5277 chore: Create third file
a9ee670 chore: Create another file
ae8617c chore: Create initial file

```

### Ex7:

```bash

$ git rebase -i HEAD~3
hint: Waiting for your editor to close the file...


$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.
```

### Ex8:

```bash

user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

user@_26026 MINGW64 /d/Advanced Git (ft/branch)
$ echo "Some content for test5" > test5.md
user@_26026 MINGW64 /d/Advanced Git (ft/branch)
$ git add test5.md

user@_26026 MINGW64 /d/Advanced Git (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch 23eca49] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

user@_26026 MINGW64 /d/Advanced Git (ft/branch)
$

user@_26026 MINGW64 /d/Advanced Git (main)
$ git cherry-pick 23eca49
[main 332b328] Implemented test 5
 Date: Mon Mar 3 19:34:56 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md


user@_26026 MINGW64 /d/Advanced Git (main)
$ git cherry-pick --continue
error: no cherry-pick or revert in progress
fatal: cherry-pick failed

user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline
332b328 (HEAD -> main) Implemented test 5
b70ceb6  added README.md
7922a35 chore: Create another file
b543dfc chore: Create third file
ae8617c chore: Create initial file
```

### Ex9:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --graph --oneline --all --decorate
* 332b328 (HEAD -> main) Implemented test 5
| * 23eca49 (ft/branch) Implemented test 5
|/
* b70ceb6  added README.md
* 7922a35 chore: Create another file
* b543dfc chore: Create third file
| *   8af45cd (refs/stash) WIP on main: b9d8441 Unwanted commit
| |\
| | * 2616ac2 index on main: b9d8441 Unwanted commit
| |/
| * b9d8441 Unwanted commit
| * 98c5277 chore: Create third file
| * a9ee670 chore: Create another file
|/
* ae8617c chore: Create initial file
```

### Ex10:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git reflog
332b328 (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
b70ceb6 HEAD@{1}: checkout: moving from ft/branch to main
23eca49 (ft/branch) HEAD@{2}: commit: Implemented test 5
b70ceb6 HEAD@{3}: checkout: moving from main to ft/branch
b70ceb6 HEAD@{4}: rebase (finish): returning to refs/heads/main
b70ceb6 HEAD@{5}: rebase (pick): added README.md
7922a35 HEAD@{6}: rebase (pick): chore: Create another file
b543dfc HEAD@{7}: rebase (pick): chore: Create third file
ae8617c HEAD@{8}: rebase (start): checkout HEAD~3
da83a14 HEAD@{9}: rebase (finish): returning to refs/heads/main
da83a14 HEAD@{10}: rebase (start): checkout HEAD~2
da83a14 HEAD@{11}: commit: added README.md
98c5277 HEAD@{12}: rebase (finish): returning to refs/heads/main
98c5277 HEAD@{13}: rebase (start): checkout HEAD~1
b9d8441 HEAD@{14}: reset: moving to HEAD
b9d8441 HEAD@{15}: commit: Unwanted commit
98c5277 HEAD@{16}: rebase (finish): returning to refs/heads/main
98c5277 HEAD@{17}: rebase (squash): chore: Create third file
522f4b4 HEAD@{18}: rebase (start): checkout HEAD~2
bb48202 HEAD@{19}: reset: moving to HEAD
bb48202 HEAD@{20}: reset: moving to HEAD
bb48202 HEAD@{21}: commit: chore: Create fourth file
522f4b4 HEAD@{22}: commit: chore: Create third file
a9ee670 HEAD@{23}: reset: moving to HEAD
a9ee670 HEAD@{24}: reset: moving to HEAD~1
3b8b08a HEAD@{25}: commit: chore: Create third file
a9ee670 HEAD@{26}: reset: moving to HEAD~1
1295381 HEAD@{27}: reset: moving to HEAD
1295381 HEAD@{28}: reset: moving to HEAD~1
8235562 HEAD@{29}: rebase (finish): returning to refs/heads/main
8235562 HEAD@{30}: rebase (squash): chore: Create second file
4e0acbd HEAD@{31}: rebase (start): checkout HEAD~2
75e2abe HEAD@{32}: rebase (finish): returning to refs/heads/main
75e2abe HEAD@{33}: rebase (reword): chore: Create second file
71daf07 HEAD@{34}: rebase: fast-forward
4e0acbd HEAD@{35}: rebase (start): checkout HEAD~2
71daf07 HEAD@{36}: commit: first initial file
4e0acbd HEAD@{37}: commit: initial file
1295381 HEAD@{38}: rebase (finish): returning to refs/heads/main
1295381 HEAD@{39}: rebase (start): checkout HEAD~2
1295381 HEAD@{40}: commit (amend): chore: Create third and fourth files
a24aaf1 HEAD@{41}: commit: chore: Create third and fourth files
a9ee670 HEAD@{42}: commit: chore: Create another file
ae8617c HEAD@{43}: commit (initial): chore: Create initial file
(END)
```

## Part 2:

### Ex1:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git branch ft/new-feature

user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout ft/new-feature
M       README.md
Switched to branch 'ft/new-feature'

user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ git branch
  ft/branch
* ft/new-feature
  main
```

### Ex2:

```bash
user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ touch feature.txt

user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ echo "This is the core functionality for the new feature." > feature.txt

user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ git add feature.txt

user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ git commit -m "feat: Implemented core functionality for new feature"
[ft/new-feature 53560c5] feat: Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

### Ex3:

```bash
user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ git checkout main
M       README.md
Switched to branch 'main'

user@_26026 MINGW64 /d/Advanced Git (main)
$ touch readme.txt

user@_26026 MINGW64 /d/Advanced Git (main)
$ echo "This project contains various features and functionalities." > readme.txt

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add readme.txt

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "docs: Updated project readme"
[main db51519] docs: Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

### Ex4:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout ft/new-feature
M       README.md
Switched to branch 'ft/new-feature'

user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ git push origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 352 bytes | 352.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/Jess-xca/Advanced-Git-Exercises/pull/new/ft/new-feature
remote:
To https://github.com/Jess-xca/Advanced-Git-Exercises.git
 * [new branch]      ft/new-feature -> ft/new-feature

user@_26026 MINGW64 /d/Advanced Git (ft/new-feature)
$ git pull origin ft/new-feature
From https://github.com/Jess-xca/Advanced-Git-Exercises
 * branch            ft/new-feature -> FETCH_HEAD
Already up to date.
```

### Ex 5

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git pull origin main
From https://github.com/Jess-xca/Advanced-Git-Exercises
 * branch            main       -> FETCH_HEAD
Already up to date.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git branch -d ft/new-feature
error: the branch 'ft/new-feature' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D ft/new-feature'
hint: Disable this message with "git config advice.forceDeleteBranch false"

user@_26026 MINGW64 /d/Advanced Git (main)
$ git branch -D ft/new-feature
Deleted branch ft/new-feature (was 8b0029a).

user@_26026 MINGW64 /d/Advanced Git (main)
$ git push origin --delete ft/new-feature
```

### Ex 6

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git log --oneline --decorate --graph --all
* 72bea31 (HEAD -> main, origin/main) Part 2 progress
* 65f0586 Part 2 progress
* 453b65c Part 2 progress
* db51519 docs: Updated project readme
* 1398129 second file
* 36b443d initial file
* edd35d4 complete Part1:
* 332b328 Implemented test 5
| * 23eca49 (ft/branch) Implemented test 5
|/
* b70ceb6  added README.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout -b ft/new-branch-from-commit 453b65c
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add README.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "Save changes before switching branches"
[main 7bb5214] Save changes before switching branches
 1 file changed, 25 insertions(+)

user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout -b ft/new-branch-from-commit 453b65c
Switched to a new branch 'ft/new-branch-from-commit'

user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git branch
  ft/branch
* ft/new-branch-from-commit
  main
```

### Ex 7

```bash
user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git checkout main
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting

user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git stash
Saved working directory and index state WIP on ft/new-branch-from-commit: 453b65c Part 2 progress

user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'

user@_26026 MINGW64 /d/Advanced Git (main)
$ git pull origin main
From https://github.com/Jess-xca/Advanced-Git-Exercises
 * branch            main       -> FETCH_HEAD
Already up to date.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git merge ft/new-branch-from-commit
Already up to date.
```

### Ex 8

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout ft/new-branch-from-commit
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add README.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "Exercise 8, Part 2"
[main f21bbaa] Exercise 8, Part 2
 1 file changed, 80 insertions(+), 4 deletions(-)

user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git fetch origin

user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'

user@_26026 MINGW64 /d/Advanced Git (main)
$ git pull origin main
From https://github.com/Jess-xca/Advanced-Git-Exercises
 * branch            main       -> FETCH_HEAD
Already up to date.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
```

### Ex 9

```bash
user@_26026 MINGW64 /d/Advanced Git (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name
```

### Ex 10

```bash
user@_26026 MINGW64 /d/Advanced Git (ft/improved-branch-name)
$ git checkout 453b65c
Note: switching to '453b65c'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 453b65c Part 2 progress

user@_26026 MINGW64 /d/Advanced Git ((453b65c...))
$ git checkout -b new-branch-from-detached
Switched to a new branch 'new-branch-from-detached'

user@_26026 MINGW64 /d/Advanced Git (new-branch-from-detached)
$ git checkout main
Switched to branch 'main'
```

## Part 3:

### Ex 1 and 2:

```bash
user@_26026 MINGW64 /d/Advanced Git (main)
$ git stash
Saved working directory and index state WIP on main: a3d83b3 End of Part 2 Exercise

user@_26026 MINGW64 /d/Advanced Git (main)
$ git stash list
stash@{0}: WIP on main: a3d83b3 End of Part 2 Exercise
stash@{1}: WIP on ft/new-branch-from-commit: 453b65c Part 2 progress
stash@{2}: WIP on main: b9d8441 Unwanted commit
stash@{3}: WIP on main: bb48202 chore: Create fourth file

user@_26026 MINGW64 /d/Advanced Git (main)
$ git stash apply
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        FETCH_HEAD

no changes added to commit (use "git add" and/or "git commit -a")

user@_26026 MINGW64 /d/Advanced Git (main)
$ git stash pop
error: Your local changes to the following files would be overwritten by merge:
        README.md
Please commit your changes or stash them before you merge.
Aborting
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        FETCH_HEAD

no changes added to commit (use "git add" and/or "git commit -a")
The stash entry is kept in case you need it again.

user@_26026 MINGW64 /d/Advanced Git (main)
$ git add README.md

user@_26026 MINGW64 /d/Advanced Git (main)
$ git commit -m "Resolved merge conflict in README.md"
[main 9af116d] Resolved merge conflict in README.md
 2 files changed, 1 insertion(+), 2 deletions(-)
 create mode 100644 FETCH_HEAD

```

### Ex 3:

```bash
This is a change from feature-branch.

```
