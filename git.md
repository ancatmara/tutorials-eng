# Git

Git is a **version control system (VCS)** and a very powerful tool honoured with a few thick textbooks ([here](https://www.oreilly.com/library/view/version-control-with/9781449345037/) is just one example). You can download git from the [official website](https://git-scm.com/downloads). They also have great multilingual [documentation](https://git-scm.com/book/en/v2), where you can find information on more advanced things like [correcting mistakes](https://git-scm.com/book/en/v1/Git-Basics-Undoing-Things) and [branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell).

### Git working areas
![](./img/areas.png)

### Git project lifecycle
![](./img/lifecycle.png)
  
**NB!** Git installation for Windows comes with a Bash CLI, which is a useful tool for running [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) commands that aren't supported in Windows `cmd`.

## Authorisation

After you install `git` on your machine, there are two important things to do.

  1. Tell git your name and email.
  
`git config --global user.name "your name / github login"`

`git config --global user.email "the email you registered with on github.com"`
  
  2. Generate an SSH key on your machine and upload it to GitHub. Using the SSH protocol, you can connect and authenticate to remote servers and services without supplying your username and personal access token at each visit. Here is a nice step-by-step [guide](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/about-ssh) from GitHub.

## Basic commands

|Command| Action|
|-------| -------:|
|git init| Create a local repository|
|git clone <LINK>| Clone a repository|
|git pull| Pull changes from a remote repository|
|git status| Check the status of local changes|
|git add| Add selected files to be tracked|
|git add \*| Add all files to be tracked|
|git rm| Delete files|
|git commit -m "Commit message"| Commit changes; -m is for commit message|
|git push| Push local changes to remote|
|git log| Check log|
  
  
## Correcting mistakes
  
One of the common undos takes place when you commit too early and possibly forget to add some files, or you mess up your commit message. If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the `--amend` option.
  
`git commit --amend -m "Commit message"`
  
Create a commit, opposite to the last one. This is **safe**.
  
`git revert HEAD`

Reset commit history to a specific commit. This is **dangerous**!

`git reset --hard <commit id>`
  

### Untracking files without deleting them
  
`git rm --cached <FILE_NAME>`
 
 Example: 
`git rm --cached siteconfig.json`

### Renaming files 
  
Git doesn’t explicitly track file movement. Under the hood, renaming a file is two operations: deleting one file and adding another, identical one with a different name.
                             
`echo "Hello world\!" > test.txt`
  
`git mv test.txt hello.txt`

### Unstaging staged files
  
These two commands do **the same**.
  
`git reset HEAD <filename>`
  
`git restore --staged <filename>`

### Unmodifying a modified file
  
These two commands do **the same**.
  
`git checkout -- <filename>`
  
`git restore <filename>`

## Remotes
Remote repositories are versions of your project that are hosted on the Internet or network somewhere. You can have several of them, each of which generally is either read-only or read/write for you.

### Check remotes 
`git remote`
  
`git remote -v`
  
 `git remote show <REMOTE_NAME>/<BRANCH_NAME>`

 ### Adding remotes
`git remote add <REMOTE_NAME> <REMOTE_URL>` 

#### Example 
  `git remote add elexis-eu https://github.com/elexis-eu/lexonomy.git`
 
### Renaming remotes
  `git remote rename <OLD_REMOTE_NAME> <NEW_REMOTE_NAME>`
  
 #### Example 
`git remote rename elexis-eu elexis`
 
  
 ### Getting changes from remotes
`git fetch <REMOTE_NAME>`
  
`git fetch --all`

 ### Deleting remotes
 
`git remote remove <REMOTE_NAME>`

 ### Changing remote urls
`git remote set-url origin <NEW_URL>`

 ### The magic of _git pull_ and _git push_
`git pull` = `git fetch origin` + `git merge`
  
`git push` = `git push origin master`

## Branching

A branch in Git is simply a lightweight movable pointer to one of these commits. The default branch name in Git is master. As you start making commits, you’re given a master branch that points to the last commit you made. Every time you commit, the master branch pointer moves forward automatically.
  
Topic branches are useful in projects of any size. A topic branch is a short-lived branch that you create and use for a single particular feature or related work.
  
 ![](./img/lr-branches-2.png)
  
 ![](./img/lr-branches-1.png)
  
 ### Checking branches
`git branch -vv`
  
 ### Creating branches
Create a new branch.
  
`git branch <BRANCH_NAME>`
  
 Move to this branch.
  
`git checkout <BRANCH_NAME>` 
  
 There is a shortcut for it.
  
`git checkout -b <BRANCH_NAME>` = `git branch <BRANCH_NAME>` + `git checkout <BRANCH_NAME>` 

 Add a new branch to the remote. This moves HEAD to point to this branch.
  
`git push origin <BRANCH_NAME>`
 
Get a new local branch from the remote.
 
`git checkout <REMOTE_BRANCH_NAME>` = `git checkout --track origin/<REMOTE_BRANCH_NAME>` =  `git checkout -b <LOCAL_BRANCH_NAME> origin/<REMOTE_BRANCH_NAME>` 

 #### Example 
`git checkout -b serverfix origin/serverfix` = `git checkout --track origin/serverfix` = `git checkout serverfix`

### Merging
 
Checkout to a master/main branch (the one, **into** which you'd like to merge another branch).
  
`git checkout master`
 
 Merge a branch and delete it after merging.
  
`git merge <BRANCH_NAME>`
  
`git branch -d <BRANCH_NAME>`
  
 Occasionally, this process doesn’t go smoothly. If you changed the same part of the same file differently in the two branches you’re merging, Git won’t be able to merge them cleanly, and you'll have to resolve conflicts manually in a text editor. A good habit that helps to avoid resolving extra merge conflicts is to do a `git pull` before you commit something.

### Renaming branches
`git branch --move <OLD_BRANCH_NAME> <NEW_BRANCH_NAME>`

#### Example
  
Change the name locally.
  
`git branch --move master main`
 
Change the name of the remote branch.
  
`git push --set-upstream origin main`
 
 Delete the remote branch with an old name.
`git push origin --delete master`

## Rebasing

With the rebase command, you can take all the changes that were committed on one branch and replay them on a different branch.

Often, you’ll do this to make sure your commits apply cleanly on a remote branch — perhaps in a project to which you’re trying to contribute but that you don’t maintain. In this case, you’d do your work in a branch and then rebase your work onto origin/master when you were ready to submit your patches to the main project. That way, the maintainer doesn’t have to do any integration work — just a fast-forward or a clean apply.
  
 `git checkout <BRANCH_NAME>`
  
`git rebase master`

## Logs

`git log -p -3`
  
`git log --pretty=short`
  
### Visualising branch topology

https://stackoverflow.com/questions/1838873/visualizing-branch-topology-in-git 

`git log --graph --decorate --oneline`

`git log --graph --full-history --all --pretty=format:"%h%x09%d%x20%s"`

With colors (if your shell is Bash):

`git log --graph --full-history --all --color --pretty=format:"%x1b[31m%h%x09%x1b[32m%d%x1b[0m%x20%s"`
