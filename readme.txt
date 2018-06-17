This is a new repository.
The main goal of it is to warm up git.

Basic commands:
0. git init

1. git add <filename>

2. git commit -m "..."

3. git diff <filename>
Note: compare CURRENT and STAGE

4. git status

Intermediate:
travel through time, back to old commits
5. git log

6. git reset --hard HEAD^
Note: HEAD means the nearest one commit; HEAD^ means one commit back

7. git reflog

CURRENT to STAGE    : git add
STAGE to MASTER     : git commit

8. git diff HEAD -- <filename>
Note: compare CURRENT and MASTER(HEAD)

9. git checkout -- <filename>
Note: from STAGE to CURRENT

10. git reset HEAD <filename>
Note: from MASTER to STAGE

11. git rm <filename>
Note: delete file from STAGE; to also delete from MASTER, use git commit

12. git remote add origin git@github.com:izff/learngit.git
Note: name of remote is ORIGIN, can be changed

13. git push -u origin master
Note: initial push, from MASTER to remote ORIGIN
the -u means associating remote MASTER with local MASTER
can be omitted for later pushes

14. git pull origin master
Note: from remote ORIGIN to MASTER

15. git clone git@github.com:USERNAME/REPOS.git

16. git checkout -b dev
== git branch dev && git checkout dev
Note: create new branch and switch to it

17. git checkout master
Note: check back to MASTER

18. git merge dev
Note: merge dev to current MASTER
(Fast-forward: easy merge, no conflicts)

19. git branch -d dev
Note: delete branch dev

20. git branch
Note: show all branches

21. git merge <branch>
Note: automatic merge may fail; need to solve manually.
Details: branch dev is from master; if they are modified the same file,
    and have both < git add; git commit -m >; when checkout to master and
    try to merge the two branched, conflicts may occur.

22. git log --graph --pretty=oneline --abbrev-commit
    git log : the full detail

23. git merge --no-ff -m <commit message> dev
Note: diable fast-forward merge method
    branch management: all workers work on their own branch
                       they commit only to dev
                       only dev commit to master

24. git checkout dev (We are working on dev in the beginning)
    git stash        (after some work, we save the workspace)
Note: save CURRENT temporarily, and then we checkout master;
    so that we can change our focus on something more urgent.
    git checkout master
    <some other work, fix bugs or so>
    git checkout dev (get back to work on branch dev)
    git stash list   (list stashes)
    git stash pop    (reload stash and delete saved stash entry)

25. git stash apply && git stash drop
    git stash apply stash@{0} (choose the stash to apply)

26. to develop a new feature: we'd better create a new branch
    and to delete a branch that has never been merged:
    git branch -D <branch>

27. git remote
Note: show remote repository designation name, which is usually ORIGIN
    git push origin master
    git push origin dev     (push other branches to remote)

28. git checkout -b dev origin/dev

    git add <filename>
    git commit -m 'modify dev branch'
    git push origin dev
    > error: failed to push some refs to <remote>
    > this means remote dev conflicts our local dev branch
    > we need to pull remote to local, fix on local machine, then push

    git pull <remote> <branch>
    > but before we pull, we need to link local branch to remote one
    git branch --set-upstream-to=origin/dev dev
    git pull

29. git rebase
Note: migrate all the modifications on one branch to another branch.
    would change the history of the commit timeline, but would make the
    timeline neater and cleaner.

Example:

    M1---M2---M3---M4       Master
         |
         B1a--B1b--B1c      Branch1
         |
         B2a--B2b--B2c      Branch2

=>                 (Master before merge)
                    |              Branch2(Master after merge)
                    |              |
    M1---M2---M3---M4---B2a--B2b--B2c 
         |
         B1a--B1b--B1c      Branch1

    git rebase --onto master branch2 branch1
    git checkout master
    git merge branch2

    git rebase master branch1
    git checkout master
    git merge branch1

    git branch -d branch1
    git branch -d branch2

30. rule of rebase: 
    Do not rebase commits that exist outside your repository.
    another trick, inform everyone to use: 
        git pull --base

