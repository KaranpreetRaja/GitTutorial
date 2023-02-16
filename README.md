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
