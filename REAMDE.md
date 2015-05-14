# Getting Started with Git and Github for n00bs#

This tutorial will help you get started with Git and Github. It is target towards Git n00bs.

Download the required Git softwares from [here](http://git-scm.com/downloads)

## Initialize a new Git repository##

If you want to make a new directory managed by Git then you have to first initialize it.

```bash
$ mkdir myapp
$ cd myapp
$ git init
```

This creates a new directory `.git` and add few git related content there. All the sourcecode that you will commit will be place here.

## Create a new File##

Create a new file inside `myapp` directory using your favorite editor and add some content to it as shown below.

On nix machines you can do the following.

```bash
$ cd myapp ## In case you are not in myapp directory
$ echo "hello Git" >> hello.txt
```

## Check your Git repository status##

```bash
$ git status
```

## Adding a file to the Git index##

Tracking an untracked file

```bash
$ git add hello.txt
```

To add multiple files do the following

```bash
$ git add --all
```

## Commit the file to the Git repository##

```bash
$ git commit -m "adding hello.txt"
```

## Lets modify the file##

```bash
$ echo "hey all" >> hello.txt
```

Now as the file is already in the Git index so you can add and commit using one command.

```bash
$ git commit -am "modified hello.txt"
```


## Check the commits##

```bash
$ git log
```

If you want to see in one line

```bash
$ git log --oneline
```

You can add an alias and make things better like as shown below. Alias let you write your own commands.

```bash
lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%C(bold blue)<%an>%Creset' --abbrev-commit
```

Now you can use `git lg`

```bash
* 717e2fc - (HEAD, master) modified hello.txt (2 minutes ago)<Shekhar Gulati>
* 1d10050 - adding hello.txt (3 minutes ago)<Shekhar Gulati>
(END)
```
## Using Github##

Signup for Github

Setup SSH keys. Copy your public key in your <User_Home>/.ssh keys. Windows uses please use Github for Windows that will set up SSH for you. https://help.github.com/articles/generating-ssh-keys/

Create a new Git repository

Add a new remote pointing to the Github repository.

```bash
$ git remote add origin git@github.com:shekhargulati/myapp.git
```


## Pushing changes to Github##

```bash
$ git push -u origin master
```

## You can push to multiple Git repositories using Git remotes##

Add multiple Git remotes

```bash
$ git remote add remote1 git@github.com:shekhargulati/myapp1.git
$ git remote add remote2 git@github.com:shekhargulati/myapp2.git
$ git remote add remote3 git@github.com:shekhargulati/myapp3.git
```


## Cloning an existing Git repository##

```bash
$ git clone git@github.com:shekhargulati/myapp.git
```

You can also give another name

```bash
$ git clone git@github.com:shekhargulati/myapp.git myapp2
```


## Always pull the changes before committing

```bash
$ git pull
```


## Reverting the last commit before pushing##


```bash
$ git reset --soft HEAD~1
```


## Deleting files from Git index

```bash
$ git rm -f hello.txt
```


## Branches are very cheap in Git

Always work on your features in branches

```bash
$ git checkout -b my_new_feature
```

Now you will inside `my_new_feature` branch

Make a change, commit it, checkout master, and then merge


```bash
$ git checkout -b my_new_feature
$ echo "abc" >> hello.txt
$ git commit -am "my change"
$ git checkout master
$ git merge my_new_feature
```
