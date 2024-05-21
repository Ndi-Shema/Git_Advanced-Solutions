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
