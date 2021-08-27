# Git

Git is a **version control system (VCS)** and a very powerful tool honoured with a few thick textbooks ([here](https://www.oreilly.com/library/view/version-control-with/9781449345037/) is just one example). You'll find some basic commands below.

You can download git from the [official website](https://git-scm.com/downloads). They also have great multilingual [documentation](https://git-scm.com/book/en/v2), where you can find information on more advanced things like [correcting mistakes](https://git-scm.com/book/en/v1/Git-Basics-Undoing-Things) and [branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell).
  
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

