## Create the repository

Initially, the repository you create in Github is going to be empty without any code in it. That's okay because you will start adding some files to it soon. This Github repository will be the central repository for your files, which means that others can access that repository if you give them permission. After creating a repository, you'll copy a version to your local system—that way you can update it from one repo, then transfer those changes to the other.

## Initializing a new repository: `git init`

To create a new repo, you'll use the `git init` command. `git init` is a one-time command you use during the initial setup of a new repo. Executing this command will create a new .git subdirectory in your current working directory. This will also create a new master branch.

## Copy your Git repository and add files

Now that you have a place to add and share your space station files, you need a way to get to it from your local system. To set that up, you want to copy the Github repository to your system. Git refers to copying a repository as "cloning" it. When you clone a repository, you create a connection between the Github server (which Git knows as origin) and your local system.

*Clone your repository to your local system*

* `git clone`

## git config

The git config command is a convenience function that is used to set Git configuration values on a global or local project level. These configuration levels correspond to .gitconfig text files. Executing git config will modify a configuration text file. We'll be covering common configuration settings like email, username, and editor. We'll discuss Git aliases, which allow you to create shortcuts for frequently used Git operations. Becoming familiar with git config and the various Git configuration settings will help you create a powerful, customized Git workflow.

* Display email of git account
  * `git config user.email`
* Git config levels and files:
  * --local
  * --global
  * --system
* **git alias**

  ```unix
  git config --global alias.co checkout
  git config --global alias.br branch
  git config --global alias.ci commit
  git config --global alias.st status
  ```

## Git overview

Developing a project revolves around the basic edit/stage/commit pattern. First, you edit your files in the working directory. When you’re ready to save a copy of the current state of the project, you stage changes with `git add`. After you’re happy with the staged snapshot, you commit it to the project history with `git commit`. The `git reset` command is used to undo a commit or staged snapshot.

In addition to `git add` and `git commit`, a third command `git push` is essential for a complete collaborative Git workflow. `git push` is utilized to send the committed changes to remote repositories for collaboration. This enables other team members to access a set of saved changes.

## **Check** the status of the file

The git status command displays the state of the working directory and the staged snapshot.

* `git status`

## git add

The `git add` command adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit. However, `git add` doesn't really affect the repository in any significant way—changes are not actually recorded until you run `git commit`.
**`git add` needs to be called every time you alter a file**

* Stage all of the change files to a commit
  * `git add -A`
  * `git add .`
* Stage all changes in \<directory\> for the next commit
  * `git add -p`
  * `git add folderpath`
* Stage a file that you missed to stage in your last commit
  * `git add filename`
  * `git commit -ammend`

## Git commit

The git commit command captures a snapshot of the project's currently staged changes. Committed snapshots can be thought of as “safe” versions of a project—Git will never change them unless you explicitly ask it to. Prior to the execution of git commit, The git add command is used to promote or 'stage' changes to the project that will be stored in a commit. These two commands `git commit` and `git add` are two of the most frequently used.

* Commit
  * `git commit -m "commit message"`
* Add and commit:
  * `git commit -am "commit message"`
* Modify the last commit, instead of creating a new commit, staged changes will be added to the previous commit.
  * `git commit --ammend`
  * `git commit --ammend -m "an updated commit message`
  * `--no-edit` allow you to make the amendment to your commit without changing its commit message.
    * `git commit --ammend --no-edit`

## git rebase

To modify older or multiple commits, you can use `git rebase`to combine a sequence of commits into a new base commit. In standard mode, `git rebase` allows you to literally rewrite history — automatically applying commits in your current working branch to the passed branch head. Since your new commits will be replacing the old, it's important to not use `git rebase` on commits that have been pushed public, or it will appear that your project history disappeared.

In these or similar instances where it's important to preserve a clean project history, adding the `-i` option to `git rebase` allows you to run rebase interactive. This gives you the opportunity to alter individual commits in the process, rather than moving all commits.

## Comparing changes with `git diff`

Diffing is a function that takes two input data sets and outputs the changes between them. `git diff` is a multi-use Git command that when executed runs a diff function on Git data sources. These data sources can be commits, branches, files and more.The `git diff` command is often used along with `git status` and `git log` to analyze the current state of a Git repo.

