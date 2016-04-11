#My Most used Git Commands

Create a new repository on GitHub.
In the Command prompt, change the current working directory to your local project.
Initialize the local directory as a Git repository.
>git init

List the files you've changed and those you still need to add or commit:	
>git status

Add the files in your new local repository. This stages them for the first commit.
>git add .
Adds the files in the local repository and stages them for commit


Commit the files that you've staged in your local repository.
>git commit -m 'First commit'
Commits the tracked changes and prepares them to be pushed to a remote repository

>git remote add origin 'remote repository URL'
Sets the new remote
>git remote -v
Verifies the new remote URL

Push the changes in your local repository to GitHub.
>git push origin master
Pushes the changes in your local repository up to the remote repository you specified as the origin

Create a new branch and switch to it:	
>git checkout -b branchname

Switch from one branch to another:	
>git checkout branchname

Delete the feature branch:	
>git branch -d branchname

Push the branch to your remote repository, so others can use it:	
>git push origin branchname

Fetch and merge changes on the remote server to your working directory:	
>git pull

To merge a different branch into your active branch:	
>git merge branchname

If you mess up, you can replace the changes in your working tree with the last content in head:
Changes already added to the index, as well as new files, will be kept.
>git checkout -- filename

Instead, to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it, do this:	
>git fetch origin
>git reset --hard origin/master