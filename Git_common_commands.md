#Install Git with Apt-Get

Install Git with apt-get in one command!
>sudo apt-get install git-core

The end! Just kidding, you still need to configure Git.
If you wish to download the most recent version of Git from the source, follow the next step. Otherwise, skip down to setup.
Install Git from the Source

Run to make sure that you download the most recent packages to your VPS.

>apt-get update

After that is successful, we are going to download all of the required dependencies (line 1). Finally, only after following the two preceding steps, may you move on to installing the latest version of Git via the google code page (line 2).

Line 1
>sudo apt-get install libcurl4-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev build-essential

Line 2
>wget https://github.com/git/git/archive/v1.9.4.tar.gz

After it downloads, untar the file and switch into that directory:
>tar -zxf v1.9.4.tar.gz
cd git-1.9.4

Global Install
This is a slightly different and more complex process. But do not worry, weary traveler! If you wish to perform a global install it's a two-step process:  

1. Install it once as yourself 
2. Install it once as root.

>make prefix=/usr/local all
sudo make prefix=/usr/local install

How to Setup Git
After Git is installed you need to copy your username and email in the gitconfig file. Using the nano command "sudo nano ~/.gitconfig" will open a completely blank page, as you have just done a fresh install. Insert the necessary information with the following commands:
>git config --global user.name "NewUser"
git config --global user.email newuser@example.com

You can see all of your settings with this command:
>git config --list