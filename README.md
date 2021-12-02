# Git Tutorial

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

## How we save save changes that are in the staging area?

```bash
git add .
git commit -m "message about changes"
git push
```

### git add
> git add .  means add all files
> git add filename means add that specific file

### git diff -r HEAD
> we can use to compare the state of files with changes in the stagind area
> -r means compare to a particular revison
> HEAD means compare with the last commit
> git diff -r HEAD path/to/file

### git commit
> we use to save all the changes. It always save everything that is in the staging area. If you want to undo commit you must undo everything.
> you must enter log message with commit
