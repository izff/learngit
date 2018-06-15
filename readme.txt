This is a new repository.
The main goal of it is to warm up git.

Basic commands:
1. git add <filename>

2. git commit -m "..."

3. git diff <filename>

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
Note: check differences between CURRENT and MASTER(HEAD)
