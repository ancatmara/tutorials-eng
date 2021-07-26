**Командная строка** - это такое окошко, куда можно вписать команду, и компьютер ее выполнит. На Windows она называется cmd, на Linux - Terminal. В командной строке вы увидите свое текущее местоположение (например, `ancatmara@INGEN C:\Users\ancatmara`), а на следующей строке - особый символ, который означает, что можно вводить команду. На Windows это **>**, а на Linux - **$**. 

As for me, the standard Windows `cmd` is not the most user friendly shell, but there are a few alternatives. For example, [this terminal](https://conemu.github.io/) allows easily switching between `cmd`, `PowerShell`, `Git bash` or any other shell in a single app.


## Basic commands in Windows and Unix

|  Action      | Windows        | Linux / MacOS |
| ------------- |-------------:| -----:|
| Change directory     | cd | cd |
| Create file    | copy con     | touch|
| Create directory | mkdir  |  mkdir |
| Delete file  | del, erase | rm; rm -rf -- удалить папку и все файлы в ней |
| Delete directory    | rmdir      |   rmdir |
| Print message | echo   |  echo |
| Print file contents | type  | cat|
| Copy file     | copy, xcopy | cp |
| Rename file  | ren, rename      |  mv |
| Move file   | move  |  mv |
| Search file | where     |   find, locate |
| Print list of files and directories| dir |  ls, dir |
| Help |   help  |  apropos, man, whatis  |


**Circumflex** ("^") means "Ctrl" (^C = Ctrl + C) on any system.

^C — break

^S — stop and restart

^I — same as "Tab" key, goes over files and directories

^M — same as Enter.

^H — same as Backspace.

## Python

|Command| Action|
|-------| -------:|
|python| Run Python from terminal |
|python --version| Check Python version|
|pip freeze| See list of installed packagess|
|pip install| Install package|
|pip uninstall| Delete package|
|pip show| See info about package|
|pip search| Search for package (if you don't remember the exact name)|

More on working with `pip` in the [official documentation](https://pip.pypa.io/en/stable/).

If you have Anaconda, you can use its package manager called `conda` (the analogue of `pip`). Here is a nice conda [cheatsheet](https://conda.io/docs/_downloads/conda-cheatsheet.pdf) and [documentation](https://conda.io/docs/index.html).


## Работа с Git

У git очень много возможностей, и про работу с ним написаны толстые книжки (см. пример ниже :D). Здесь перечислены только самые часто употребляемые команды.

|Команда| Значение|
|-------| -------:|
|git clone| Склонировать репозиторий по указанной ссылке|
|git pull| Скачать изменения из удаленного репозитория|
|git init| Создать репозиторий |
|git status| Посмотреть статус изменений|
|git add| Добавить указанные файлы в список отслеживаемых|
|git add \*| Добавить все файлы|
|git rm| Удалить файлы|
|git commit -m| Закоммитить изменения; после -m в кавычках пишется сообщение о том, что изменено|
|git push| Отправить изменения в удаленный репозиторий|
|git log| Посмотреть журнал действий|

Более продвинутые вещи -- например, как исправлять ошибки или как работать с разными ветками -- можно почитать в [пошаговом тьюториале](https://git-scm.com/book/en/v1/Git-Basics-Undoing-Things) на официальном сайте.

**NB!** Чтобы не печатать длинные пути целиком, существует *автозаполнение*: набираете 1-2 первые буквы, нажимаете tab и вуаля!

### Как настроить авторизацию в Git?

После установки git необходимо его настроить, это делается с помощью двух команд:

`git config --global user.name "ваш логин на github"`

`git config --global user.email "почту, которую указали при регистрации на GitHub.com"`
