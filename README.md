Git Commands
============

_A more comprehensive list of useful Git commands with organization by task in mind_

___

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/<username>/<repository-name>.git` | Create a local copy of a remote repository |


### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add <file-name.txt>` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "<commit message>"` | Commit changes |
| `git rm -r <file-name.txt>` | Remove a file (or folder) |
| `git show --name-only` | Print the files that changed since the last commit |
| `git diff --name-only HEAD HEAD~1` | Print the files that changed since the last commit |
| `git diff HEAD HEAD~1` | Print the changes that were made since the last commit |


### Undoing Commits

| Command | Description |
| ------- | ----------- |
| `git reset --hard` | Discard all local changes to all files permanently |
| `git reset --soft HEAD~1` | Undo the Last 1 Commit, preserving changes |
| `git reset --hard HEAD~1` | Undo the Last 1 Commit, undoing changes permanently |
| `git reset --hard <commit_SHA>` | Undo all the commits up to the commit at that SHA |


### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch <branch name>` | Create a new branch |
| `git branch -m <old branch name> <new branch name>` | Rename a local branch |
| `git branch -u origin/<branch name>` | Start tracking a branch |
| `git branch -D <branch name>` | Delete a local branch |
| `git push origin --delete <branch name>` | Delete a remote branch |
| `git switch -c <new local branch name>` | Copy checked out branch to a new branch and switch to it |
| `git checkout -b <new local branch name> origin/<remote branch name>` | Clone a remote branch and switch to it |
| `git checkout <branch name>` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- <file-name.txt>` | Discard changes to a file |
| `git merge <branch name>` | Merge a branch into the active branch |
| `git merge <source branch> <target branch>` | Merge a branch into a target branch |
| `git pull <separate_git_remote_url> <branch> --allow-unrelated-histories` | Pull a branch from different repo |


### Stashing

| Command | Description |
| ------- | ----------- |
| `git stash` | Stash changes in a dirty working directory |
| `git stash save "Your stash message"` | Stash with message |
| `git stash show` | Shows the summary of the stash diffs |
| `git stash list` | View the list of stashes |
| `git stash apply` | Takes the most recent stash in the stack and applies it to the repo |
| `git stash apply stash@{stash_list_number}` | Takes the specific stash and applies it to the repo |
| `git stash pop` | Stash apply but it deletes the stash from the stack after it is applied. |
| `git stash drop` | Deletes the latest stash from the stack |
| `git stash clear` | Remove all stashed entries |
| `git stash branch <name> stash@{1}` | Creates a new branch with the latest stash, and then deletes the latest stash ( like stash pop) |


### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin <branch name>` | Push a branch to your remote repository |
| `git push -u origin <branch name>` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git pull` | Update local repository to the newest commit |
| `git pull --rebase` | Rebase from tracked branch |
| `git pull origin <branch name>` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/<username>/<repository-name>.git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/<username>/<repository-name>.git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git show` | View file changes |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff <source branch> <target branch>` | Compare branches |
| `git diff <branch> <target_branch>:<outside_remote_repo_url>` | Compare branch to a branch on another repo |
| `git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative` | Git logs with graphs and color |
| `alias gitlg="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative"` | Create a gitlg shortcut in the bash shell for git logs with graphs and color, can be added to the end of your .bashrc |


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
| Step | Command | Description |
| ------- | ------- | ----------- |
| 1 | `git reset --soft <SHA>` | Undo commit but leave files unchanged |
| 2 | `git add .` | Re-add the files to be tracked |
| 3 | `git commit -m "new squashed message"` | Commit with new message |
| 4 | `git push --force origin <branch name>` |  Re-push, forcing it to override previous commits |

### Reverting Changes to a File
| Step | Command | Description |
| ------- | ------- | ----------- |
| 1 | `git checkout <SHA> filename` | Checkout a specific file from a previous commit, repeat with other files if needed |
| 2 | `git add .` | Re-add the files to be tracked |
| 3 | `git commit -m "new squashed message"` | Commit with new message |
| 4 | `git push --force origin <branch name>` |  Repush, forcing it to override previous commits |

### Git Pull Push
| Step | Command | Description |
| ------- | ------- | ----------- |
| 1 | `git branch --set-upstream-to=origin/branch_name branch_name` | Set upstream to origin/branch_name, fixes "git pull" |
| 2 | `git config --global push.default matching` | Set push without parameters default, now you can just "git push"  |

___

_A list of useful Git commands_

*If you are interested in Josh's Git aliases, have a look at his `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--
