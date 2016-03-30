#My Most used Git Commands

Create a new repository on GitHub.
In the Command prompt, change the current working directory to your local project.
Initialize the local directory as a Git repository.
git init


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
