# Git-advanced
## Challenges 
### Part 1

#### Challenge 1

```bash

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git add README.md 
warning: in the working copy of 'README.md', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git commit -m "initial commit"
[master (root-commit) a881375] initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git remote add origin https://github.com/Ndi-Shema/Git-advanced.git

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git push -u origin main
error: src refspec main does not match any
error: failed to push some refs to 'https://github.com/Ndi-Shema/Git-advanced.git'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 231 bytes | 231.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Ndi-Shema/Git-advanced.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ touch test{1..4}.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git add test1.md && commit -m "chore: Create initial file"
bash: commit: command not found

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ e: Create initial file"
At line:1 char:18
+ git add test1.md && git commit -m "chore: Create initial file"
+                  ~~
The token '&&' is not a valid statement separator in this version.
    + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException   
    + FullyQualifiedErrorId : InvalidEndOfLine

PS C:\Users\Lenovo\desktop\GitAdvancedExercises>^C

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[master 0fb00e7] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[master 14e11bb] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[master bae4e34] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git log
chore: Create third and fourth files
commit bae4e346cf718346b682c9fc5f80c3bc2c63712c (HEAD -> master)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 11:47:22 2024 +0200

    chore: Create third and fourth files
Date:   Tue May 21 11:47:21 2024 +0200

    chore: Create initial file

commit a88137556342ccc8df70ed41365b15c82a24d744 (origin/master)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Tue May 21 11:30:09 2024 +0200

    initial commit

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git add test4.md

chore: amended fourth files
 fourth files
 Date: Tue May 21 11:47:22 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$ git commit --amend
[master 4376971] chore: amended fourth files
 Date: Tue May 21 11:47:22 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Desktop/GitAdvancedExercises (master)
$

```
