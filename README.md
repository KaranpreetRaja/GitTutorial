# Git Tutorial

## Installing Git


## Git Config

Git configuration allows you to add configuration information (Name and Email) on three levels:

* `git config --system` sets configuration information for all users of the system
  * Applies to all users and their repositories
* `git config --global` sets configuration information for current user of the system
  * Applies to currently logged in user and their repositories
  * Usage: When you have
* `git config` sets configuration information for local project
  * Applied to the current repo on the system

### Initializing Git Config

When setting up git config you want to set up two main things, your name and your email address:

```
git config --global user.name "FirstName LastName"
```

```
git config --global user.email "user@emailaddress.com"
```

In order to view current configuration, you can check running the following command:

```
git config --list
```

## Git Basics

### Initializing a New Repository

In order to make a new local repository using git, run the following command once you are in the directory you want to turn into a repository

```
git init 
```

this creates a hidden .git configuration directory.

### Adding/Removing Tracking Files

Git does not know what files in the directory to track for the next commit, `git add` allows you to add files to be tracked for the next commit

```
git add .
```

The . paramter adds all files that have been modified to be added to the files being tracked. if you wish to add a single file replace the "." in the command above with the path to the file name (ex. `git add README.md`).

You can stop tracking files by using the following command.

```
git rm path/to/file

```

The same "." parameter can be used to stop tracking all the files that are currently being tracked (`git rm .`)

### Check Files Being Tracked

In order to see what files are being currently tracked by git, you may use the following command

```
git status
```

This command will only show you what files with changes are being tracked, this will not actually show you the changes. In order to see the changes, you can use the following command

```
git diff
```

### Commiting Changes

Now that you have added files for git to track, in order to commit the changes (add them as a single update in the version control) you can run the following command.

```
git commit -m "Description of Change"
```

### Pushing You changes

For now, all of your changes are local, in order to "publish" these changes you must **push** them to the remote repository. This can be done by doing the following.

```
git push origin
```
