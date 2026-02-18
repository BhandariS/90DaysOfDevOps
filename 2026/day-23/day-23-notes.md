1. What is a branch in Git?
>>  Branch is a copy of main or dev branch where developers works on independent changes without affetcing the main code.

2. Why do we use branches instead of committing everything to main?
>> Main is a production branch and we cannot make change in prod branch direclty for that we create a feature branch and make changes in that and then a pull request is raised once approved then only the changes are merged in main.

3. What is HEAD in Git?
>> HEAD show the current position of the repository commit history
    eg: if main /feature branch are in sync the HEAD will be main and feature branch as all commits are in sync
    >> but if feature branch has extra commit then the current head will be that feature branch commit.

4. What happens to your files when you switch branches?
>> Files remain untouched only if there is no conflict with the swithc branch..

5. What is the difference between origin and upstream?
>> Origin is the repo which we cloned from and here we push changes on the other hand upstream is basically the repo we forked a repo and we sync changes.

6. What is the difference between git fetch and git pull?
>> Git Fetch -- It basically fetch the latest changes from your repo and you can check what all changes are made, it does not sync the changes directly
>> Git Pull -- It downloads all the latest changes and sync with your local

7. What is the difference between clone and fork?
>> Clone is a copy of your repo on local , we can push changes, can edit files locally.
>> Fork is a copy of someone else repo on github, we can make changes but do not have access to update the repo directly, mostly used for open source contributions

8. When would you clone vs fork?
>> Clone is used when you want to make changes in existing code which worked by your company
>> Fork is used mostly for open source contributions as you do not have write access you clone and then create pull request mostly independent projects.

9.After forking, how do you keep your fork in sync with the original repo?
>> Manually syncing the fork in github
