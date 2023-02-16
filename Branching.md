# Branching

##  Table of Contents
1. [Create branch](#create-branch)
2. [Switch to another branch](#switch-to-another-branch)
3. [Compare branches](#compare-branches)
4. [Rename branch](#rename-branch)
5. [Delete branch](#delete-branch)
6. [Merge a branch](#merge-a-branch)
7. [Merge Conflict](#merge-conflict)
8. [Resolve a merge conflict](#resolve-a-merge-conflict)
9. [Cheat sheet](#cheat-sheet)



Git's powerful branching feature allows developers to create new branches to experiment with new ideas without modifying the master branch. If the changes on a new branch are unsuccessful, it can be discarded without impacting the master branch. On the other hand, if the changes are successful, they can be merged back into the master branch. Branching is particularly useful for collaborating with others, allowing developers to work on separate branches and merge changes back into the master branch when complete.

## Create branch

To create a new branch using Git use

    git branch 'name'

If no name is provided, Git will display a list of all existing branches. Or you can use

    git checkout -b 'name'

to create a new branch and switch to it automatically. 

Once a new branch is created, the developer can check the current branch by looking at the "*" symbol, which will indicate the master branch.

 Developers can also manually verify the current branch by checking the ".git/HEAD" file, which keeps track of the current branch. The ".git/refs/heads" directory stores the references to the head of each branch.

## Switch to another branch
To switch to a different branch using Git, developers can use the command 

    git checkout 'name'

After making commits in the new branch, switching back to the master branch will not show the same changes, as the changes made in the new branch do not affect the master branch. 

## Compare branches
The process of comparing branches in Git is similar to comparing files. The `git diff` command can be used, with the `..` symbol separating the two branches being compared. 

    git diff 'name'..'name' 

It is not necessary to be on either of the branches that are being compared to use this command. 

## Rename branch
To rename a branch, Git provides the option to use the following command where first name is the old branch name and second is new branch name

    git branch -m 'name' 'name'

The current branch can be renamed by specifying just the new name. 

    git branch -m 'name'

## Delete branch
To delete a branch use

    git branch -d branch-name
    
 However, there are checks that Git performs before allowing the branch to be deleted. You cannot delete the branch you are currently on, and if you have made changes on a branch but not merged them into the master branch, you cannot delete it. In such cases, Git warns you that the branch is not fully merged.

If you wish to discard all the changes on a branch, you can use the `-D` option to delete the branch, which will also destroy all the commits on that branch.

## Merge a branch
To merge a branch, first switch to its ancestor branch and use following command specifying what branch have to be merged.

    git merge 'name'
To see which branches have been merged, the following command can be used.

    git branch --merged

This will show which commits from one branch have been merged into another branch.

## Merge Conflict
When you create a new branch, make changes, and then try to merge it back into the master branch when someone else has made changes to the same file on the same line Git will detect a conflict when trying to merge the changes and prompt an error message. To fix the conflict, the changes on both branches need to be reviewed and manually resolved before they can be merged. 

Using 

    git status

will show that the file has been modified more than once. When you check the content of the file, you will see two versions of the file, one from the current branch and one from the branch containing the modification. Git shows both versions and uses special markers to separate them.
The content under

    <<<<<<< HEAD
shows the modification under our current branch, and content under

    =======
shows the modifications and the branch contains that modification.
You must manually change contents of that file  by deciding which changes to keep before you can merge the changes back to the master branch.

## Resolve a merge conflict
There are three ways to resolve a merge conflict: 

 - Abort the merge
 - Resolve the conflict manually
 - Use a merge too

If you decide not to merge, you can abort the merge using 

    git merge --abort

If you want to merge conflict manually its recommended to use tools that are built into your IDE or if you using GitHub do it through online interface. However online merge manager capabilities are limitied and in some cases you will have to use other means.

If you use a merge tool, you can see the manual of the built-in mergetool using

    git help mergetool


It is always best to avoid merge conflicts, and strategies for doing so include keeping lines short, limiting and prioritizing commits, and merging often.

## Cheat sheet
|Command | Description  |
|--|--|
|  git branch | list all branches |
| git branch 'name' | create new branch|
|git checkout -b 'name' | create new branch and switch to it|
| git checkout 'name' | switch to a specified branch|
| git diff 'name'.\.'name'| compare 2 branches|
|git branch --merged| see what branches were merged|
|git branch -m 'name'| rename current branch|
|git branch -m 'name' 'name'| rename specified  branch|
|git branch -d 'name'| delete specified branch|
|git merge 'name'| merge specified branch into current one|
|git merge --abort | cancel merge|
|git help mergetool| utility application to help merge|


