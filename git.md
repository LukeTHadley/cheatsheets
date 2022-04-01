# Git Cheatsheat

### Configuring git credentials on a new system

```shell
$ git config --global user.name "<NAME>"
$ git config --global user.email "<EMAIL>"
$ git config --global credentials.helper store
```

### New Repo / Assigning A Repo

Add a repo url to your git directory
```shell
$ git remote add <name> <url>
```

Set and rename the branch you are currently on
```shell
$ git branch -M <branch-name>
```

Set the upstream branch for branch name referenced with
```shell
$ git push -u <remote> <branch-name>
```

### Removing A Repo

Remove a repo from your computer by running

```shell
$ git remote remove <name>
```

View what repos are assigned using
```shell
$ git remote `-v` for verbose mode
```

### Branches

Note! Sometimes all branch information is not downloaded, e.g. the repo was downloaded with a `Shallow Clone`.

See [Shallow Clone](https://github.com/LukeTHadley/cheatsheets/blob/main/git.md#shallow-clone) information.

#### Showing branches

```shell
$ git branch # Branch you are in
$ git branch -a # All branches (local and remote)
$ git branch -l # All local branches
$ git branch -r # All remote branches
```

#### Switching Branches

Switch to a branch with

```shell
$ git checkout branch-name
```
#### Creating New Branches

Create a new branch with
```shell
$ git checkout -b new-local-branch-name origin/branch-name`
```

Then set the upstream branch for branch name referenced with
```shell
$ git push -u <remote> <branch-name>
```

### Shallow Clone

When you clone a repository normally, you download all information regarding previous revisions of every file, entier log history, etc...

This can be useful for repos with a large file size

Clone a repo with no revision history, no previous log information, branch information and more using:

```shell
$ git clone <repo> --depth=1
```

But if you want all remote branch info (which you probably do to work on all the branches), really you want to do this:

```shell
$ git clone <repo> --depth=1 --no-single-branch
```

Sometimes you shallow clone a repo but realise you need more info; so you want to `unshallow` a repo. Do this using:

```shell
$ git fetch --unshallow
```

### Gitignore

Useful site for auto-creating `.gitignore` files can be found [here](https://www.toptal.com/developers/gitignore).