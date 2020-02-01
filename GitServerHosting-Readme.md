# Setup Git server and client locally in ubuntu

## Git Server Setup:

1. Install open ssh first

        $ apt-get install openssh-client openssh-server

2. Go to terminal and create new user

        $ adduser git

3. Now run

        $ git

4. Create directory

        $ mkdir .ssh

5. Now go to home directory and create project

        $ mkdir projectname

6. Then go to your project directory and run

        $ git init
        $ git --bare init

## Your git server setup is completed.

7. To check current connected git user on Git server,  run

        $ cat .ssh/authorized_keys


8. Initial or first time need rsa authoruized key of client machine. Generate ssh key if you not created already from terminal

        $ ssh-keygen -t rsa -C "use your any email"
        $ ssh-keygen -t rsa -C 
        "yourmachineusername@yourmachinename on 
        gitusername@gitservermachine"

9. Copy the server ssh. You can use servername instead of use server IP

        $ ssh-copy-id gitserverusername@gitserverip

10. Client machine added to git server machine done. You can check by running from server machine to check it connected or not.

        $ cat .ssh/authorized_keys

11. Clone project from server machine to client machine:
Clone the project from server what you created as projectname . Go to your directory where you wanted to clone. Then  run

        $ git clone serverusername@gitserverip:/home/git/projectname
 

12. New  project  push to server  machine from client machine:
Go to your project directory and run the following command from terminal

        $ git init
        $ git add .
        $ git commit -m "initial commit"
        $ git remote add origin username@serverip:path/projectname.git
        $ git push origin master

13. If following message shown from client machine
receive.denyCurrentBranch’ configuration variable to ‘refuse’
Go to server machine & run from terminal

        $ git config --bool core.bare true


### Setup Completed

#### Thanks
