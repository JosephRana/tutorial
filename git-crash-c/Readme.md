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

> You'll need to Generate a Personal Access Token (PAT)

```md
https://github.com/settings/personal-access-tokens
```

You'll use `PAT` as your password when you login when you're pushing files from local environment

- Give permisson to commits

### SSH

```sh
git clone git@github.com:Muhammadyousafrana/tutorial.git
cd tutorial
```

> Most of the time it show's that access is denied if you try to clone or push the file in this case we've need to generate a `ssh key` by using the following command:

```sh
ssh-keygen -t rsa
#after the above command it will ask you to enter the name of file and you will enter the name of file with root directory to `.ssh` folder and copy the key with extention `.pub` and add in github ssh-key and for Local terminal use the below commands
eval "$(ssh-agent -s)"
ssh-add /c/Users/muham/.ssh/github-alt_id_rsa
# finally Test that authentication is added successfully
ssh -T git@github.com
```

- it will ask you enter the name of file and you've need to enter the name in the following directory:
`/c/Users/muham/.ssh/github-alt_id_rsa`
- and then use the cat comand to view and copy the key and add into the github repo a `ssh public key` 

### GitHub CLI

> Download and intall the github cli using the following link:

```md
[link](https://cli.github.com/)
```

- open the command line and enter the following command to authenticate with cli:

```md
gh auth login
```

## Git Hidden Folder

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

> show the list of branches

```md
git branch
```

> Create a New Branch

```md
git branch branch_name
```

> checkout the branch

```md
git checkout branch_name
```

## Remotes

`git remote add <name> <url>`
This command adds a new remote repository to your local Git project. It establishes a connection between your local repository and the remote repository.

- `name` The name you want to give to this remote, typically origin (but you can name it anything).
- `url` The URL of the remote repository (e.g., a GitHub, GitLab, or Bitbucket repo).

```sh
git remote add origin https://github.com/user/repo.git
```

we add remote but often you'll just add remote via upstream when adding a branch

```sh
git remote add ...
git branch -u origin new-feature
```

## Stashing

Saved working directory and index state WIP on dev:

```sh
git stash
# if you want to specify the name
git stash save stash-name
git stash apply # same as pop
git stash list
git stash pop
```

## Merging

```sh
git checkout dev
git merge main
```

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
