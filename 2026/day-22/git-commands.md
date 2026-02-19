                                                <!--GIT COMMANDS-->
<<SETUP & CONFIG>>

>> git init - To initialize the repository
>> ls -a - Shows hidden files
>> git config --global -user.name "Name" - to set author and email of user

<<WORK FLOW>>
>> To move file from unttracked to Stages status -- git add <filename>
>> To move file from Stagged to Tracked status -- git commmit -m "Commmit message"
>> To move file from Staged to Untracked status -- git rm --cache <filename>
>> To restore deleted files -- git restore <filename>

<< Remote Commands >>
>> git fetch - It basically fetch the latest changes from your repo and you can check what all changes are made, it does not sync the changes directly
>> git pull - It downloads all the latest changes and sync with your local
>> git clone <repourl> - Help in creating a copy of your repo on local , we can push changes, can edit files locally.
>> git push - It push your local commited changes to the remote repo.

<< Branching >>
>> To Create new branch with all commits of current branch -- git checkout -b <branchname>
>> To delete the branch -- git branch -D <filename>

<<VIEW CHANGES>>
>> git log - To check all changes happend(history) on that repo
>> git log --oneline - To check all logs in one line
>> git log --graph - It shows the logs  in grphn format
>> git status - To check the current status of working directory and staging area to see what changes are staged, which are                   not and which files are tracked or untracked
>> git remote -v - This commands shows origin of repo connected

<<Merging & Rebasing>>
>> git merge <branch> - To merge the commit history of one branch to other.
>> git rebase <main> - If you are on feature branch and use this command your history becomes linear with main.
                     - To make 2 branches commit history is singlle sequence.

<< Stash & CherryPick >>
>> git stash - It helps in saving your changes temporarily while you can work on other branch and removes the stash entry.
>> git stash pop - It helps in recover the saved changes
>> git stash push <file> - It can stash specific files
>> git stash apply - It restores stashed changes but keeps them in the stash list.
>> git cherry-pick <commitid> - It helps in merging specific commit to the main
