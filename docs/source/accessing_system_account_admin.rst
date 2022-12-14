============================================================
Accessing the System and Account Administration
============================================================

The page contains information about how to set up your machine to log
into and use the Nightingale cluster computer at NCSA. This page will
contain general setup instructions for logging into your interactive
node on the Nightingale cluster.

**If you don't understand how to log into Nightingale, and the "ssh"
section below doesn't help you enough, here is a page to walk users who
mostly use Windows to set up your computer to log in.**

If you cannot find the information in this user guide to do your work on
Nightingale or if you need further help please contact your user support
contact. To do that, send an email to "help@ncsa.illinois.edu". Be sure
to put "Nightingale" in the subject line and a few words about what the
problem is. Then put as much information as you can into the body of the
email.

**Introduction to Nightingale**
-------------------------------

Nightingale is a cluster computer. That is, it is several separate
computers (called "node"s) connected together by network that share some
pieces. Mostly when you log into Nightingale, you will log into a
particular "interactive" node that will have software, hardware, and
data that is specific for the work that you and your group do. To
configure your logins, you will need to know the **name** of the
interactive node assigned to you. That name will be a fully-qualified
hostname, something like "ng-notarealnode01.ngale.internal.ncsa.edu".

Logging onto Nightingale
~~~~~~~~~~~~~~~~~~~~~~~~

To work on Nightingale, you will "log in" to it. Logging in establishes
a connection between your computer and a node of nightingale, so that
you can use software on Nightingale to manipulate and analyze data on
Nightingale, but you're controlling that software using your mouse and
keyboard, and the display window for that software shows up on **your**
computer. To log into Nightingale, user will need at least a ssh client
available on their local desktop or laptop to make the connection. All
Nightengale users must use a ssh based connection to go through the
secure node (`bastion
host <https://en.wikipedia.org/wiki/Bastion_host>`__) to be able to
login to the general access head (login) nodes or, for groups that have
them, their specific interactive specialized nodes.

| 

+----------+-------------------------+---------------------------------+
| Access   | Secure Node             | General Access Head Nodes       |
| Method   |                         |                                 |
+----------+-------------------------+---------------------------------+
| SSH      | ngale-bast              | ng-                             |
|          | ion-1.ncsa.illinois.edu | login01.ngale.internal.ncsa.edu |
|          |                         | ng-                             |
|          |                         | login02.ngale.internal.ncsa.edu |
+----------+-------------------------+---------------------------------+

**Note:** All Nightingale users have access to the general access head
nodes. Please be aware that the general access head nodes are a shared
resource for all users of the system and their use should be limited to
editing, compiling and building your programs.

| 

+----------+-------------------------+---------------------------------+
| Access   | Secure Node             | Group Specific Interactive      |
| Method   |                         | Node(s)                         |
+----------+-------------------------+---------------------------------+
| SSH      | ngale-bast              | ng-group_specific_no            |
|          | ion-1.ncsa.illinois.edu | de_name.ngale.internal.ncsa.edu |
+----------+-------------------------+---------------------------------+

**Note:** Certain Nightingale groups have exclusive access to their
interactive specialized nodes.

| 

| 

Mac OS users
^^^^^^^^^^^^

You will log into Nightingale using the "ssh" command in your Terminal
program. It's already installed and ready. You will also need an
application that serves as an "X-windows server". For Mac OS users, we
recommend XQuartz.

| 

Unix/Linux OS users
^^^^^^^^^^^^^^^^^^^

Will also log into Nightingale using the "ssh" client that is run from
the command line in the terminal. Generally, the "ssh" client along with
an "X-Windows" server should be available by default on recent versions
of Unix/Linux OSes.

| 

Windows users
^^^^^^^^^^^^^

We recommend Nightingale users first install a program called MobaXterm
on their computers and then use that to log into Nightingale. This
install process is detailed on this separate wiki page.

| 

User environment configuration via "module" commands
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Nightingale uses a set of commands called "lmod" (short for "Lua
Modules") that allows users to turn access to certain software on or off
by "loading" or "unloading" a modulefile (which is just a file that adds
or removes the software's configuration to your user environment). Here
are the most common module commands you will use as a user of
Nightingale.

| 

+--------------------+-------------------------------------------------+
| Command            | Description                                     |
+--------------------+-------------------------------------------------+
| module avail       | Lists the modules that are available. If you    |
|                    | are looking for a piece of software but typing  |
|                    | the command to run it gets you a "command not   |
|                    | found" error, then loading the modulefile for   |
|                    | that specific piece of software first is        |
|                    | probably what you need to do.                   |
+--------------------+-------------------------------------------------+
| module list        | Lists the modules that you currently have       |
|                    | loaded in your current user environment.        |
+--------------------+-------------------------------------------------+
| module help        | Provide general information on what the         |
| *modulefile*       | modulefile does to your current user            |
|                    | environment when loaded.                        |
+--------------------+-------------------------------------------------+
| module display     | |                                               |
| *modulefile*       |                                                 |
|                    | Display (or show) the changes that loading the  |
| or                 | modulefile will make to the user environment.   |
|                    |                                                 |
| module show        |                                                 |
| *modulefile*       |                                                 |
+--------------------+-------------------------------------------------+
| module load        | Loads a modulefile [or modulefiles] into your   |
| *modulefile (      | current shell environment (see "module avail"   |
| modulefile2        | above to get a list)                            |
| modulefile3 ...)*  |                                                 |
+--------------------+-------------------------------------------------+
| module unload      | Unloads a modulefile; if you unload a           |
| *modulefile*       | modulefile you had previously loaded, then the  |
|                    | software is no longer available to you (in your |
|                    | current shell environment).                     |
+--------------------+-------------------------------------------------+
| module swap        | Unloads one *modulefile1* and loads another     |
| *modulefile1       | *modulefile2*. This is typically used to change |
| modulefile2*       | the version of a modulefile that you have       |
|                    | loaded.                                         |
+--------------------+-------------------------------------------------+
| module save        | If you have modulefiles that you want to load   |
|                    | every time you log in, then you can set up your |
|                    | account so that they are loaded every time you  |
|                    | log in without you having to type the "module   |
|                    | load" every time. Do this by first loading the  |
|                    | modulefiles you always want to have loaded.     |
|                    | Then type "module save". The system will save   |
|                    | your current module list as your default. When  |
|                    | you log in the next time, these modulesfiles    |
|                    | will already be loaded.                         |
+--------------------+-------------------------------------------------+

| 

Note1: Modules are independent of the user???s shell, so any shell (bash,
tcsh, ksh, etc ...) can use the same commands to modify their current
user environment.

Note2: Order is important. With each module load, the changes are
prepended to your current user environment paths.

| 

| 

If you have questions: SUBMIT A TICKET!
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

As we deploy the Nightingale system, we are doing our best to make it
user-friendly and available to users.

| 
