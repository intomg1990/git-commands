## Do not forget to add the following files:

* CONTRIBUTING.md
* README.md
* .gitignore

## Useful commands:

### Local changes

Pre commit, changes:
* `git status` -> show the status of files for commit (working dir OR staged files)
* `git diff` -> the difference between working dir and last commit (?).
* `git diff --staged` -> the difference between staged and last commit
* `git log` -> show the commits of the repo in descending chronological order. Options:
    * `-n` show `n` previous commits. 
    * `--patch` show the differences *in relation* to previous commit.
    * `--stat` show only the modifications in number of lines. 
    * `--no-merge` does **not** show the merge commits.
    * `--oneline --decorate --graph --all` try to draw some schematics of branching.
    * `--decorate` -> show the `HEAD` pointer.

<br />

Dealing with commits:
* `git commit --ammend` -> fix last commit, both forgotten files and wrong commit message.
* `git restore --staged <file>` -> unstage file.
* `git restore <file>` -> modify unstaged file to the previous commit (snapshot). 
    * Deprecated:
        * `git reset HEAD <file>` -> unstage file.
        * `git checkout -- <file>` -> modify unstaged file to the previous commit (snapshot).
* `git tag -a <name_of_tag> -m "message_for_tag"` -> create a *tag for a commit* (last one) and attach a message to it. 
* `git tag -a <name_of_tag> -m "message_for_tag" <check_sum>` -> as above, but attach tag to commit with `<check_sum>`.

<br />

Other:
* `git config --global alias.<new_comand> '<old_command>'` -> create an alias to an **git** command.

### Branching

* `git switch <branch_name>` -> switch to pre existing branch (newer version of `git checkout`).
* `git branch <branch_name>` -> **create** a new branch, however does **not** change to it. This creates a new pointer to the commit you are currently on.
* `git checkout <branch_name>` -> switch to an existing branch.
* `git branch` -> list branches of repo.
* `git branch -v` -> as above, adding message of last commit.
* `git branch -all` -> list all branches, including remote repo branches.
* `git merge <branch_name>` -> merge `<branch_name>` into the current branch.
* `git rebase <branch_name>` -> put current branch onto `<branch_name>`.
* Renaming branch:
    * `git branch --move <old_name> <new_name>` -> rename the name of the branch **locally**.
    * `git push --set-upstream <name_remote_repo> <new_name>` -> push new renamed branch to remote. 
    * `git push origin --delete <old-name>` -> remove branch `<old_name>` from remote repo. 

### Dealing with remote

* `git remote add <name> <URL>` -> add remote repo from URL and name it.
* `git remote -v` -> list the name of remote repos followed by their adress.
* `git fetch <remote>` -> download all the data from the remote repo, however it does **not** merge your branch with remote branch.
* `git checkout --track <remote_repo>/<remote_branch>` -> download a remote repo branch and keep track of it.
* `git branch -u <remote>/<branch>` -> set the current branch to track the `<remote>/<branch>` of remote repo.
* `git remote rename <old_name> <new_name>` -> rename the remote repo.
* `git remote remove <remote>` -> lose track and erase remote repo reference. 
* `git push <remote_name> <tag_name>` -> push the tag attached to a commit also to remote repo.
* `git push <remote_name> <branch_name>` -> push *only* the `<branch_name>` branch to the remote.
* `git push <remote_name> --all` -> push all branches to remote.
* `git push <remote_name> --mirror` -> push all branches and tags to remote.


## Observations:

* If you use `git diff`, but you have already staged all the files, you get no output.
* `git mv` is a substitute for bash `mv` and it is faster.
* Puting a string after the `git clone http://path_to_remote_repo <name_dir>` copies the repository to a new directory with the name of the string.
* The `HEAD` pointer points to the branch you are currently on.
* There are the following *subtle* differences in git to pay attention to:
    * The difference between `git pull` e `git fetch` is that `git pull` try to merge into the local repo the new commits related to the remote repo. It is usually *safer* to use `git fetch`.
    * The difference between `git merge` and `git rebase` is that only in how the resultint history of commits are done. `git rebase` makes it looks like it was a linear development history. The merge process you merge a different branch in the current branch you are on. The rebase process you rebase from a current branch to a target branch.

