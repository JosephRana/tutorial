# README

## Clonning

We can clone in three ways: HTTPS, SSH, GithubCLI

since we're using codespaces we'll create a temporary directory

```sh
mkdir /workspaces/temp
cd temp
```

### HTTPS

```sh
git clone https://github.com/Muhammadyousafrana/tutorial.git
cd tutorial
```

### Git Hidden Folder

there is a hidden flder called `.git` which tell you that your project is a github repo.

If we want to create a git repo in a new project. Create the folder of the project and initilize the repo using `git init`

```sh
mkdir /workspaces/temp/new-project
cd /workspace/temp/new-project
git init
touch Readme.md
# open the file
code Readme.md
git status
git add .
# make changes to md
git commit -m "add readme file"
```

## Commit

when we want to commit the code that we write `git comit` will open up a commit edit message in the editor of choice.

we can use `-m` tag to commit directly without opening any editor.(`Make a commit and commit message without opening any editor`)

```sh
git commit -m "your message here"
```

but if we use only `git comit` than if will open up the editor and ask you to add message to the commit:

```sh
git commit
```

set the global editor

```sh
git config --global core.editor editor_name
```

## GitConfig File

the .gitconfig file is what store your global configration for git such as email, name, editor etc.

```sh
git congfig --list
```

when you install Git on your machine you've supposed to set the name and email in global configration

```sh
git config --global user.name "username"
git config --global user.email xyz@gmail.com
```

## Git Log

`git log` will show recent git commit to the git tree

```sh
git log
```

## Push

when we want to push a repo to our remote origin

```sh
git push
```

## Branches

## Remotes

## Stashing

## Merging

## Add

when we want to stage changes that'll be included in the commit we can use `.` `(period or dot)` to add all files to the commit other wise we put the name of the file we want to add to the commit.

```md
git add Readme.md
or
git add .
```

## Reset

reset allow you to convert staged file(commited file) to be unstaged (uncommit)

```sh
git add .
git reset
```

> `git reset` will revert `add .`

## Status

Status will show you which file will or will not be commited

```sh
git status
```
