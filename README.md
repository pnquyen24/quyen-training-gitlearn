#How to use Git?

--Download Git---
Download: https://git-scm.com/
Check Git version: git --version
Set up Git in local: git config --global user.name, git config --global user.email

A. Git with local repository
- In case, you begin a new project:

1. Create a Git database for project: git init
2. Add files modified, files untracked to prepear commit to Git database at local: git add <file_name> or git add . (add all file)
3. Commit files at staged to Git database:
	+ New commit: git commit -m '<Content commit>'
	+ Combined with last commit: git commit --amend -m '<Content new commit>'

- That is base step to store a project use Git at local.
- Also you use the commands:
	+ git status : view status of files(untracked, unmodified, modified), location of Head
	+ git log or git log --oneline: view log from previous commits.
	+ git diff: view files changes between modified status and unmodified status.
	+ git diff --staged: view files changes between unmodified status(last commit) and staged.

- If you want to update some changes status:
	+ git reset --soft HEAD~1: Delete last commit and back it to staged status.
	+ git reset --hard HEAD~1: Delete last commit forever.
	+ git reset -- . : Delete all file changes at staged and back it to modified status.
	+ git restore <file_name>: Recover file changes from last commit or modified to staged.
	+ git checkout <commit_hashcode> <file_name>: Recover a file from previous commits.

B. Branch in Git
- In case you want to work in a new branch to do not image to main branch

1. Create new branch:
	+ git branch <Branch_name>: Create new brach.
	+ git checkout -b <Branch_name>: Create and move HEAD to new branch.
2. After you create new branch, you can do your git work.

- Also you use the commands:
	+ git branch: check which branch is Head in?
	+ git checkout <Branch_name> or git swicth <Branch_name>: move HEAD back and forth between branches.
	+ git checkout <Commit_HashCode> : move HEAD back to <Commit_HashCode>
	+ git merge <Branch_to_merge> : merge file changes in HEAD branch with branch others order Time
	+ git rebase <Branch_to_merge> : merge file changes in HEAD branch with branch others make sub-branch into base of HEAD brach
	+ git branch -d <branch_name> : Delete a branch.

- When merge more branches work on a file will be conflicted.
	+ git mergetool: remove conflict
		+ :diffg RO: remove changes in sub branch
		+ :diffg RE: remove changes in main branch
		+ :diffg BA: remove all save file with none changes

C. Git with remote repository

- To do work with remote repository, the first we need create new repository in remote and connecting local repository with remote repository
- There are two protocol:
	+ HTTPS: git remote add origin <repo_url>
	+ SSH: git remote add origin <SSH_key>

- After connection 
	+ git push -u origin <branch_name> or git push -u origin --all: upload commit from local repo to remote repo.
	+ git fetch origin : update latest news from remote repo
	+ git pull origin : update commit from remote repo to local repo
- We can perform operations in local repo and push change commit to remote repo again.

D. SSH key on remote server (Github)

- Create new folder to contain (public key and private key).
- Grenerate public key and private key by command: ssh-keygen -t rsa -f id_rsa
- After have key we use public key to set up SSh key for Github.
- Next, set up private SSH for SSH/Git on your machine.
- When use SSH key we need connecting local repository with remote repository.

E. Reference

- HTTPS and SSH Protocol: https://viblo.asia/p/git-dung-https-hay-ssh-eW65Gm9jZDO
- Create SSH key: https://xuanthulab.net/su-dung-github-de-lam-remote-repo-chua-code-du-an.html#sshgith




