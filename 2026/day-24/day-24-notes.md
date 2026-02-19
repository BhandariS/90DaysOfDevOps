1. What is a fast-forward merge?
>> When merging feature branch with main (Target) and target does not have any new commits then it merges direclty without create a mrege commit which keeps the history clean.

2. When does Git create a merge commit instead?
>> When the target and feature both have merge commits and when feature is merged to main in that case a merge commit is created and fast forward is not possible.
>> Git creates a merge commit when both branches have new commits after branching, making fast-forward impossible.

3. What is a merge conflict?
>> A merge conflict comes when multiple dev trying to update the same path of same file, while merging it throws conflict issue.

4. What does rebase actually do to your commits?
>> Rebase help to keep in sync the dev/feturebranch with main
>> To make 2 branches commit history in single sequence.
eg :
>> A --- B --- C --- X   (main)
          \
            D --- E   (feature)
after rebase
>> A --- B --- C --- X --- D' --- E'   (feature)

5. How is the history different from a merge?
>> Merge commit is used to merge the history of one branch to other, creates a merge commit and hostory shows parallel work where as in rebase hostiry is linear.

6. Why should you never rebase commits that have been pushed and shared with others?
>> It can cause issues like duplicate commit , confusion between team and force push required.

7. When would you use rebase vs merge?
>> Rebase is used when dev is working alone on feature branch, you want clean history before creating PR and wants linear history
>> Merge is user when dev working on shared branch, wants history to be intact, you merging with main

8. What does squash merging do?
>> Squash treats multiple commits and turn them into 1 commit.

9. When would you use squash merge vs regular merge?
>> Regular merge we do when we want to preserve the history, for tracebility and multiple devs working on branch.
>> Squash merge we do when we want to have one commit history, when it has small messy fixes.

10. What is the trade-off of squashing?
>> Squashing simplifies history by combining commits into one, but sacrifices detailed commit traceability, granular rollback ability, and debugging visibility.

11. What is the difference between git stash pop and git stash apply?
>> git stash pop restores them and removes the stash entry.
>> git stash apply restores stashed changes but keeps them in the stash list.

12. When would you use stash in a real-world workflow?
>> git stash temporarily saves your uncommitted changes so you can Switch branches, Pull latest changes and Fix something quickly.

13. What does cherry-pick do?
>> We can take a certain commit from our dev branch and mmerge only specific commit to the main using cheery pick.
>> git cherrypick <commitid>

14. When would you use cherry-pick in a real project?
>> If a Bug found during production release and Fix is committed in develop in that case we don’t want to merge full develop into release or main, we can cherry-pick only approved commits into release branch.

15. What can go wrong with cherry-picking?
>> Can create duplicates commits, if the branch is merged later.
>> merge COnflicts can be caused
