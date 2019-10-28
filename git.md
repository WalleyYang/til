# Helpful Git Commands

Git Commands
```bash
# Remove untracked files and unstaged changes
$ git clean -df
$ git checkout -- .

# See one line log of last x commits
$ git log --oneline -x

# See changes on staged files
$ git diff --cached

# Reset and sync remote to local repository
$ git fetch origin && git reset --hard origin/master && git clean -f -d

# Reset last commit prior to push
$ git reset --soft HEAD~1

# Merge repositories and retain history
$ git subtree add --prefix=<repository_name> git@github.com:<username/repository_name>.git master

# Revert a file to specific version
$ git checkout commit_version path_to_file/file

# Rename a branch
$ git branch -m <new-branch>

# Show local and remote branches
$ git branch -a

# Local branch to track remote branch
$ git checkout -b <branch_name> -t origin/<branch_name> 

# List files to be pushed
$ git diff --stat --cached remote/<branch>

# See difference between local and remote (files only)
$ git diff --name-only <local branch> origin/<branch>

# Combined (squash last multiple commits) without using rebase or squash
$ git reset --soft HEAD~x
$ git commit -m "New message"

# Rebase (squash multiple commits) on a branch and force push
# Change the pick to squash and leave at least one and save
# Update the commit message
$ git checkout <branch>
$ git rebase -i HEAD~x
$ git push origin branch --force

# Set git username
$ git config --global user.name "My Name"

# Set git email
$ git config --global user.email "email@example.com"

# Set git editor to vim
$ git config --global core.editor vim

# Delete all local branches except for current
$ git branch | grep -v '^*' | xargs git branch -D
```
