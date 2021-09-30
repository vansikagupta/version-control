## Git cheat sheet

Purpose of any version control system is to allow you to record changes made to your code so that you can go back and see who made what changes, where were bugs introduced and revert the problematic changes.

> **git log**

allows you to display commits. You can filter the commits or format how they are displayed by passing parameters.

> **merge** and **rebase**

Git offers two utilities for integrating changes from one branch to another. One of them is rebase and the other is merge. Both do the same things but in very different ways.

Let's understand:
https://www.atlassian.com/git/tutorials/merging-vs-rebasing

Merging is nice because it’s a non-destructive operation. The existing branches are not changed in any way. 

> **git cherry-pick**

Cherry picking is the act of picking a commit from a branch and applying it to another. 
Enables you to pick arbitrary commit and append to the current working HEAD.

> **git clean**

Remove untracked files from working branch
More details https://koukia.ca/how-to-remove-local-untracked-files-from-the-current-git-branch-571c6ce9b6b1

# Undo commits or changes
Consider commits as snapshots of time in the past. So by 'undoing' in git, we want to go back in time or to a specific time where the mistake was not there.

## Exploring old commits
 **git log** : review history of a repository
## Viewing an old commit
 Once you have identified the commit, you can visit it using
 **git checkout <commit SHA-1>**\
 It loads the saved snapshot into your development machine. This is a Detached HEAD state, you can explore the code base, make changes, commit, nothing will be effected. \
 You can checkout to your previous branch safely.
## Undo with checkout
someCommit->goodCommit->crazyCommit\
If you are at crazyCommit and want to go back to goodCommit.\
**git checkout goodCommit**\
We are now at a detached HEAD.\
**git checkout -b new_branch_with_goodCommit**

*This will leave the previous branch useless*
## Undo with revert
someCommit->goodCommit->crazyCommit\
**git revert HEAD**
Creates a new commit with inverse changes from crazyCommit.\
someCommit->goodCommit->crazyCommit->inverseCrazyCommit

**Preffered way public branches**

## Undo with reset
**git reset --hard goodCommit**\
* Reset the commit history to goodCommit and commits after goodCommit will be erased.\
* Maintains Clean commit history
* Remote branch will show conflict and need a force push
**Not preferred for public branches**

## Undo premature commits
In order to add on to the last commit, that was commited prematurely, we can stage the new chnages with\
git add\
and then do\
**git commit --amend**

## References:

https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud