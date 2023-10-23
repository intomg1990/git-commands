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

### Dealing with remote

* `git remote add <name> <URL>` -> add remote repo from URL and name it.
* `git remote -v` -> list the name of remote repos followed by their adress.
* `git fetch <remote>` -> download all the data from the remote repo, however it does **not** merge you main branch with remote main branch.
* `git pull` -> as above but merge into local branch. 
* `git remote rename <old_name> <new_name>` -> rename the remote repo.
* `git remote remove <remote>` -> lose track and erase remote repo reference. 
* `git push origin <tag_name>` -> push the tag attached to a commit also to remote repo.

### Branching

`git branch <branch_name>` -> **create** a new branch, however does **not** change to it. This creates a new pointer to the commit you are currently on.
`git checkout <branch_name>` -> switch to an existing branch.

## Observations:

* If you use `git diff`, but you have already staged all the files, you get no output.
* `git mv` is a substitute for bash `mv` and it is faster.
* Puting a string after the `git clone http://path_to_remote_repo <name_dir>` copies the repository to a new directory with the name of the string.
* The `HEAD` pointer points to the branch you are currently on.


