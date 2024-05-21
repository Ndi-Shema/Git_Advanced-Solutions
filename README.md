# Git-advanced
## Challenges 
### Part 1

#### Challenge 1

```bash

$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add test.md
fatal: pathspec 'test.md' did not match any files

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add test4.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git commit --amend
[main 8c03a9a] chore: adding and amending the fourth files
 Date: Tue May 21 14:10:17 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$
```

#### 2. Editing Commit history.
```bash

$ git log
commit 8c03a9ab1367f1dc2f8dcf4516ade07920de796e (HEAD -> main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:10:17 2024 +0200

    chore: adding and amending the fourth files

commit 523bf68381b9c4012a4336f9eef3e5afd5ba7b00
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:10:17 2024 +0200

    chore: Create another file

commit c36ad5d238dc15f03b1a350ac8352988e067c7e2
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:10:17 2024 +0200

    chore: Create initial file

commit e17dfd966b3ace3b02130876931c32d5433a5a1d (origin/main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:01:40 2024 +0200

    Initial commit

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git commit --amend
[main be601ab] chore: creating second file
 Date: Tue May 21 14:10:17 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase --continue
fatal: No rebase in progress?

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git log
commit be601abaebddaf0b5d3f530ad068172c472a92a5 (HEAD -> main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:10:17 2024 +0200

    chore: creating second file

commit 523bf68381b9c4012a4336f9eef3e5afd5ba7b00
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:10:17 2024 +0200

    chore: Create another file

commit c36ad5d238dc15f03b1a350ac8352988e067c7e2
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:10:17 2024 +0200

    chore: Create initial file

commit e17dfd966b3ace3b02130876931c32d5433a5a1d (origin/main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:01:40 2024 +0200

    Initial commit

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$
```

#### Squashing commits
```bash
    pick c36ad5d chore: Create initial file
# This is a combination of 3 commits.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i HEAD~3
[detached HEAD a70e8f3] chore: creating first and second commit
 Date: Tue May 21 14:10:17 2024 +0200
 4 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

$ git rebase --continue
fatal: No rebase in progress?
```

#### Split commit
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git reset HEAD~

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add test3.md && git commit -m "Create third file"
[main 3cbb5a3] Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add test4.md && git commit -m "Create fourth file"
[main 026f13a] Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ 

```
#### Advanced squashing
```bash 

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i HEAD~2
[detached HEAD 2661435] chore: Create third file and fourth file
 Date: Tue May 21 15:26:32 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase --continue
fatal: No rebase in progress?
```

### Dropping a commit 
```bash 
    pick 2661435 chore: Create third file and fourth file

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ Echo "# Unwanted text" >> unwanted.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add unwanted.txt && git commit -m "Unwanted commit"
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the next time Git touches it
[main 15528df] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i
Successfully rebased and updated refs/heads/main.
```

#### Reordering

```bash
pick 2661435 chore: Create third file and fourth file

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i HEAD~2
fatal: invalid upstream 'HEAD~2'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git log
commit 266143562e3461cdb9ae46e512439179ca2d2d57 (HEAD -> main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 15:26:32 2024 +0200

    chore: Create third file and fourth file

commit e17dfd966b3ace3b02130876931c32d5433a5a1d (origin/main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:01:40 2024 +0200

    Initial commit

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.
```

#### Cherry-picking
```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/branch)
$ echo "# Creating test5" >> test5.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/branch)
$ git add test5.md && commit -m "Implimented test 5"
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it
bash: commit: command not found

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/branch)
$ git add test5.md && git commit -m "Implimented test 5"
[ft/branch 948dd3d] Implimented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/branch)
$ git log
commit 948dd3dc41927d564872dd0dcb019083a420e0a1 (HEAD -> ft/branch)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 16:31:18 2024 +0200

    Implimented test 5

commit 924413d8f9827d739f4a1ad1ef829c6a3df6540f (main)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 14:01:40 2024 +0200

    Initial commit

commit 6204ba71370f0a09c0168cdd1b5f592d5c54eb6e
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 15:26:32 2024 +0200

    chore: Create third file and fourth file

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/branch)
$ git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 2 and 1 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git cherry-pick 948dd3dc41927d564872dd0dcb019083a420e0a1
[main 2122147] Implimented test 5
 Date: Tue May 21 16:31:18 2024 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$
