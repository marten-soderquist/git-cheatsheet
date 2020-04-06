# Git Cheat Sheet

## Setting up

### Installation
Download and install Git [https://git-scm.com/](https://git-scm.com/)

### Configuring user details

Commits in Git always include the commiters name and email. To set these variables to something meaningful use:

`git config --global user.name "Your Real Name"`\
`git config --global user.name "your@email.here"`

This sets these two variables globally for the system. This name and email is then included with each commit you make in every repository on the system.

These variables can also be overridden for each repository, e.g. running\
`git config user.email "..."`\
changes your email for commits **in that repository!**

---

## Getting started

There are two main ways to get started, either cloning an existing repository or creating a new of your own. A repository is a collection of one to several branches for a project with the commit history included.

### Cloning an existing repository

Use the command `git clone <link to repository>` to clone the contents of that repository to your computer to new folder from your current. For example, to clone the repository `another-repo` use:\ `git clone another-repo`\
This will download the files in the remote repository, as well as all brnaches that exist into the folder `<your-current-location>/another-repo`\
This also automatically sets up the remote repository as a remote. 

### Creating a new repository

Run `git init` in the folder you want to source control.

For example, if the command is run in the folder `/home/UserGuy/` this puts everything in the folder to be tracked with Git. In practice this creates the folder `/user/UserGuy/.git` which contains metadata used by Git. **You should never touch this folder.** 

#### Creating a `.gitignore` file

Some files created in a repository you will typically not want to be visible to Git, such as editor specific temporary files. To specify which these are create the text file `.gitignore` in the root folder of the repository. In this file you can specify filenames and patterns to ignore. See [the documentation](https://git-scm.com/docs/gitignore). You *do* want to keep `.gitignore` under version control. There are templates for different languages available, e.g. there is one for [MatLab here](https://github.com/github/gitignore/blob/master/Global/MATLAB.gitignore)

*Note that Mathworks also recommends adding a `.gitattributes` to avoid corrupting binary files, see [here](https://se.mathworks.com/help/matlab/matlab_prog/set-up-git-source-control.html) for more information.*

---
## Daily use

### Check status and view logs

Check the curren status of your working branch with `git status`. This will show which files have changed.

View the history with `git log`.

### Branches
Always do work on a separate branch. This keeps your work separate from others.

To create a new branch and switch to it use `git checkout -b <new branch name>`

To see what branches you have use `git branch`.

### View changes

To view what changes have been made to a file use the command:\
`git diff <filename>`

### Commiting changes

Commiting changes is a two step process. First stage (add) the changed files you want to include in your commit.

`git add <file1> <file2> ...`  (or `git add .` to add all changed files.)

#### Commit philosophy

- Keep commits small
  * If you have several files that have changed but the changes are not related to each other then split then make several commits. 
- Leave a relevant commit message
  * This makes changes easier to find later.


---
## Terminology






 