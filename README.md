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