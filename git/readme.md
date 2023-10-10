# How to: add a submodule
```
git submodule add <(relative)-path/to/git-project-or-remote-url> <path/to/destination/folder>

git commit -m "Added the submodule to the project."

git push

```

# How to: remove a submodule
See: https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule/36593218#36593218
```
# Remove the submodule entry from .git/config
git submodule deinit -f path/to/submodule

# Remove the submodule directory from the superproject's .git/modules directory
rm -vrf .git/modules/path/to/submodule

# Remove the entry in .gitmodules and remove the submodule directory located at path/to/submodule
git rm -f path/to/submodule
```

# How to: Update Repo Remote URL (after moving the remote Project)
```
# check current remote url
git remote -v

# set new remote url (can be copied from "Clone" button)
git remote set-url origin <new-remote-url-of-git-project>

# check new remote
git remote -v
```

# How to: Revert the last commit (not pushed)
```
# get the commit hash, from the commit you want to revert
git reflog

git revert <git-commit-hash>
```

