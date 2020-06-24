Git Commands
============

_A more comprehensive list of useful Git commands with organization by task in mind_

___

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git branch -u origin/[branch name]` | Start tracking a branch |
| `git branch -d [branch name]` | Delete a local branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Copy checked out branch to a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |


### Stashing

| Command | Description |
| ------- | ----------- |
| `git stash` | Stash changes in a dirty working directory |
| `git stash save “Your stash message”` | Stash with message |
| `git stash list` | View the list of stashes |
| `git stash show` | Shows the summary of the stash diffs |
| `git stash apply` | Takes the top most stash in the stack and applies it to the repo |
| `git stash pop` | Stash apply but it deletes the stash from the stack after it is applied. |
| `git stash drop` | Deletes the latest stash from the stack |
| `git stash clear` | Remove all stashed entries |
| `git stash branch <name> stash@{1}` | Creates a new branch with the latest stash, and then deletes the latest stash ( like stash pop) |


### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git pull` | Update local repository to the newest commit |
| `git pull --rebase` | Rebase from tracked branch |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git show` | View file changes |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Cleaning Untracked Files

| Command | Description |
| ------- | ----------- |
| `git clean -n` | To see which files will be deleted by git clean |
| `git clean -f` | To force remove all un-tracked files |
| `git clean -f <path>` | To remove a specific file |
| `git clean -fd` | To remove directories |
| `git clean -f -x` | To also remove ignored files |

## Workflows

### Easy Squashing
| Command | Description |
| ------- | ----------- |
| `git reset --soft [SHA]` | Undo commit but leave files unchanged |
| `git add .` | Re-add the files to be tracked |
| `git commit -m "new squashed message"` | Commit with new message |
| `git push --force origin [branch name]` |  Re-push, forcing it to override previous commits |

### Reverting Changes to a File
| Command | Description |
| ------- | ----------- |
| `git checkout [SHA] filename` | Checkout a specific file from a previous commit, repeat with other files if needed |
| `git add .` | Re-add the files to be tracked |
| `git commit -m "new squashed message"` | Commit with new message |
| `git push --force origin [branch name]` |  Repush, forcing it to override previous commits |

___

_A list of useful Git commands_

*If you are interested in Josh's Git aliases, have a look at his `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--
