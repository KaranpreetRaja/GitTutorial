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