* `git diff` will show you any uncommitted changes since the last commit
* Comparing two branches
  * `git diff branch1..other-feature-branch`
* Comparing files from two branches
  * `git diff master new_branch ./diff_test.txt`

## git stash

## .gitignore

ignored - a file which Git has been explicitly told to ignore.

## `git status`

The `git status` command displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. Status output does not show you any information regarding the committed project history. For this, you need to use `git log`.

## git log

The `git log` command displays committed snapshots. It lets you list the project history, filter it, and search for specific changes. While `git status` lets you inspect the working directory and the staging area, `git log` only operates on the committed
history.

* `git log`
* Limit the number of commits by . For example, `git log -n 3` will display only 3 commits.
  * `git log -n`
* Condense each commit to a single line. This is useful for getting a high-level overview of the project history.
  * `git log oneline`
* Along with the ordinary `git log` information, include which files were altered and the relative number of lines that were added or deleted from each of them.
  * `git log --stat`
* Display the patch representing each commit. This shows the full diff of each commit, which is the most detailed view you can have of your project history.
  * `git log -p`
* Search for commits by a particular author. The  argument can be a plain string or a regular expression.
  * `git log --author=""`
* Search for commits with a commit message that matches , which can be a plain string or a regular expression.
  * `git log --grep=""`
* Show only commits that occur between  and . Both arguments can be either a commit ID, a branch name, HEAD, or any other kind of revision reference.
  * `git log ..`
* The --graph flag that will draw a text based graph of the commits on the left hand side of the commit messages. --decorate adds the names of branches or tags of the commits that are shown. --oneline shows the commit information on a single line making it easier to browse through commits at-a-glance.
  * `git log --graph --decorate --oneline`

## git reflog

Reflog is like a trump card. It is useful when you have messed up to a point that none of the above commands works. Reflog shows you a list of all the things you have done in a project so far. Then you can go to any point in the past and fix the problem.

 `git reflog`

## git fetch

The git fetch command downloads commits, files, and refs from a remote repository into your local repo. Fetching is what you do when you want to see what everybody else has been working on.

* `git fetch --all`
* `git fetch --dry-run`

## git push

The git push command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo. It's the counterpart to git fetch, but whereas fetching imports commits to local branches, pushing exports commits to remote branches. Remote branches are configured using the git remote command. Pushing has the potential to overwrite changes, caution should be taken when pushing.

* Push the specified branch to , along with all of the necessary commits and internal objects.
  * `git push <remote> <branch>`
* force the push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing.
  * `git push <remote> --force`
* Push all of your local branches to the specified remote.
  * `git push <remote> --all`

## git pull

The `git pull` command is used to fetch and download content from a remote repository and immediately update the local repository to match that content. Merging remote upstream changes into your local repository is a common task in Git-based collaboration work flows. The `git pull` command is actually a combination of two other commands, `git fetch` followed by `git merge`. In the first stage of operation `git pull` will execute a `git fetch` scoped to the local branch that HEAD is pointed at. Once the content is downloaded, `git pull` will enter a merge workflow. A new merge commit will be-created and HEAD updated to point at the new commit.

* Fetch the specified remote’s copy of the current branch and immediately merge it into the local copy.
  * `git pull <remote>`
* fetches the remote content but does not create a new merge commit.
  * `git pull --no-commit <remote>`
* pull Instead of using git merge to integrate the remote branch with the local one, use `git rebase`.
  * `git pull --rebase <remote>`
* Gives verbose output during a pull which displays the content being downloaded and the merge details.
  * `git pull --verbose`

## git branch

A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, staging area, and project history. New commits are recorded in the history for the current branch, which results in a fork in the history of the project.

* List all of the branches in your repository.
  * `git branch`
* Delete the specified branch. This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.
  * `git branch -d branchname`
* Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.
  * `git branch -D`
* Rename the current branch to
  * `git branch -m`
* List all remote branches.
  * `git branch -a`
* Create a branch using the following command:
  * `git branch branch_name`

## Git Checkout

