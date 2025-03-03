# Advanced Gi Exercises

## Part1:

### Ex1,Ex2:

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
