# Discussion 1 - 11/01/23
## Installing VS Code
The first step in order to get started with the Lab Activity is to download VSCode. 
Windows and Mac users can download VSCode by clicking [here](https://code.visualstudio.com/download). 
<img width="1099" alt="image" src="https://user-images.githubusercontent.com/89179888/211932363-45cabe8e-0edf-42c4-8d5b-f45d10679c3a.png">
Depending on your Operating System, you can choose different links to download VSCode. Once you have downloaded VSCode, you can proceed to the next steps of the activity.

## Remotely Connecting
Again, depending on your operating system, there are different ways of remotely connecting to the server. In case you are a Windows user, you will need to download `git` first. You can download Git by going to [this](https://gitforwindows.org) link. 
Mac users do not need to install Git and can proceed directly to the next step.
Now, you need to go to [this](https://sdacs.ucsd.edu/~icc/index.php) website and check the account details linked to your UCSD PID. Once you have done so, you will find your unique username beginning with `cs15lwi23`. Since you would most probably be logging into this website for the first time, it is highly recommended to change your password on the same link above. It might take upto 15 minutes for the new password changes to reflect.

Once the above step has been completed, you can open the terminal in VSCode and enter the following command:
`$ ssh cs15lwi23abc` where `abc` is your unique ID.
After successfully copying this, you will get the following message:
<img width="553" alt="image" src="https://user-images.githubusercontent.com/89179888/211950027-9b9a88f5-0fd1-46ad-9709-21da90731b57.png">

Respond, **yes** to this message on the terminal.
If completed successfully, the following dialogue should appear:

```
Hello cs15lwi23amy, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   13:45:01   21  0.58,  0.26,  0.20
ieng6-202   13:45:01   24  0.35,  0.12,  0.10
ieng6-203   13:45:01   13  0.04,  0.07,  0.11
```

This message implies that you have finished the 'Remotely Connecting' part of the task.

## Trying Some Commands
This activity is designed so as to get an idea of how the terminal works. First, open your terminal in VSCode. It should look something like this:

<img width="805" alt="image" src="https://user-images.githubusercontent.com/89179888/212430083-dac2522e-69d3-437c-8624-f0813cae0fb9.png">

Some of the basic commands that you can try in the terminal are as follows:


` cd ` This command stands for 'change directory'. If you add a ` ~ ` symbol, it returns to the home directory. Instead, if your current working directory is ` Users/yourname ` add a path name after cd, for example ` cd JavaProjects `, the new working directory would be ` Users/yourname/JavaProjects `. You can verify this by typing ` pwd ` after the command.

` ls ` This command lists all the files in the current directory except hidden files.

` pwd ` This command stands for 'print working directory'. If this command is executed, it prints and lets the user know which exact directory they are currently in.

` mkdir ` This command creates a new directory or subdirectory within the current working directory.

` cp ` - cp stands for copy. This command is used to copy a single file or a group of files. It creates an exact image of a file on a disk with different file name.


Now, when trying the following commands as part of the assignment, you will get the following results:

` cd ` This command will just return back nothing, meaning that it was successfully executed.

` cd ~`This command will just change the current directory back to the home directory and return nothing, meaning that it was successfully executed.

`ls -lat` When running the following command, you will get the following result:
```total 128
-rw-r--r--   1 cs15lwi23abc ieng6_cs15lwi23  1346 Jan 13 15:14 .modulesbegenv
-rw-r-----   1 cs15lwi23abc ieng6_cs15lwi23     0 Jan 13 15:14 .motd
drwxr-sr-x 638 cs15lwi23    ieng6_cs15lwi23 53248 Jan 13 08:06 ..
-rw-------   1 cs15lwi23abc ieng6_cs15lwi23   182 Jan 11 15:12 .bash_history
drwxr-s---   6 cs15lwi23abc ieng6_cs15lwi23  4096 Jan 11 15:12 .
drwxr-sr-x   2 cs15lwi23abc ieng6_cs15lwi23  4096 Jan 11 13:46 perl5
drwxr-sr-x   3 cs15lwi23abc ieng6_cs15lwi23  4096 Jan 11 13:46 .local
drwxr-sr-x   3 cs15lwi23abc ieng6_cs15lwi23  4096 Jan 11 13:46 .config
drwxr-sr-x   3 cs15lwi23abc ieng6_cs15lwi23  4096 Jan 11 13:46 .cache
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23   290 Jan  6 15:11 .zshrc
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23   481 Jan  6 15:11 .zshenv
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23  1931 Jan  6 15:11 .zprofile
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23  1961 Jan  6 15:11 .profile
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23   837 Jan  6 15:11 .procmailrc
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23   431 Jan  6 15:11 .login
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23   155 Jan  6 15:11 .locallogin
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23  1692 Jan  6 15:11 .kshrc
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23  1931 Jan  6 15:11 .cshrc
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23  1721 Jan  6 15:11 .bashrc
-rwxr-x---   1 cs15lwi23abc ieng6_cs15lwi23   975 Jan  6 15:11 .bash_profile
```
`ls -a` This command returns the following:
```.              .bashrc  .kshrc       .modulesbegenv  .zprofile
..             .cache   .local       .motd           .zshenv
.bash_history  .config  .locallogin  .procmailrc     .zshrc
.bash_profile  .cshrc   .login       .profile        perl5
```
`cat /home/linux/ieng6/cs15lwi23/public/hello.txt` This command concatenates different text files to give the output `Hello! Welcome to CSE 15L`.

If you have been able to finish all these tasks without any problems, that means you have been able to complete the assignment successfully. Now, in order to exit the terminal, you can either run the command `exit` or use the command `Ctrl-D`.