```

#### Git grapgh
```bash
$ git log --graph
* commit 2122147bef63eb00d6ea639087a4365215254618 (HEAD -> main)
| Author: Ndi-Shema <f.shema@alustudent.com>
| Date:   Tue May 21 16:31:18 2024 +0200
| 
|     Implimented test 5
| 
* commit 924413d8f9827d739f4a1ad1ef829c6a3df6540f
| Author: Ndi-Shema <f.shema@alustudent.com>
| Date:   Tue May 21 14:01:40 2024 +0200
| 
|     Initial commit
| 
* commit 6204ba71370f0a09c0168cdd1b5f592d5c54eb6e
  Author: Ndi-Shema <f.shema@alustudent.com>
  Date:   Tue May 21 15:26:32 2024 +0200
  
      chore: Create third file and fourth file

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ 
```

### Reflogs (Bonus)

```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git reflog
2122147 (HEAD -> main) HEAD@{0}: cherry-pick: Implimented test 5
924413d HEAD@{1}: checkout: moving from ft/branch to main
948dd3d (ft/branch) HEAD@{2}: commit: Implimented test 5
924413d HEAD@{3}: checkout: moving from main to ft/branch
924413d HEAD@{4}: rebase (finish): returning to refs/heads/main
924413d HEAD@{5}: rebase (pick): Initial commit
6204ba7 HEAD@{6}: rebase (pick): chore: Create third file and fourth file
315883e HEAD@{7}: rebase (start): checkout 315883e956ac24e115c899b662b9d3597bf5041a
2661435 HEAD@{8}: rebase (finish): returning to refs/heads/main
2661435 HEAD@{9}: rebase (start): checkout HEAD~1
2661435 HEAD@{10}: rebase (finish): returning to refs/heads/main
2661435 HEAD@{11}: rebase (start): checkout HEAD~1
2661435 HEAD@{12}: rebase (finish): returning to refs/heads/main
2661435 HEAD@{13}: rebase (start): checkout refs/remotes/origin/main
15528df HEAD@{14}: commit: Unwanted commit
2661435 HEAD@{15}: rebase (finish): returning to refs/heads/main
2661435 HEAD@{16}: rebase (squash): chore: Create third file and fourth file
3cbb5a3 HEAD@{17}: rebase (start): checkout HEAD~2
026f13a HEAD@{18}: commit: Create fourth file
3cbb5a3 HEAD@{19}: commit: Create third file
e17dfd9 (origin/main) HEAD@{20}: reset: moving to HEAD~
a70e8f3 HEAD@{21}: rebase (finish): returning to refs/heads/main
a70e8f3 HEAD@{22}: rebase (squash): chore: creating first and second commit
319b46d HEAD@{23}: rebase (squash): # This is a combination of 2 commits.
c36ad5d HEAD@{24}: rebase (start): checkout HEAD~3
be601ab HEAD@{25}: commit (amend): chore: creating second file
8c03a9a HEAD@{26}: rebase (finish): returning to refs/heads/main
8c03a9a HEAD@{27}: rebase (start): checkout HEAD~2
8c03a9a HEAD@{28}: commit (amend): chore: adding and amending the fourth files
5512f52 HEAD@{29}: commit: chore: Create third and fourth files
523bf68 HEAD@{30}: commit: chore: Create another file
:
```


## Part 2
### Feature Branch Creation:
```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
```

### Working on the feature branches
```bash
96  echo "# Feature files" >>feature.txt
97  git add .
98  git commit -m "Implemented core functionality for new feature"
```

### Switching Back and Making More Changes:
```bash
    101  git checkout main
    102  echo "# readme file" >readme.txt
    103  git add && git commit -m "Updated project readme"
    104  git add . && git commit -m "Updated project readme"
```

###  Local vs. Remote Branches
```bash
 109  git checkout main
  110  clear
  111  git merge ft/new-feature
  112  git push origin main
  113  git pull
  114  gti branch -r
  115  git branch -r
  116  git branch
  117  git pull origin
  118  git pull origin ft/branch
  119  clear
  120  git fetch origin
  121  git merge origin/main --allow-unrelated-histories
  122  git pull origin main --allow-unrelated-histories
  123  git push
```

### Branch Deletion:
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git branch -d ft/new-feature 
Deleted branch ft/new-feature (was c3446f7).

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ 
```

### Creating a Branch from a Commit:
```bash
    129  git log
    130  git log -1 --pretty=format:%H HEAD~2
    131  git checkout -b ft/new-branch-from-commit c46b4d36e1d1d7a1bd715ed0351f2d80e0e6585f  
```

### Branch Merging:
```bash
  134  git checkout main
  135  git merge ft/new-branch-from-commit
```

### Rebasing
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$  git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
```

### Renaming branches
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)
$ 
```