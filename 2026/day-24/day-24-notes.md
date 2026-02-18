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


