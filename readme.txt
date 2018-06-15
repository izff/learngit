This is a new repository.
The main goal of it is to warm up git.

Basic commands:
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

13. git push -u origin master
