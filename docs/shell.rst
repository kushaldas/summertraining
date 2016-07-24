Shell commands
===============

Linux shell or the terminal is the life line of the developers, and of any power user. Things
which can be done on the GUI (by clicking on different buttons), can be done much efficiently
on the terminal by using commands. One can not remember all the commands, but with regular usage
one can easily remember the most useful ones.

The following guide will introduce you to some basic minimal commands required to use your Linux
computer efficiently.

Gnome Terminal
---------------

.. figure:: img/terminal1.png
   :width: 600px
   :align: center

The above is the screenshot of the Gnome terminal application. As you can see the command prompt contains
these following information::


    [username@hostname directoryname]

In our case the username is *babai*, hostname is *kdas-laptop*, and directory is mentioned as *~*. This *~*
is a special character in our case. It means the home directory of the user. In our case the home directory path
is */home/babai/*.

pwd command
------------

*pwd* command will help you to find out the current directory. Let us see an example below:
::

    [babai@kdas-laptop ~]$ pwd
    /home/babai

cd command
----------

The next command we will learn is *cd*. This command will help you to change your current directory. We will move
to */tmp* directory in our example.::

    [babai@kdas-laptop ~]$ cd /tmp
    [babai@kdas-laptop tmp]$ pwd
    /tmp
    [babai@kdas-laptop tmp]$ cd ~
    [babai@kdas-laptop ~]$ pwd
    /home/babai

Here you can see that first we moved to */tmp* directory, and then we moved back to the home directory by using
*~* character.

ls command
----------

We use *ls* command to view the files and directories inside any given directory. If you use *ls* command
without any argument, then it will work on the current directory. We will see few examples of the command
below.::

    [babai@kdas-laptop ~]$ ls
    Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
    [babai@kdas-laptop ~]$ ls /tmp/
    cpython           systemd-private-759094c89c594c07a90156139ec4b969-colord.service-hwU1hR
    hogsuspend        systemd-private-759094c89c594c07a90156139ec4b969-rtkit-daemon.service-AwylGa
    hsperfdata_babai  tracker-extract-files.1000
    plugtmp           tracker-extract-files.1002
    [babai@kdas-laptop ~]$ ls /
    bin   cpython  etc   lib    lost+found  mnt  proc  run   srv  sysroot  usr
    boot  dev      home  lib64  media       opt  root  sbin  sys  tmp      var

