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

5. How is git revert different from git reset?
>> git reset rewrites history by moving the branch pointer, while git revert creates a new commit that undoes changes.

6. Why is revert considered safer than reset for shared branches?
>> Revert is safer for shared branches because it preserves history and avoids disrupting other developers’ work.

7. When would you use revert vs reset?
>> Use git reset when:
* The commits are local and not pushed
* Cleaning up commits before creating a PR
* Squashing or editing commit history
* Fixing a recent mistake in your own branch
* Working alone on a feature branch

>> Use git revert when:
* The commit is already pushed
* The branch is shared (main, release, etc.)
* Undoing a bad production change
* Working in team environments
* CI/CD pipelines depend on commit history

| Topic                                | `git reset`                                 |`git revert`                            |                                      |                                             |
| ------------------------------------ | --------------------------------------------| -------------------------------------------------------------------------------------------------------------------------------------------------------------------  
| **What it does**                     | Moves the branch pointer to a               |Creates a new commit that undoes the  
|                                      | previous commit (rewrites history)          | changes of a previous commit  
|                                      |                                             | 
| **Removes commit from history?**     | ✅ Yes                                      | ❌ No (original commit remains,
|                                      |   (commit disappears from branch history)   | a new reversing commit is added)
|                                      |                                             |
| **Safe for shared/pushed branches?** | ❌ No (requires force push                  | ✅ Yes (does not rewrite history)
|                                      |    and rewrites shared history)             |                                        |                                      |                                             |
| **When to use**                      | Local cleanup, fixing recent commits,       | Undoing a bad commit on shared         |                                      | squashing, editing history before pushing   | branches, production rollback, 
|                                      |                                             | safe team collaboration 
---------------------------------------|---------------------------------------------|----------------------------------------

