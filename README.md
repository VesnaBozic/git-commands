# Git Tutorial

## Summary
:arrow_right:[What is version control system?](#what-is-version-control-system)
:arrow_right:[What is in Git repository?](#what-is-in-git-repository)
:arrow_right:[What is .git?](#what-is-git)
:arrow_right:[Git status](#git-status) 
:arrow_right:[Git diff](#git-diff) 
:arrow_right:[How we save save changes that are in the staging area?](#how-we-save-changes-that-are-in-the-staging-area) 
:arrow_right:[Git add](#git-add) 
:arrow_right:[Git commit](#git-commit)
:arrow_right:[Git push](#git-push) 
:arrow_right:[Git log](#git-log) 
:arrow_right:[How can I change email for git in Bash?](#how-can-i-change-email-for-git-in-bash) 
:arrow_right:[Git checkout](#git-checkout) 
:arrow_right:[How to restore old version of file?](#how-to-restore-old-version-of-file) 
:arrow_right:[Git reset](#git-reset) 
:arrow_right:[Reversing files](#reversing-files) 
:arrow_right:[What is branch?](#what-is-branch) 
:arrow_right:[What is master branch?](#what-is-master-branch) 
:arrow_right:[Differences between branches](#differences-between-branches) 
:arrow_right:[Switching branches](#switching-branches)
:arrow_right:[Creating branch](#creating-branch)
:arrow_right:[Merging branches](#merging-branches) 
:arrow_right:[Conflicts](#conflicts) 
:arrow_right:[How to create new repository?](#how-to-create-new-repository) 
:arrow_right:[Convert existing project into repository](#convert-existing-project-into-repository) 
:arrow_right:[Repository clone](#repository-clone) 
:arrow_right:[How to see from copy of repository on our computer url of the repository?](#how-to-see-from-copy-of-repository-on-our-computer-url-of-the-repository) 
:arrow_right:[Git pull](#git-pull) 
:arrow_right:[Trying to pull when we have unsaved changes](#trying-to-pull-when-we-have-unsaved-changes) 


## What is version control system?

> A version control system is a tool that manages changes made to the files and directories in a project. Every version that ever existed is stored in the repository.

**Nothing saved on Git is ever lost. You can always access every version that ever was created.**

**Git makes collaboration very easy. We shouldn't use it just for software development, but for various stuff that need to be stored and shared.**

## What is in Git repository?

> Combination of collection of files and directories and history of the changes on the project (different versions of the project)

## What is .git?
> In .git are located all extra informations about repository. .git directory is in the root directory of the repository. We should never delete or change .git.

## Git status
```bash
git status
```
> With ***git status*** command we display a list of the files that have been modified since the last time changes were saved. These changes are stored in a staging area. While changes are in the staging area we can still change them. But once we added them to the repository, we can't make changes anymore in that commit.
> git status shows files in staging area.

>git status show us files that are not tracked by git and they are not listed in the tree

>the untracked files won't benefit from version control, so with git status we can see them

>when we add and commit files git starts tracking them

## Git diff
```bash
git diff filename
```
> With ***git diff*** we can compare the changed file in the staging area with the last saved version of that file.

> Just ***git diff*** will show all changes in the repository.

> ***git diff directory*** will show all the changes in the directory

![git diff](/assets/img/git_diff.jpg)

> On the image above we can see the differences. 

> ***a*** - means the first version 

> ***b*** - means the second changed version

> ***---*** (red) means lines removed

> ***+++*** (green) means lines added

> a line starting with ***@@*** tells us where the changes are being made

> we can use to compare the state of files with changes in the stagind area

> -r means compare to a particular revison

> HEAD always means last commit

> HEAD~1 - means commit before last commit and so on

> git diff -r HEAD path/to/file

## How we save save changes that are in the staging area?

```bash
git add .
git commit -m "message about changes"
git push
```

## git add
with

```
git add .
```

we add all files

with 

```
git add path/to/file
```

 we add that specific file, when we don't want to commit all the changes, but just part, or maybe do it in more commits
 
 with
 
 ```
 git reset HEAD
 ```
 
 we can reset last commit


## git commit

> we use to save all the changes. It always save everything that is in the staging area. If you want to undo commit you must undo everything.

> you must enter log message with commit

> if you want to change log message you can do it with

```
git commit --amend - m "new message"
```

## git push

> command used to upload local repository to a remote repo.

Pushing is how we transfer commits from our local repository to a remote repo.

We usually run 

```bash 
git push origin main
```
to push our local changes to our online repository.


## git log

> is used to see the log of the repository's history

![git log](/assets/img/git_log.jpg)

>commit line shows hash (ID for the commit)

>it says who made change, when and what and commit message

with 

```
git log -4 README.md
```

we can see last three commits involving README.md

for quit press

```
q
```

To see history of a specific file or directory

```
git log path/to/file
```

## git annonate file
>shows who made changes to each line and when

## .git ignore

> is a file in root directory for storing files we don't want Git to pay attention to

if we write in git ignore

```
*.txt
run
```
it will ignore any file or directory called run and every file with .txt extension

## git clean

with

```
git clean -n
```

we can see a list of files that are in repository but not commited (tracked), only work with ubtracked files whose history hasn't been saved

with 

```
git clean -f
```

we can delete those files and they are deleted for good

## How to configure Git?

with 

```
git config --list
```

we can see settings

## How can I change email for git in Bash?

```
git config --global user.email mymail@gmail.com 
```

## git checkout

with 

```
git checkout -- path/to/file
```

we can undo changes that we staged with git add

## How to restor old version of file?

with

```
git log
```

we can see hash ID of the commit

![git log](/assets/img/git_log.jpg)

then we use first 6 characters of hash

```
git checkout 5382de README.md
```

and it wound replace current version with this version

It would not erese any commit history, it would show just as new commit

## git reset

with

```
git reset
```

we can unstaged everything

## reversing files

with

```
git checkout --
```

we can also revert all files


## What is branch?

Git allows you to create branches, one branch represent different version of your work and you can trach each version systematically.

Change you make in one branch doesn't affect other branches, until you merge them together

## What is master branch?

Every repository has master branch. Master is a naming convention for a branch. It means it is a repository's default branch.

## git branch

with

``` 
git branch
```

we can list all the branches in a repository

* next to the name of the branch means that we are currently working in that branch

## Differences between branches

```
git diff branch1..branch2
```

## Switching branches

```
git checkout name-of-the-branch
```

## Creating branch

```
git checkout -b name-of-the-branch
```

>the content of the created branch will be sam as the content of master branch when we create it

> When we start making changes it will only affected branch

## Merging branches

it means bringing branches back together

if changes don't overlap the result is new commit, that includes every changes from branch to master branch

if conflicts exist we need to solve them first

``` 
git merge branch master
```

## Conflicts

A merge conflict is an event that occurs when Git is unable to automatically resolve differences in code between two commits. When all the changes in the code occur on different lines or in different files, Git will successfully merge commits without your help.

However, when there are conflicting changes on the same lines, a “merge conflict” occurs because Git doesn’t know which code to keep and which to discard.

If Git detects a conflict, it will highlight the conflicted area and ask which code you wish to keep.

Once you tell Git which code you want, you can save the file and proceed with the merge, rebase, or cherry pick.

Git relies on you to reconcile the conflicting changes.

## How to create new repository?

```
git init repository_name

```

## Convert existing project into repository

```
git init
```

or

from anywhere in the computer :

```
git init path/to/project
```

## Repository clone

> When we need to join existing project, or contienue working on a prject from a different machine we use git clone

```
git clone https://github.com/VesnaBozic/Git-Tutorial.git
```

## How to see from copy of repository on our computer url of the repository?

```
git remote -v
```

![git remote](/assets/img/git_remote.jpg)

with 

```
git remote
```

we get list of all remotes

## git pull

with

```
git pull
```

we can pull changes from origin repository to our cloned one

>that is usually done when we are pull changes that our collaborators made


## Trying to pull when we have unsaved changes

```
git checkout --
git pull
```
this will discard our unsaved changes







