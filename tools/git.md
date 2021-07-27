# Git

Very popular distributed version control system

workflow of git

```txt
         git init       git add     git commit     git push
┌─────────┐    ┌─────────┐    ┌───────┐    ┌────────┐    ┌────────┐
│ initial ├───►│ untrack ├───►│ track ├───►│ staged ├───►│ master │
└─────────┘    └─────────┘    └───────┘    └────────┘    └────────┘
```

## User and email

Add username and email to git

```sh
git config --global user.name "username"
git config --global user.email "username@example.com"
```

## Commit

Add describe to changes, for one-liner 

```sh
git commit -m "commit message"
```

or open in editor

```sh
git commit
```

## Clone project

Clone project to local computer

```sh
git clone <url-of-project>
```

## Diff

Check the different between unstage changes and latest commit

```sh
git diff
```

## Pull and Fetch

The different between ```git pull``` and ```git fetch``` is ```git fetch``` doesn't merge automatically when upstream is changed unlike ```git pull``` will automatically merge without asking

fetch from upstream

```sh
git fetch --all
```

## Merge

```sh
git merge origin master
```

## Checkout

create new branch

```sh
git checkout -b <new branch>
```

switch between working branch

```sh
git checkout <branch>
```

## Cherry picking

Cherry picking commits

```sh
git cherry-pick master <commits>
```

## Set core editor

Set editor for commits

```sh
git config --global core.editor "vim"
```

## Undo commits

Undo staged change

```sh
git reset HEAD~
```

## Reset to last commit

Revert back to last commit and ignore all changes

```sh
git reset --hard HEAD
```
