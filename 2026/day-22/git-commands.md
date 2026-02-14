                                                <!--GIT COMMANDS-->
<<SETUP & CONFIG>>

>>git init - To initialize the repository
>>ls -a - Shows hidden files
>>git config --global -user.name "Name" - to set author and email of user

<<WORK FLOW>>
>> To move file from unttracked to Stages status -- git add <filename>
>> To move file from Stagged to Tracked status -- git commmit -m "Commmit message"
>> To move file from Staged to Untracked status -- git rm --cache <filename>
>> To restore deleted files -- git restore <filename>
>> To Create new branch with all commits of current branch -- git checkout -b <branchname>
>> To delete the branch -- git branch -D <filename>

<<VIEW CHANGES>>
git log - To check all changes happend(history) on that repo
git status - To check the current status of working directory and staging area to see what changes are staged, which are not and which                 files are tracked or untracked
git remote -v - This commands shows origin of repo connected