In the last two commands we provided a path as the argument to the *ls* command. */* is a special
directory, which represents root directory in Linux filesystem. You will know more in the next chapter.

mkdir command
-------------

We can create new directories using *mkdir* command. For our example we will create a *code* directory
in our home directory.::

    [babai@kdas-laptop ~]$ mkdir code
    [babai@kdas-laptop ~]$ ls
    code  Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos

We can also create directories in a recursive way using -p option.::

    [babai@kdas-laptop ~]$ mkdir -p dir1/dir2/dir3
    [babai@kdas-laptop ~]$ ls dir1/ dir1/dir2/ 
    dir1/:
    dir2

    dir1/dir2/:
    dir3

rm command
----------

*rm* command is used to remove a file, or directory. The -rf option is being used to remove in a recursive way.::

    [babai@kdas-laptop ~]$ rm -rf dir1/dir2/dir3
    [babai@kdas-laptop ~]$ ls dir1/ dir1/dir2/ 
    dir1/:
    dir2

    dir1/dir2/:

tree command
-------------

*tree* command prints the directory structure in a nice visual tree design way.::

    [babai@kdas-laptop ~]$ tree
    .
    ├── code
    ├── Desktop
    ├── dir1
    │   └── dir2
    ├── Documents
    ├── Downloads
    ├── Music
    ├── Pictures
    │   └── terminal1.png
    ├── Public
    ├── Templates
    └── Videos

cp command
-------------

*cp*   - Copy a file (or directory).

    Examples:

    cp foo ~/Documents/bar
        copy a file named "a" (in the current directory) into your Documents directory and name the copy "bar"
    cp *.jpg ~/Documents
        copy all files with names ending in ".jpg" into your Documents directory
    cp -R Documents "Documents backup"
        copy an entire directory named "Documents"; name the copy "Documents backup". The quotes are needed because of the space in the directory name.
        
Working with Text Files:
========================

more and less   - display the contents of a text file, one screenful at a time (hit the spacebar to get the next screen). Note that this only works well with plain text files, not Word files, RTF's, PDF's, or anything else that contains formatting information. less also allows you to go backwards (type "b") in the file. In either one, type "h" for more detailed help.

    Examples:

    more /etc/inetd.config
        print the inetd.conf file to the terminal, one screen at a time.
    ps -ax | more
        use the ps command to generate a list of processes running on the system, and pipe them to more to display them one screen at a time. 

grep   - search the contents of a text file, and print lines containing a given word or pattern.

    Examples:

    grep telnet /etc/inetd.config
        search the inetd.conf file, and print all lines that contain "telnet".
    ps -ax | grep netinfod
        use the ps command to generate a list of processes running on the system, then pipe the list through grep, which will print only those lines containing "netinfod". Note: this will list all runing netinfod processes, and also list the process running grep itself. 

vi and emacs   - other text editors provided with the standard *nix installation. They're both more powerful than pico, but also a lot harder to figure out if you aren't already familiar with them.

tail   - print the last few lines of a text file. This is mainly useful for examining the last (i.e. most recent) entries in things like log files.

    Examples:

    tail /var/log/system.log
        print the last screenful of entries from the main system log.
    tail -1000 /var/log/system.log | more
        print the last 1000 entries from the main system log, using more to display them one screenful at a time.

Pipes and Rediretion
====================

`` > ``   - Redirect output from a command to a file on disk. Note: if the file already exist, it will be erased and overwritten without warning, so be careful.

    Example:

    ps -ax > processes.txt
        Use the ps command to get a list of processes running on the system, and store the output in a file named processes.txt 

`` >> ``  - Append output from a command to an existing file on disk.

    Example:

    ps -ax >> processes.txt
        Tack the current process list onto the end of the file processes.txt 
 
`` < ``   - Read a command's input from a disk file, rather than the user. Be careful not to type ">" by mistake, or you'll erase the contents of the file you're trying to read from.


`` | ``   - Pass the output of one command to another for further processing.

    Examples:

    ps -ax | grep Finder
        Use the ps command to get a list of processes running on the system, and pass the list to grep to search for lines containing "Finder". (Usually, it'll find two: the Finder, and the processes executing grep Finder.)

tee   - Used in the middle of a pipeline, this command allows you to both redirect output to a file, and pass it to further commands in the pipeline.

    Examples:

    ps -ax | tee processes.txt | more
        Use the ps command to get a list of processes running on the system, store it in the file processes.txt, and also pass it to more to display it one screen at a time.

Miscellaneous:
==============

man   - display online documentation ("manual pages") for a command.

    Example:

    man ls
        displays detailed documentation on the ls command 

apropos   - list the manual pages relating to a particular keyword.

    Example:

    apropos file
        list manual pages that mention "file" in their summary line. 

find   - Scan a directory structure for files matching certain criteria, and either print their names or do nearly anything else with them. 

    Examples:

    find / -name foo
        Search the entire file structure (including all mounted volumes) for files named exactly "foo", and print their paths.
    find . -mtime -2
        Search the current directory and all subdirectories for files modified within the last 2 days. 

Administration Commands
=======================

kill   - Kill (or send other signals to) a process

    Examples:

    kill 220
        Terminate process #220
    kill -9 220
        Terminate process #220 with extreme prejudice

su   - Set user. Allows you to temporarily become another user (root is the default). It'll ask for that user's password. Use the "exit" command to go back to normal.

    Note:

        You must be a member of the "wheel" group to su to root. Use sudo instead. 

sudo   - Set user and do. Execute a single command as another user (root is the default). It will ask for your password. Access is controlled by a configuration file and can be made quite complex (see the man page). By default, any administrator use sudo to perform any command as any user.

    Examples:

    sudo rm /private/var/db/.AppleSetupDone
        Become root just long enough to delete one file.


