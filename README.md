# Common Git commands for everyday use

## Configuring user name and email
```
git config --global user.name "mir ali"
git config --global user.email mannanali413@github.com
```

## Initialze and empty git repository in the current directory
```
git init
```

## Sample add and commit of a file
1. Add all files ending with `.c` extension
```
git add *.c
```
2. Add a specific file
```
git add LICENSE
```
3. Commit the changes with a commit message
```
git commit -m "initial project version"
```

## Reset the previous commit
```
git commit --amend --reset-author
```

## Show changes to files in the staging area
```
git diff --staged
```
**Note:** `--staged` is a *synonym* for `--cached` 

## Remove a file completely
Suppose we delete a file by executing `rm PROJECTS.md`  
The current status can be viewed via  `git status`  
```
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add/rm ..." to update what will be committed)
  (use "git checkout -- ..." to discard changes in working directory)

        deleted:    PROJECTS.md

no changes added to commit (use "git add" and/or "git commit -a")
```
Now if you want the deletion to reflect in git as well then use the below command
```
git rm PROJECTS.md
```

Another useful thing you may want to do is to keep the file in your working tree but remove it from your staging area  
In other words, you may want to keep the file on your hard drive but not have Git track it anymore  
```
git rm --cached README
```
**Note:** `git rm` when used without `rm` removes the file from both the local file system and the git tree.

## Rename file in Git
```
git mv file_from file_to
```

## Log the list of all commits
```
git log
```
In order to view the **difference introduced in each commit**
```
git log -p -2
```
If you want to see some abbreviated stats for each commit, you can use the `--stat` option:
```
git log --stat
```

## Print commits on a single line
The oneline option prints each commit on a single line, which is useful if you’re looking at a lot of commits. In addition, the short, full, and fuller options show the output in roughly the same format but with less or more information
```
git log --pretty=oneline
```

If one wants to view the time elapsed since the commit were last made, one can use
```
git log --pretty=format:"%h - %an, %ar : %s"
```

##Deleting a local branch
```
git branch -d feature_x
```

## Renaming of branches
1. Rename your local branch
If you are on the branch you want to rename  
```
git branch -m new-name
```
If you are on a different branch
```
git branch -m old-name new-name
```
2. Delete the old-name remote branch and push the new-name local branch
```
git push origin :old-name new-name
```
3. Reset the upstream branch for the new-name local branch.
Switch to the branch and then
```
git push origin -u new-name
```