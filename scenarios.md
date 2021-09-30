# Git Scenario based questions

1. What is the process to revert a commit that has already been pushed and made public?

For public branches and published chnages, git revert is the best option. It does not erase any commits but creates a new revert commit. A revert is safer than a reset because it will not remove any commits from a shared history.\
**git revert HEAD**