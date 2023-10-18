### Do not forget the following files:
* CONTRIBUTING.md
* README
* .gitignore

### Useful commands:
* `git diff` -> the difference between working dir and the staged area
* `git diff --staged` -> the difference between staged and last commit
* `git log` -> show the commits of the repo in descending chronological order. Options:
    * `-n` show `n` previous commits. 
    * `--patch` show the differences *in relation* to previous commit.
    * `--stat` show only the modifications in number of lines. 
    * `--no-merge` does **not** show the merge commits.

### Observations:
* If you use `git diff`, but you have already staged all the files, you get no output.
* `git mv` is a substitute for bash `mv` and it is faster.
* Puting a string after the `git clone http://path_to_remote_repo` copies the repository to a new directory with the name of the string.


