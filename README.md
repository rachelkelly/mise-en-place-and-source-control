mise-en-place-and-source-control
================================

no code, just info

Source Control

Bart Massey 2013-02-05
Mise En Place: Setting Up

"Mise-en-place (pronounced [miz on plas]) is a French phrase which means 'everything in place', as in set up." 
      --Wikipedia

    When starting a program, there are standard things you can get in the habit of doing to make your work easier later.
    First, if you haven't yet, make a single directory (folder) in a single place on some machine you control for 
    putting programs in.
        Make sure this directory will be continuously backed up.
        Make sure you can get easy access to it, either from the Internet or by carrying it around: flash drive, laptop.

Backups
    100% always, as computers lose stuff lots of ways:
        Accidentally: hard drive crash, software problem, disaster.
        Maliciously: Internet breakin, virus, burglarly.
    I always have two backups of everything: one offsite.
        Move flash drives or hard disks around.
        Use an Internet backup service.
    Everything means everything.

Starting A Program
    Make a directory inside your programs directory for the new program.
    Make your .py file for your program.
        Choose names wisely!
        Start with two lines of comment: copyright and purpose.
    Make a README file. (I use "markdown".)
    Write some tests if possible.
    Commit the whole thing to source control!

No Source Control
    Bad Idea: As you work on your program, make a copy every so often and put it somewhere.
        Easy to lose track of where you put it.
        Easy to forget which copy is which.
        Big pain, so not likely to do it often.
        Hard to get to it from another machine.

Source Control
    Better Idea: Have software that notes changes to your program when you ask it to, and records that change history.
        Sticks history right where you're working.
        Structured tracking means no confusion.
        Easy, so changes get recorded frequently.
        Can be easily synchronized with a central copy on an Internet-hosted server.

    Diffs / Commits
        Show lines added and deleted (changed is deleted then added) from one version to the rest.
        Nice format for understanding program change.

Mercurial (Hg): A Source Code Management System
    SCMS == SCCS == Version Control System == Revision Control System
    Popular ones include CVS [ancient and stinky!], Subversion (SVN) [previous generation], Git, Hg
    We will work with Hg. I will show you command-line and GUI Hg on Linux. You can find out about Windows / Mac
      on your own.

Setting Up For Hg
    Get and install Hg, TortoiseHg.
    Make a .hgrc or hg.ini in your "home directory" containing
    [ui]
    username = My Name <my-email-address@example.com>
    Go to your program directory.
    Make a backup copy of anything already there.
    Decide on command-line Hg or TortoiseHg.

Using Hg

    Initialize the repo ("hg init").

    Add files to the repo as you want them to be tracked ("hg add").

    Make a commit when you want to record the state of the project ("hg commit").

    Look at commits when you want to know what happened ("hg log").

    Go back to a previous version when you need to ("hg update").


    s = input("? ")
    csum = 0
    for c in s:
        csum += ord(c)
    print(csum % 100)

Exercises To Try

    Word Count: Loop over a string to count the number of words in that string. Does your loop handle whitespace characters next to each other? At the beginning? At the end?

    Branching: Sometimes you want to just try something out in your program, while being able to go back to the earlier version easily afterward. For this, you can use "hg branch". Use "hg branch mybranch" to create a new branch in a repo. Make and commit a change to the repo, then use "hg update default" to get back to the default branch. Use "hg update mybranch" to check that "mybranch" is ok, and "hg branch" to list the branches.

