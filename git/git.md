# Helpful Git Commands

Git Commands
```bash
# Reset and sync remote to local repository
$ git fetch origin && git reset --hard origin/master && git clean -f -d

# Reset last commit prior to push
$ git reset --soft HEAD~1

# Merge repositories and retain history
$ git subtree add --prefix=repository_name git@github.com:username/repository_name.git master

# Revert a file to specific version
$ git checkout commit_version path_to_file/file

# List files to be pushed
$ git diff --stat --cached remote/branch
```
