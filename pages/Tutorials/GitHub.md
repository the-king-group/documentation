---
layout: default
title: Using GitHub for Version Control
parent: Tutorials
nav_order: 4
---
*Note for trouble shooting: the Git Docs are a very goog resources and simply googling your question is decently reliable since Git is so widely used*

## Using GitHub for Version Control

If you don't already please make a GitHub account and let the admins of the King Group GitHub Organization know what your username is. As of Sep. 2026 these admins are Katherine Ellis and Ella King. 

### Setting up GitHub locally (on your own machine)

In effort to not reinvent the wheel please see [this guide on setting up Git](https://docs.github.com/en/get-started/git-basics/set-up-git) on GitHub Docs. This will walk you through how to download Git on your own machine and how to set it up and connect it to your GitHub account. 

### Setting up remote GitHub (online)

Once you are added to the King Group Organization on GitHub it is time to make your first repository to back up all your work to. Please follow [this guide](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories) to create your repository, make sure to set the repository to private. If you already have work on your personal machine that will go in this repository DO NOT upload it now, proceed to Option 2 of the next section. 

### Creating a local repository then linking it to your remote repository.

While you could do 100% of you code work on GitHub using the website interface you may want to consider making a local (on your own device) repository to edit files on your local machine. 

There are two ways to do this depending on where you started creating your code files.

#### Option 1: If you created work in your remote repository first (on the GitHub website)

1. In your terminal navigate to where you want your local repository to live, where do you want the folder to be that will have all your work in it? You can do this by using cd in your terminal
~~~
cd desired_repository_home
~~~
2. Find the name of your remote repository
3. Run the following code
~~~
git clone https://github.com/remote_repository_name
#replacing remote_repository_name with the name of your remote repository
~~~
The local repository is already connected to your remote repository and will refer locally to the remote repository as *origin*, you can confirm this by running 
~~~
git remote -v
~~~

#### Option 2: You already have work on your local device that you want to be in a repository

1. Navigate to the folder you want to become a repository, this is the folder where you already have your work.
2. Then in the terminal run the command
~~~
git init
~~~
this makes that folder a repository and anything in it is now apart of that repository
3. Run the command
~~~
git add .
~~~
this tell Git that you want to track all of the files in the folder.
4. Run
~~~
git commit -m "Initial Commit"
~~~
this ensures all your files are committed to the repository. 
5. To connect it to a remote repository run the command
~~~
git remote add origin https://github.com/remote_repository_name
#replacing remote_repository_name with the name of your remote repository
~~~
you can change *origin* to be a different name, just remember what you name it as this will be how you refer to the remote repository on your local machine
6. Confirm the connection with 
~~~
git remote -v
~~~
7. Run the command
~~~
git push -u origin main
#main is the branch name, this is the only time you need to use -u when pushing to the remote repository
~~~

### Git cheat sheet (comand line prompts for use on your local machine)

#### How do I commit things to my local and remote repositories
1. Optional: Run
~~~
git status
~~~
to see all the tracked changes 
2. Run
~~~
git add .
~~~
to tell Git to track all your files, essentially staging your files for commit
3. Run
~~~
git commit -m "a message"
~~~
you must have a message when you commit
4. Run 
~~~
git push
~~~
since you used the -u flag when first pushing to the remote repository this command automatically pushes your changes to the 
5. To confirm that your local and remote repositories are up-to-date with eachother run
~~~
git pull
~~~
this will attempt to pull any changes in the remote repository that you dont have in your local one, if they are up-to-date you will see a message telling you you are up-to-date. 

#### Good practice
- ALWAYS go through the ( git add . -> git commit -m "word" -> git push ) when you are done working for the day so you never lose any changes
- when making a large code change you should make a new repository branch for the change while you are working on it so you maintain the unchanged version of the code, there are exisiting guides on how to make and eventually merge new branches both locally and remotely
- you can see old versions of files from the last time they were pushed, this can be very good for making sure you dont accidently lose code and you always have a backup of your code work.
- you can store files on github that arent code files, virtually any type of file can be uploaded to GitHub

Last update: Katherine Ellis Sep. 2026
