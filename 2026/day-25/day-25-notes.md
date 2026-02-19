1. What is the difference between --soft, --mixed, and --hard?
** Most Inportant -- git reset moves the branch pointer (HEAD),but the flag decides what happens to staging + working directory.

>> git reset --soft HEAD~1 -- what it does it moves the branch pointer and keep the changes in staging and in working directory.
>> git reset --mixed -- What is does is it moves the branch pointer head and keep the changes unstaged and in working directory.
>> git reset --hard -- It also moves branch pointer but clear the staging and clear working dir. All changes are deleted                               permanently.

2. Which one is destructive and why?
>> git reset --hard is destructive because it moves the branch pointer and permanently deletes staged and working directory changes, potentially losing uncommitted work.
>> git reset --hard HEAD~1
Git will:
*Move branch back 1 commit
*Delete all local modifications
*Remove staged changes
*Revert files to exact state of that commit

3. When would you use each one?
>> Use --soft when you want to rewrite commits but keep all changes staged.
* eg: You have multiple messy commits and you want to make it a single commit in that case we will use soft
* git reset --soft HEAD~3 --> It will revert last 3 commits keeps in staged will update the commit message and commit all 3 files as one.
  
>> Use --mixed when you committed too early.
* eg: You commited the files and forgot to add something then we can use mixed
* git reset HEAD~1 --> Using this commit will be removed, file becomes unstaged and you can edit and recommit.

>> Use --hard when you want to completely discard changes.
* eg: You messed up with conflict resolution on your local branch in that case
* git reset --hard HEAD --> It cleans the local , removed all changes which were made.

4. Should you ever use git reset on commits that are already pushed?
>> You should not use git reset on commits that are already pushed and shared because it rewrites history and can break other developers’ branches. Instead, you should use git revert for public branches.
* eg: Revert the changes after push amy lead to confusion in team and some dev already have the changes or getting issues wjile git pull, duplicate commits.

