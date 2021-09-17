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