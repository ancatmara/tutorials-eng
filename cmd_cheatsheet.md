The **command line interface (CLI)** is a text interface for your computer. It's a program that takes in commands, which it passes on to the computer's operating system to run. From the command line, you can navigate through files and folders on your computer and run applications. When you open a CLI, it shows you your current location in the file system (for example, `ancatmara@INGEN C:\Users\ancatmara`) and a special symbol that shows you that the CLI is ready to take a command. This symbol is **>** on Windows and **$** on Unix systems.

CLIs "remember" a certain amount of commands that you run during a session, and you can navigate between them using ⇅ arrows: ↑ will get you the previous command you run, and ↓ goes to the next one. Another useful thing is *autocomplete* that helps you avoid typing long paths and filenames: just type the first few letters of a file/directory name you need, press `tab`, and voilà!

The standard CLI  is called `cmd` on Windows and `Terminal` on Linux and Mac OS. As for me, the standard Windows `cmd` is not the most user friendly shell, but there are a few alternatives. For example, [this terminal](https://conemu.github.io/) allows switching between `cmd`, `PowerShell`, `Git bash` or any other CLI in a single app.


## Basic commands in Windows and Unix

|  Action      | Windows        | Linux / MacOS (Bash)|
| ------------- |-------------:| -----:|
| Change directory     | cd | cd |
| Create file    | copy con     | touch|
| Create directory | mkdir  |  mkdir |
| Delete file  | del, erase | rm; rm -rf -- delete folder and all files inside |
| Delete directory    | rmdir      |   rmdir |
| Print message | echo   |  echo |
| Print file contents | type  | cat|
| Copy file     | copy, xcopy | cp |
| Rename file  | ren, rename      |  mv |
| Move file   | move  |  mv |
| Search file | where     |   find, locate |
| Print list of files and directories| dir |  ls, dir |
| Help |   help  |  apropos, man, whatis  |

You can find more useful commands in [this tutorial](https://www.codecademy.com/articles/command-line-commands) on Codecademy.

*** 

**Circumflex** ("^") means "Ctrl" (^C = Ctrl + C) on any system.

^C — break

^S — stop and restart

^I — same as "Tab" key, goes over files and directories

^M — same as Enter.

^H — same as Backspace.

**NB!** Many common shortcuts, like Ctrl+C / Ctrl+V for copy and paste, won't work in standard CLIs! 

## Python

|Command| Action|
|-------| -------:|
|python| Run Python in terminal |
|python <PYTHON_SCRIPT_NAME>| Run Python script|
|python --version| Check Python version|
|pip freeze| See list of installed packagess|
|pip install| Install package|
|pip uninstall| Delete package|
|pip show| See info about package|
|pip search| Search for package (if you don't remember the exact name)|

More on working with `pip` in the [official documentation](https://pip.pypa.io/en/stable/).

If you have Anaconda, you can use its package manager called `conda` (the analogue of `pip`). Here is a nice conda [cheatsheet](https://conda.io/docs/_downloads/conda-cheatsheet.pdf) and [documentation](https://conda.io/docs/index.html).


## Git

Git is a **version control system (VCS)** and a very powerful tool honoured with a few thick textbooks ([here](https://www.oreilly.com/library/view/version-control-with/9781449345037/) is just one example). You'll find some basic commands below.

|Command| Action|
|-------| -------:|
|git clone <LINK>| Clone repository|
|git pull| Pull changes from remote repository|
|git init| Create repository|
|git status| Check status of local changes|
|git add| Add selected files to be tracked|
|git add \*| Add all files to be tracked|
|git rm| Delete files|
|git commit -m "Commit message"| Commit changes; -m is for commit message|
|git push| Push local changes to remote|
|git log| Check log|

You can download git from the [official website](https://git-scm.com/downloads). They also have great multilingual [documentation](https://git-scm.com/book/en/v2), where you can find information on more advanced things like [correcting mistakes](https://git-scm.com/book/en/v1/Git-Basics-Undoing-Things) and [branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
  
**NB!** Git installation for Windows comes with a Bash CLI, which is a useful tool for running [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) commands that aren't supported in Windows `cmd`.

### Authorisation

After you install `git` on your machine, there are two important things to do.

  1. Tell git your username and email.
  
`git config --global user.name "your github login"`

`git config --global user.email "the email you registered with on github.com"`
  
  2. Generate an SSH key on your machine and upload it to GitHub. Using the SSH protocol, you can connect and authenticate to remote servers and services without supplying your username and personal access token at each visit. Here is a nice step-by-step [guide](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/about-ssh) from GitHub.
