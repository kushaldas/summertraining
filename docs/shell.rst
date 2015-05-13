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

