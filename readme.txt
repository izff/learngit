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
    git log : with verbose output
