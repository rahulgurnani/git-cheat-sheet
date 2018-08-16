# Everyday Commands (for beginners)
I tried to order them in the order you will require to use them.
## Cloning a repository
Usually the first step you take when you start working with git, you clone a remote repository
```
git clone <url-to-repo.git>
```
## Converting local directory to git repository
When you create a repository and want to use version control it :
```
git init
```
## View Branches
Shows all the branches which
```
git branch -vv
```
```
git branch
```
See all the branches 
```
git branch -a
```

## Checkout another branch
```
git checkout <branch-name>
```
In case you want to create a new branch
```
git checkout -b <branch-name>
```

## Status of branch
```
git status
```
## Difference in previous and current
```
git diff
```

## Adding changes for staging
If you want to add all the files, then,
```
git add
```
or in case you want to add a specific file
```
git add <file-path>
```
Many times, it's useful to add changes in patches, also reviewing them on the way (feels more efficient than doing ```git diff``` and then ```git add```)
```
git add -p
```

## Committing changes
Whenever adding a new commit, you can do:
```
git commit -m "Commit message"
```
Frequently, we want to merge our current changes in the previous commit, in that case :
```
git commit --amend
```

## Syncing with master
There are many ways of doing this, but the one that I prefer is, first checkout master, then pull master, then checkout branch and then rebase to master
```
git checkout master
git pull origin master
git checkout <branch-name>
git rebase master
```

TODO : This may result in merge conflicts: 

## Stashing/Avoiding local changes
### Stashing
In case, you may want them in future, good idea to stash them
```
git add <new-files>		# newly added files don't get stashed if you try to stash them without adding
git stash 				# In case you want to stash specific files, you can: git stash push <file-name> , this is available from git 2.13 onwards
```
You can get them back by :
```
git stash pop 			# git stash works like a stack, you can stash and then pop changes 
```

### Avoiding local changes
If you want to get rid of local changes, for modifications to already existing files :

```
git checkout <file-name>
```

## Push to remote
Once we have commited local changes, we would push it to remote
```
git remote -v 		# check which repository is remote pointing to currently, if you find that you need to change it:
# git remote set-url origin https://github.com/USERNAME/REPOSITORY.git 		# update remote repository
git push origin <branch-name> 	# finally, push to remote
```

## See history/logs
We can see commit history,
```
git log 				# logs for the repo
git log <file-name> 	# logs for the specific file
```

## Merging to master
After you raise a pull request, and are going to merge it, usually you end up getting a merge message. If you want to avoid it, you can push to master:
```
git push origin develop:master
```

TODO : Explain detached head : => your head is detached from the branch and you are on some other commit => you are not even on the original branch. => resolve this using “git checkout ..“

# Commands used sometimes/Advanced 
Logs for specific lines
```
git log -L start, end:FileName
```

Diff colors, checkout diff-so-fancy
TODO: Add relevant links

## Diff between 2 branches
Difference in files, master and current branch 
```
git diff --name-status master
```
Actuall diff for file across branches :
```
git diff master:foo foo
```
## Git commit messages, best practices
TODO: read articles and update this.