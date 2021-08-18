[How to install Lexonomy locally](https://github.com/elexis-eu/lexonomy/blob/master/INSTALL.md)

[Widget API documentation](https://github.com/elexis-eu/lexonomy/wiki/Create-widgets)

### Launching a local installation

1. `cd ./lexonomy/website`

The path in this command depends on where you are; the example assumes that you are in the directory where you cloned the Lexonomy repo from GitHub.

2. `cp siteconfig.json.template siteconfig.json`

Create a config file from template.

3. `python3 ./adminscripts/init.py`

Initialise a database and create the admin user. After running this command, you will see a prompt in the terminal: `I have created a user account for root@localhost. The password is: ******`. **Save this password**, you'll need it to log in!

4. `source ./<ENV>/bin/activate`

\<ENV\> is your environment name. The assumption is that its source files are within `lexonomy/website` directory, otherwise please change the path according to their location.

5. `python3 lexonomy.py`

You can then open `http://127.0.0.1:8080` or `http://localhost:8080/` in your browser and enjoy everything that `https://www.lexonomy.eu/`offers locally. 

### Forking a repo

When you are working on a rather independent feature for a big project, a good practice is to *fork* the project repo, which means creating its independent copy under your own account without losing connection to the original. 

![](./img/1.png)

You can always get the latest project updates by pressing `Fetch upstream`. It will get new commits from the `master` branch in the original repo and merge them into yours. 

![](./img/2.png)

When you are ready to contribute something to the project, you can create a pull request.

![](./img/3.png)

### Changing remote

We cloned the original repo `https://github.com/elexis-eu/lexonomy.git`, so our local `lexonomy` folder is associated with it. Now that we have our own fork, we need to tell git that that's where we want to push local changes.

`git remote set-url origin https://github.com/<YOUR_GITHUB_USERNAME>/lexonomy.git`

Now everything is set for work 😎
