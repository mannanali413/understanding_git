# understanding_git
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com

git config --global core.editor emacs
git config --list

git config user.name

git init

git add *.c
git add LICENSE
git commit -m "initial project version"

git clone https://github.com/libgit2/libgit2
git clone https://github.com/libgit2/libgit2 mylibgitgit clone https://github.com/libgit2/libgit2 mylibgit

git status

.gitignore

git diff
git diff --staged

git add CONTRIBUTING.md
git commit -a -m "added new benchmarks"

rm PROJECTS.md
git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add/rm ..." to update what will be committed)
  (use "git checkout -- ..." to discard changes in working directory)

        deleted:    PROJECTS.md

no changes added to commit (use "git add" and/or "git commit -a")

git rm PROJECTS.md
git status

git rm --cached README
Another useful thing you may want to do is to keep the file in your working tree but remove it from your staging area. In other words, you may want to keep the file on your hard drive but not have Git track it anymore.

git rm log/\*.log

If you want to rename a file in Git, you can run something like:
git mv file_from file_to

git log
git log -p -2
shows the difference introduced in each commit.

if you want to see some abbreviated stats for each commit, you can use the --stat option:
git log --stat

git log --pretty=oneline
The oneline option prints each commit on a single line, which is useful if you’re looking at a lot of commits. In addition, the short, full, and fuller options show the output in roughly the same format but with less or more information

git log --pretty=format:"%h - %an, %ar : %s"

git log --pretty=format:"%h %s" --graph
