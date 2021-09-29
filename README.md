# Git-Learning Version Control Cheatsheet Day-1
This repository contains the cheat sheet for the Day 1 session of Git-Learning Version Control. Fork it and you are good to go 💻 !


# What is version control?
- Version control, also known as source control, is the practice of tracking and managing changes to software code. Version control systems are software tools that help software teams manage changes to source code over time.
	
- Software teams that do not use any form of version control often run into problems like not knowing which changes that have been made are available to users.

## Benefits of using Version Control Systems

- A complete long-term change history of every file.This means every change made by many individuals over the years. They also include the author, date and written notes on the purpose of each change.
	
- Branching and merging. Having team members work concurrently is a no-brainer, but even individuals working on their own can benefit from the ability to work on independent streams of changes.
	
- And many other different features!

# Installation

## Install Git for Windows 

Just go to https://git-scm.com/download/win and the download will start automatically. Apply the steps described in the session to install.

## Install Git on Linux
**For a Debian-based distribution, such as Ubuntu**

`sudo apt install git-all`

The above command will install all sub-packages including a GUI and tree visualizer. If you only want to include main components with minimal dependencies then you should rather use this command!.

`sudo apt install git`

**For Fedora (or any closely-related RPM-based distribution, such as RHEL or CentOS)** 

`sudo dnf install git-all`


*For other options, there are instructions for installing on several different Unix distributions on the Git website, at https://git-scm.com/download/linux.*

## Install Git on Mac

A macOS Git installer is maintained and available for download at the Git website, at https://git-scm.com/download/mac. Follow the steps mentioned ont the website after that.


# Seting up the git terminal

## Setting up your git config. 

The git config command changes the configuration options in your Git installation. It is often used to set your Git email, editor, and any aliases you want to use with the git command.

- *Setting up username*

`git config --global user.name "username"`

- *Seting up Email*

`git config --global user.email "name@email.com"`

- *View your configuration file*

`git config --list`



## Adding tokens 

**A. By Adding SSH Tokens**

GitHub offers a convenient SSH key feature for accessing your repositories on the command line. Instead of using usernames and passwords every time you push to or pull from your repository, you can use your key.


1. Create a new SSH: Type `ssh-keygen -t -b 4096 -C "<your email here>"` in your terminal, then press enter.

2. It will ask for a new passphrase. Enter and then confirm a new passphrase.

3. Without changing the path of your terminal, type `eval $(ssh-agent -s)` and press enter.

4. Next, type `ssh-add ~/.ssh/id_rsa`, and press enter.

5. Go to the present file location manually using File manager and copy the file named `id_rsa.pub`, or you can also type `clip < ~/.ssh/id_rsa.pub`, if you have windows installed.

6. Go to github.com and login to your account.

7. Go to `settings>SSH and GPG keys`

8. Click on `NEW SSH KEY`

9. Choose a Title and paste the SSH key in the Box.

10. You are all caught up!


**B.** 
**By adding Personal Access Tokens (PAT)**

You can also refer to this article: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

1. Login to your account on github.com

2. In the upper-right corner of any page, click your profile photo, then click Settings.

3. In the left sidebar, click Developer settings.

4. In the left sidebar, click Personal access tokens.

5. Click Generate new token.

6. Give your token a descriptive name.

7. To give your token an expiration, select the Expiration drop-down menu, then click a default or use the calendar picker.

8. Select the scopes, or permissions, you'd like to grant this token. To use your token to access repositories from the command line, select repo.

9. Click Generate token.

-  **REMEMBER**

	**(i) By using PAT, you'll have to enter the token everytime you try to perform any operation. Here is an example of how you'll use it while cloning:**

	Example:

	```
	$ git clone https://github.com/username/repo.git
	Username: your_username
	Password: your_token
	```
	
	**(ii) If you donot wish to enter your PAT everytime, enter this line before using any command(like the one shown above in the example). After this you will have to enter the your PAT just one last time as it will cache your credential for the next use.**
	
	`git config --global credential.helper cache`


# Github Commands
See where Git is located:
`which git`

Get the version of Git:
`git --version`

Create an alias (shortcut) for `git status`:
`git config --global alias.st status`

Help:
`git help`

### Initializing the repository
Initialize Git:
`git init`

Get everything ready to commit:
`git add .`

Get custom file ready to commit:
`git add index.html`

### Pull 

Pull:
`git pull`

Pull specific branch:
`git pull origin branchname`

### Commiting
Commit changes:
`git commit -m "Message"`

Commit changes with title and description:
`git commit -m "Title" -m "Description..."`

Add and commit in one step:
`git commit -am "Message"`

### Removing files

Remove files from Git:
`git rm index.html`

Update all changes:
`git add -u`

Remove file but do not track anymore:
`git rm --cached index.html`


### Branching
Show branches:
`git branch`

Create branch:
`git branch branchname`

Change to branch:
`git checkout branchname`

Create and change to new branch:
`git checkout -b branchname`


### Cloning a repository

Clone to localhost:
`git clone https://github.com/user/project.git` or:
`git clone ssh://user@domain.com/~/dir/.git`

Clone to localhost folder:
`git clone https://github.com/user/project.git ~/dir/folder`



### Push 

Push (set default with `-u`):
`git push -u origin master`

Push:
`git push origin master`

Force-Push:
`git push origin master --force


### Setting up aliases

They allow you to write shortcuts for common commands that you write.

Example: 

`git config --global alias.co commit`

Every time we run git co, the git commit command will be run!


## Terminal Commands

Show folder content: `ls -la`

Show the path to the present working dirctory: `pwd`

Create directory: `mkdir <file_name>`

Change directory: `cd <file_name/file_location>`

