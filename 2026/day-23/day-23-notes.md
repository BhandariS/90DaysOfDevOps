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