In Git terms, a "checkout" is the act of switching between different versions of a target entity. The git checkout command operates upon three distinct entities: files, commits, and branches.

* checkout existing branch
  * `git checkout branch_name`
* Checkout and create new branch
  * `git checkout -b branch_name`

## Git merge

Merging is Git's way of putting a forked history back together again. The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.

## Merge conflicts

**git reset --hard\<commit\>**
**git reset --hard origin/master**

## Autocorrect

To enable autocorrect run this command in your terminal
`git config --global help.autocorrect 1`

## Switching back and forth between two branches

* `git checkout -branch_name`
  
## Check Commit History

* This will show you all the commit messages, authors name, and email, as well as the date and time they were committed.
  * `git log`
* If you want to see only the diff introduced in each commit
  * `git log -p`
* To exit git log, type “q” or “z”. Or type “h” to seek for help.

## See where all your branches are tracking from

* To understand where a code that you push will land, or to know where exactly a piece is coming from when you perform a git pull, it is very important to know which branches are pointing where.
Run the following command to see where all your branches are tracking from:
  * `git branch -vv`

## Pinpoint exactly when in the history a commit was made

* Let’s say you have just discovered a bug, and you want to change the code which is causing it. You got to find out the point in history a commit was made so that you can fix it in that commit. Here’s a command that helps you quickly achieve that
  * `git bisect`
  * `git bisect [help|start|bad|good|new|old|terms|skip|next|reset|visualize|view|replay|log|run]`
  
## Undo a git add

* If you have accidentally added a wrong file to the repo, or have added a file in a wrong directory, you can undo it.
* **If you haven’t committed yet**
  * `git reset /path/filename`
* **If you have already committed the code** This will undo the commit, remove the particular file, delete the file from the repo and add a new commit in its place.
  * `git reset --soft HEAD~l`
  * `git reset /path/filename`
  * `git rm /path/filename`
  * `git commit`
* If you want to undo whole uncommitted branch that you have just added.This is the command to reset the whole branch to as it was before running git add
  * `git reset`

## Revert repo to a previous commit

* If you have messed up completely in your last one or more commits, and one to go back to a previous commit, you can do so easily, in fact, ultimately this is the main purpose of Git.
  * `git checkout <SHA>`
  * SHA is the Hash or unique ID of the commit you want to revert to. To get the hash of the commit you want to run a git log.
  * Once you are on that commit you want you simply run any command you want.And to go back to the present state, you can check out the branch you were on previously.

## Undo a GIT merge

* Sometimes you mess up badly while trying to merge few branches, and want to undo the merge.
* Because merge is a commit which points the HEAD to a specific commit, we can undo the merge commit running the command
  * `git revert HEAD`
* If you want to specify the exact merge commit that you want to undo, using the following command
  * `git revert -m l <SHA>`
  * SHA is the Hash of the merge you want to undo, and “-m 1” indicates we want to keep the parent of the merge.

## Delete a Git branch locally and remotely

Delete the entire branch and start everything from a clean branch.

* To delete a branch on your local repo:
  * `git branch --delete <branchname>`
  * `git branch --delete --force <branchname>`
* To delete a branch remotely and to create a new branch to work on
  * `git push origin --delete <branchname>`
  * `git checkout -b <branchname>`

## Change branch name

If you have typed a branch name wrong you can fix it too later on.

* If you haven’t pushed it yet, run this
  * `git branch -m <Incorrect Branchname> <Correct Branchname>`
* To change a remote branch name you need to first delete the branch and then push the new one
  * `git push origin --delete <Incorrect Branchname>`
  * `git push origin <Correct Branchname>`

## Autostash

Let’s say you are working on a branch and you just find out your colleague has pushed some changes to the same branch, but if you are not ready to pull those changes yet, then you have to stash whatever you are working on, then fetch, then rebase and then apply for a stash.

You can automate it. What you have do is just enable autostash, which automatically stashes your work and then applies the stash after rebase is done. To enable autotash, type this into your terminal -

* `git config --global rebase.autoStash true`

### Refrences

* <https://medium.com/@gitship/15-git-hacks-to-save-your-life-as-a-developer-aa8808846dbb>
* <https://www.atlassian.com/git/tutorials>
