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

### Checking out detached HEAD
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git checkout 52ee964
Note: switching to '52ee964'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 52ee964 Merge branch 'ft/new-feature'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges ((52ee964...))
$
```

## Part 3

### Stashing Changes:
```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git stash
Saved working directory and index state WIP on main: 919d3e3 Merge remote-tracking branch 'origin/main'
```

### Retrieving Stashed Changes
```bash
  151  git stash list
  152  clear
  153  git add .
  154  git commit -m "Read me"
  155  clear
  156  git stash
  157  git stash pop
```

### Branch Merging Conflicts (Continued):
```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add readme.txt && git commit -m "Main branch commit"
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
Merging branch 'ft/improved-branch-name' to main
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git add readme.txt && git commit -m "This is a feature branch commit"
On branch ft/improved-branch-name
nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ vi readme.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git add readme.txt && git commit -m "This is a feature branch commit"
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it
[ft/improved-branch-name 269979a] This is a feature branch commit
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git merge ft/improved-branch-name
Merge made by the 'ort' strategy.
 readme.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$

```

### Resolving Merge Conflicts with a Merge Tool:
```bash
# Readme file big
# Readme file not that big

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ vi readme.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git add readme.txt && git commit -m "New readme"
[main 38b8383] New readme
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git add readme.txt && git commit -m "New updated  readme"
On branch ft/improved-branch-name
nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ vi readme.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)
$ git add readme.txt && git commit -m "New updated  readme"
[ft/improved-branch-name 754308f] New updated  readme
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
No files need merging

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git pull origin main
From https://github.com/Ndi-Shema/Git_Advanced_Challenge
 * branch            main       -> FETCH_HEAD
Already up to date.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git checkout ft/improved-branch-name 
Switched to branch 'ft/improved-branch-name'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ echo "conflicting_files.txt" >> conflicting_files.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git add conflicting_files.txt && git commit -m "New updated  file"
warning: in the working copy of 'conflicting_files.txt', LF will be replaced by CRLF the next time Git touches it
[ft/improved-branch-name 439e460] New updated  file
# Readme file not that big.
 1 file changed, 1 insertion(+)
 create mode 100644 conflicting_files.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (ft/improved-branch-name)      
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git merge ft/improved-branch-name
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main|MERGING)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
Merging:
readme.txt

Normal merge conflict for 'readme.txt':
  {local}: modified file
  {remote}: modified file
Hit return to start merge resolution tool (vimdiff):
4 files to edit

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main|MERGING)
$ git add conflicting_files.txt 

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main|MERGING)
$ git commit -m "New updated  file"
[main 1ba72dc] New updated  file

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git merge ft/improved-branch-name 
Already up to date.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$
```

### Understanding Detached HEAD State:
```bash
<<<<<<< HEAD

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git checkout --detach
HEAD is now at 1ba72dc New updated  file

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges ((1ba72dc...))
$ vi readme.txt

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges ((1ba72dc...))
$ git add readme.txt && git commit -m "Updating readme"
[detached HEAD 9a0963b] Updating readme
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges ((9a0963b...))
$ git checkout -b new-branch-detached
Switched to a new branch 'new-branch-detached'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git log
commit 9a0963ba05795b2ecb4b85eddb4c64b7889ebc4c (HEAD -> new-branch-detached)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Wed May 22 17:27:44 2024 +0200

    Updating readme

commit 1ba72dc17a7cbd96d9bd167d16a700fac82d0180 (main)
Merge: 38b8383 439e460
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Wed May 22 17:18:25 2024 +0200

    New updated  file
```

### Ignoring Files/Directories:
```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
*tmp*
$ touch .gitignore

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ ls -la
total 34
drwxr-xr-x 1 Lenovo 197121   0 May 22 17:30 ./
drwxr-xr-x 1 Lenovo 197121   0 May 21 13:54 ../
drwxr-xr-x 1 Lenovo 197121   0 May 22 17:28 .git/
-rw-r--r-- 1 Lenovo 197121   0 May 22 17:30 .gitignore
-rw-r--r-- 1 Lenovo 197121  23 May 22 17:13 conflicting_files.txt
-rw-r--r-- 1 Lenovo 197121  17 May 21 21:17 feature.txt
-rw-r--r-- 1 Lenovo 197121  54 May 22 17:13 README.md
-rw-r--r-- 1 Lenovo 197121 102 May 22 17:26 readme.txt
-rw-r--r-- 1 Lenovo 197121 103 May 22 17:13 readme.txt.orig
-rw-r--r-- 1 Lenovo 197121   0 May 21 21:17 test1.md
-rw-r--r-- 1 Lenovo 197121   0 May 21 21:17 test2.md
-rw-r--r-- 1 Lenovo 197121   0 May 21 16:16 test3.md
-rw-r--r-- 1 Lenovo 197121   0 May 21 16:16 test4.md
-rw-r--r-- 1 Lenovo 197121  18 May 21 16:37 test5.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ ^C

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ vi .gitignore

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git add.gitignore
git: 'add.gitignore' is not a git command. See 'git --help'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git add .gitignore
warning: in the working copy of '.gitignore', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git commit -m "Updating .gitignore to exclude temp files"
[new-branch-detached 40c6a01] Updating .gitignore to exclude temp files
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$

```

### Working with Tags:
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag -l

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag -a v1.0 -m "First tag"

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag
v1.0

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag -d v1.0 
Deleted tag 'v1.0' (was afdfe69)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ 


```

### Listing and Deleting Tags:
```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag -l

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag -a v1.0 -m "First tag"

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag
v1.0

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git tag -d v1.0 
Deleted tag 'v1.0' (was afdfe69)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ 

```


### Pushing Local Work to Remote Repositories:
```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git push origin main
Enumerating objects: 23, done.
Counting objects: 100% (23/23), done.
Delta compression using up to 8 threads
Compressing objects: 100% (16/16), done.
Writing objects: 100% (20/20), 1.79 KiB | 916.00 KiB/s, done.
Total 20 (delta 9), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (9/9), completed with 1 local object.
To https://github.com/Ndi-Shema/Git_Advanced_Challenge.git
   919d3e3..1ba72dc  main -> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ 



```

### Pulling Changes from Remote Repositories:

```bash
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (new-branch-detached)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$ git pull origin main
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 969 bytes | 51.00 KiB/s, done.
From https://github.com/Ndi-Shema/Git_Advanced_Challenge
 * branch            main       -> FETCH_HEAD
   1ba72dc..0f4acdc  main       -> origin/main
Updating 1ba72dc..0f4acdc
Fast-forward
 README.md | Bin 54 -> 46 bytes
 1 file changed, 0 insertions(+), 0 deletions(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedChallenges (main)
$

```