1. What is the difference between git add and git commit?
>> Git add --> moved changes from untrack to staged status
>> git commit --> moves changes from staged to tracked with proper commit message

2. What does the staging area do? Why doesn't Git just commit directly?
>> Staging area helps in reviewing the changes and also allows to commit specific files instead of direclty commiting it to the repo.

3. What information does git log show you?
>> Git logs shows the commit id/Name and email of Author /Date of commit/ commit message and location of commit file

4. What is the .git/ folder and what happens if you delete it?
>> .git folder is basically a git database which store all commit hostory/branches/files/connections.
>> if we delete it then our all branched/commits will be deleted and our folder will work like normal file system.

5. What is the difference between a working directory, staging area, and repository?
>> Working Directory -- were we are working and making changes to files.
>> Staging area -- when we go git add it moves files to staging area were it can be review before commit
>> Repository -- It is a project history were all your commits are stored, need to do git commit and git push to move changes to repo.
