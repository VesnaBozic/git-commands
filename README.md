# Git Tutorial

## What is version control system?

> A version control system is a tool that manages changes made to the files and directories in a project.

**Nothing saved on Git is ever lost. You can allways access every version that ever were created.**

**Git makes collaboration very easy. We shouldn't use it just for software development, but for various stuff that need to be stored and shared.**

## What is in Git repository?

> The files and directories.
> History of the changes on the project.

## What is .git?
> In .git are located all extra informations about repository. .git directory is in the root directory of the repository. We should never delete or change .git.

## Git status
```bash
git status
```
> With **git status** command we display a list of the files that have been modified since the last time changes were saved. This changes are stored in a staging area. While changes are in the staging are we can still change them. But once we added them to the repository, we can't make changes anymore in that commit.
> git status shows files in staging area

## git diff
```bash
git diff filename
```
> with **git diff** we can compare the changed file in the staging area with the last saved version of that file
> just **git diff** will show all changes in the repository
> **git diff directory** will show all the changes in the directory