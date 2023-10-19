### Do not forget to add the following files:
* CONTRIBUTING.md
* README.md
* .gitignore

## Useful commands:

### Local changes

* `git diff` -> the difference between working dir and the staged area
* `git diff --staged` -> the difference between staged and last commit
* `git log` -> show the commits of the repo in descending chronological order. Options:
    * `-n` show `n` previous commits. 
    * `--patch` show the differences *in relation* to previous commit.
    * `--stat` show only the modifications in number of lines. 
    * `--no-merge` does **not** show the merge commits.
* `git commit --ammend` -> fix last commit, both forgotten files and wrong commit message.
* `git restore --staged <file>` -> unstage file.
* `git restore <file>` -> modify unstaged file to the previous commit (snapshot). 
* Deprecated:
    * `git reset HEAD <file>` -> unstage file.
    * `git checkout -- <file>` -> modify unstaged file to the previous commit (snapshot).

### Dealing with remote
* `git remote add <name> <URL>` -> add remote repo from URL and name it.
* `git remote -v` -> list the name of remote repos followed by their adress.
* `git fetch <remote>` -> download all the data from the remote repo, however it does **not** merge you main branch with remote main branch.
* `git pull` -> as above but merge into local branch. 
* `git remote rename <old_name> <new_name>` -> rename the remote repo.
* `git remote remove <remote>` -> lose track and erase remote repo reference. 

### Observations:
* If you use `git diff`, but you have already staged all the files, you get no output.
* `git mv` is a substitute for bash `mv` and it is faster.
* Puting a string after the `git clone http://path_to_remote_repo` copies the repository to a new directory with the name of the string.



