#My Most used Git Commands

There are several states of Git dat:
+ Working Directory
+ Staging Area (Git Index)
+ Repository (.git folder)
+ Remote repository

Configuring 

> git version

> git config --global user.name "Your Name"
> git config --global user.email "YourEmail@mm.com"
> git config --global --list (In order to confirm)

Starting a fresh project
> git init fresh-project (creates a folder named "fresh-project" 

Create a complete copy of a repository:
> git clone https://your.git.repository.com

Git was developed by Linux Tolvard
Repository contains files, history, config managed by Git

Create a new repository on GitHub.
In the Command prompt, change the current working directory to your local project.
Initialize the local directory as a Git repository.
>git init

List the files you've changed and those you still need to add or commit:	
>git status

List the files modified since the last commit
>git diff --name-only

Add the files in your new local repository. This stages them for the first commit.
>git add .
Adds the files in the local repository and stages them for commit. It also adds recursively the files in a tree structure.

Adds any file that has been renamed, deleted or moved
>git add -A 

Renaming files in git:
>git mv original_file_name new_file_name

Moving files
>git mv file_name directory_to_move

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

In order to back out your changes
>git reset HEAD fileName.txt
So this command unstaged the file

If you want to leave the file as it was originally before your changes
>git checkout -- fileName.txt

It is possible to do an inline add and commit if we combine the "a" and "m" parameter. This is only possible with files that are tracket by git (added previously or in the git index. A way to know the files that are tracked is with command "git ls-files"). This will add all the files in the staging area:
>git commit -am "Adding more content"

Deleting a file that is not tracked by Git:
> rm file_name.txt

Deleting a file that is tracked by Git:
> git rm file_name.txt
In order to unstage a deleted file that is not yet committed
> git reset HEAD file_name.txt (but it does not restore the file, to do this just "checkout")
> git checkout -- file_name.txt

When you delete (deletions and renames) a file outside of the git commands (in the OS), you have to stage the changes
> git add -A

Get the history
> git log
> git log --abbrev-commit --> abreviates the response in screen
> git log --oneline --graph --decorate --> This is the most interesting
> git log commitID_initial commitID_end --> prints a range of logs by the specified initial commit to the specified final commit.
> git log -- filename.txt --> prints the activity of the filename.txt

> git show commitID --> show all the information of a specified commit

Create alias for long commands
> git log --all --graph --decorate --oneline --> git config --global alias.nameOFtheCommandYourAreInventing "log --all --graph --decorate --oneline"
>git nameOFtheCommandYourAreInventing

In order to modify an alias you can open .gitconfig file and edit all the aliases you've created.

Synchronise local folder with remote repository
> git pull origin master      

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
or
>git pull origin master

To merge a different branch into your active branch:	
>git merge branchname

Ignore files
> create .gitignore file
> add within the .gitignore file the file or files that we want to ignore (with the name of the file or with a pattern or folder)
> commit .gitignore file

If you mess up, you can replace the changes in your working tree with the last content in head:
Changes already added to the index, as well as new files, will be kept.
>git checkout -- filename

Instead, to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it, do this:	
>git fetch origin
>git reset --hard origin/master

## Clone a repository
>git clone https://github.com/Pirlo220/matrixes.git

##El uso de GIT STASH

@telecristy
https://www.codejobs.biz/es/blog/2015/11/06/el-uso-de-git-stash

Git Stash es uno de los comandos que nos permite guardar las modificaciones locales en forma temporal y regresa el directorio de trabajo a un estado inicial (sin ningun cambio).

 
Por ejemplo, podemos usar git stash cuando estamos trabajando en un proyecto que tiene una funcionalidad dentro de una rama hija diferente y master cómo rama padre del proyecto. Supongamos que tenemos la rama “tarea#1” y estamos trabajando en ella, pero surge que debemos parar nuestro trabajo en esta rama por un rato porque se tiene que hacer un cambio en la rama master (padre). Lo que sucede con git es que siempre tenemos que hacer un commit para poder cambiar de rama, aquí es donde entra Git Stash cómo buena práctica al momento de estar desarrollando. 

Nos encontramos en la rama “tarea#1” y si hacemos un git status veremos los cambios que hemos hecho dentro de esa rama. 

![picture alt](https://www.codejobs.biz/public/images/blog/original/356a192b7913b04.png)

Ahora bien, para cambiarnos de rama sin problema alguno lo único que tenemos que hacer es git stash:

![picture alt](https://www.codejobs.biz/public/images/blog/original/da4b9237bacccdf.png)

Si hacemos de nuevo un git status sobre la rama “tarea#1” veremos que no hay nada, todo está limpio, y ahora puedo fácilmente cambiar de rama sin haber hecho ningun commit.

![picture alt](https://www.codejobs.biz/public/images/blog/original/77de68daecd823b.png)

Para ver nuestra lista de stash ejecutamos el comando git stash list

![picture alt](https://www.codejobs.biz/public/images/blog/original/1b6453892473a46.png)

Ahora bien, si queremos asignar un nombre a nuestro stash debemos utilizar el comando git stash save “Nombre de mi stash”.

Por ahora tengo dos stash en mi lista con los índices 0(es el cambio más reciente) y 1:

![picture alt](https://www.codejobs.biz/public/images/blog/original/c1dfd96eea8cc2b.png)

Para obtener de nuevo los cambios que había hecho en mi rama y seguir trabajando en ello, hago git stash pop stash@{0} :

![picture alt](https://www.codejobs.biz/public/images/blog/original/902ba3cda188380.png)

## gitignore update and things
To untrack a single file that has already been added/initialized to your repository, i.e., stop tracking the file but not delete it from your system use: 
>git rm --cached filename

To untrack every file that is now in your .gitignore:

First commit any outstanding code changes, and then, run this command:

>git rm -r --cached .
This removes any changed files from the index(staging area), then just run:

>git add .
Commit it:

>git commit -m ".gitignore is now working"
