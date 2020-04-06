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

Check the curren status of your working branch with `git status`. This will show files that have changed.

View the history with `git log`.

### Branches
Always do work on a separate branch. This keeps your work separate from others.

To create a new branch and switch to it use `git checkout -b <new branch name>`

To see what branches you have use `git branch`.

Switch to an existing branch with `git checkout <branch name>`

### View changes

To view what changes have been made to a file use the command:

`git diff <filename>`

### Commiting changes

Commiting changes is a two step process. First stage (add) the changed files you want to include in your commit.

`git add <file1> <file2> ...`  (or `git add .` to add all changed files.)

Once you are happy with which files are going to be commited (check with `git status`) initiate the commit with `git commit`. This will open a text editor. Which editor can be configured, see [here](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration) for details. Alternatively you can use the option `-m` to specify the commit message on the command line, e.g. `git commit -m "Simple fix"`.

#### Commit philosophy

- Keep commits small
  * If you have several files that have changed but the changes **are not related** to each other then make several commits. 
- Leave a relevant commit message
  * This makes changes easier to find later.

---

## Merging changes

When you have made changes that need to be included in another branch you need to merge them. 
1. Switch to the other, i.e. the branch on which the changes need to be applied. Example, switch from the `<branch-with-changes>` were you have been working.

> `$ git checkout <other-branch>`\
> `Switched to branch <other-branch>`

2. Apply changes on the `<other-branch>`, which is now the branch you are on.
> `$ git merge <branch-with-changes>`

3. If all went well Git will apply the changes and do a fast-forward. If not you have merge conflict and need to manually edit these files. 

More in-depth information can be found [here](https://git-scm.com/docs/git-merge)


## Remote repositories

To update your repository and download remote changes to your computer use `git fetch`. Do not confuse this with the command `git pull`, which **downloads changes and merges them into your current branch**.

View the list of remote repos with `git remote` or `git remote -v` for more details (such as the remote location).
You can manage remotes (add, remove, rename etc) as well. See [here](https://git-scm.com/docs/git-remote) for more.




 