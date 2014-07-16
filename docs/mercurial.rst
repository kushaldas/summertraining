Mercurial
=========

Reverting some uncommitted change
----------------------------------

Say now we delete the file **hello.txt** from the directory by mistake. *hg status*
now shows that in output.
::

    $ hg status
    ! hello.txt

We can revert back all the changes in our repo by using the following command.
::

    $ hg revert --all
    reverting hello.txt

In case you made some changes to bye.txt and want to revert only that file, you
can do the following::

    $ hg revert bye.txt
