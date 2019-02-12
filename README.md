# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  WEB DEVELOPMENT IMMERSIVE


# Terminal
Working with the MacOS Terminal.


# Objectives
*After this lesson, students will be able to:*
- Undertsand what the MacOS Terminal is
- Navigate MacOS using Terminal commands
- Manipulate files and folder on their machine using Terminal commands


# What is the Terminal?

### Let's open it:


- <kbd>⌘</kbd> + <kbd>Space</kbd> (Command + spacebar)
- "Terminal"
- Enter

The terminal is a tool developers use to execute instructions to a computer. It's the developer's best friend! Through the terminal one can navigate through files and folders with speed. We can write scripts to automate common tasks and run them in the terminal.

# Modifier keys? 
![Mac Keyboard modifier keys](https://cdn.osxdaily.com/wp-content/uploads/2018/01/apple-keyboard-modifier-keys.jpg)

MacOS Shortcut Keys: https://support.apple.com/en-us/HT201236

## Paths

Every file or folder in a file system can be read, written, and deleted by referencing its position inside the file system. When we talk about the position of a file or a folder in a file system, we refer to its "path". There are a couple of different kinds of paths we can use to refer to a file – **absolute paths** and **relative paths**.

*Directory* is an important term that's used interchangeably with *folder*. Though they are not exactly the same thing, when we say "navigate to your project directory" think of this as "navigate to your project folder".  Here's a little more information:

_Strictly speaking, there is a difference between a directory which is a file system concept, and the graphical user interface metaphor that is used to represent it (a folder)...If one is referring to a container of documents, the term folder is more appropriate. The term directory refers to the way a structured list of document files and folders is stored on the computer. It is comparable to a telephone directory that contains lists of names, numbers and addresses and does not contain the actual documents themselves._

*Taken from [Close-To-Open Cache Consistency in the Linux NFS Client](http://www.citi.umich.edu/projects/nfs-perf/results/cel/dnlc.html)*

# What is an Absolute Path?

An absolute path is defined as the specific location of a file or folder from the root directory, typically shown as `/`. The root directory is the starting point from which all other folders are defined and is not normally the same as your **Home** directory, which is normally found at `/Users/[Your Username]`.

# Working with Unix Commands and File Paths

Typing `cd` - a command for "change directory" with no parameters takes us to our home directory.

```bash
cd
```

If we type in `pwd` - a command for "print working directory" from that folder, we can see where we are in relation to the root directory.

Some examples of absolute path:

```bash
/usr/local/bin/git
/etc/example.ext
/var/data/database.db

```

Notice, all these paths started from `/` directory which is a root directory for every Linux/Unix machines.

# What is a Relative Path?
> *Note:* Instructors – customize this lesson to demo with folders that you have present on your filesystem, or alternatively create a similar file structure on the fly.

A relative path is a reference to a file or folder **relative** to the current position, or the present working directory(pwd). If we are in the folder `/a/b/` and we want to open the file that has the absolute path `/a/b/c/file.txt`, we can just type:

```bash
open c/file.txt
```

or

```bash
open ./c/file.txt
```

At any time, we can also use the absolute path, by adding a slash to the beginning of the path. The absolute path is the same for a file or a folder regardless of the current working directory, but relative paths are different, depending on what directory we are in.  Directory structures are laid out like `directory/subdirectory/subsubdirectory`.

Below are some examples of using relative and absolute path for the same action:


1. My present location is `/Users/bruno/ga/lessons` and now I want to change directory to `/Users/bruno/ga`.

  * Using relative path: `cd ..`
  * Using absolute path: `cd /Users/bruno/ga`

2. My present location is `/Users/bruno/ga/lessons` and I want to change the location to `/Users/bruno/ga/labs`

  * Using relative path: `cd ../labs`
  * Using absolute path: `cd /Users/bruno/ga/labs`

# More Commands

`pwd`

shows in which directory you're currently in

`mkdir`

creates a new directory

`ls`

lists the contents of the current directory you're in

`cd`

moves you to the specified directory

`cd ..`

goes back one directory

`cd ~`

takes you to your home directory

`touch`

creates an empty file

`cp`

copies an existing specified file and pastes it with whatever name you give it

`cp hello.txt bye.txt`

`rm`

deletes the specified file

`mv`

moves an existing specified file to a specified destination

`mv bye.txt ga/`

`rm -rf`

deletes an entire directory including all of its contents! Be careful with this one.

`rm -rf ga`

`man`

open a help manual for a particular command

`man ls`

`history`

shows the history of the commands you've typed in your terminal

# UNIX Permissions and chmod

> Note: Update the narrative to reflect your own OS.

An OS is meant to serve many users, A user may correspond to a real-world person, but also a program that acts as a specific user. In my laptop OS, I am "Gerry" and with gerry goes a set of permissions and restrictions on all files and folders, But I can also act for some specific program as the user "www" which corresponds to the privileges necessary to operate the local web server. Every User on the OS has a User ID - the name "Gerry" or "www" is just an alias for a User ID.

Users can be organized in groups. A user may be in one or several groups. A group will have the same set of permissions for every user assigned to this group.

Every file has an owner user and an owner group. So, for any file in the system, user 'gerry' may have one of the following ownership relations:

* gerry owns the file, i.e. the file's owner is 'gerry'.
* gerry is a member of the group that owns the file, i.e. the file's owner group is 'wdi'.
* gerry is neither the owner, nor belonging to the group that owns the file.

Every file on the system has associated with it a set of permissions. Permissions tell UNIX what can be done with that file and by whom. There are three things you can do with a given file:

* read it.
* write it.
* execute it.

Permissions for a file will specify which of the three actions above can be performed for groups and users in an OS.

For every file, there is 3 types of permissions: permissions for the owner, for the group owner and for everyone else. Remember that there are three possibles actions a user can take on a file - read (r), write (w), execute (x) - so for each of the three permissions we need three actions.


If you change the present working directory to the root (`cd /`) and then show the folder content with the details by typing `ls -l` on the command prompt, you will get something like this:

```bash
 0 drwxrwxr-x+ 93 root  admin  3162 Aug 15 19:37 Applications
 0 drwxr-xr-x+ 66 root  wheel  2244 Jan 18  2015 Library
 0 drwxr-xr-x@  2 root  wheel    68 Sep  9  2014 Network
 0 drwxr-xr-x+  4 root  wheel   136 Jan 18  2015 System
 8 lrwxr-xr-x   1 root  wheel    49 Apr 14  2014 User Information -> /Library/Documentation/User Information.localized
 0 drwxr-xr-x   6 root  admin   204 Jan 18  2015 Users
 0 drwxrwxrwt@  5 root  admin   170 Aug 15 16:35 Volumes
 0 drwxr-xr-x@ 39 root  wheel  1326 Apr 28 21:05 bin
 0 drwxrwxr-t@  2 root  admin    68 Sep  9  2014 cores
 0 drwxr-xr-x   3 root  wheel   102 Sep  8  2014 data
10 dr-xr-xr-x   3 root  wheel  4805 Aug 14 11:45 dev
 8 lrwxr-xr-x@  1 root  wheel    11 Jan 18  2015 etc -> private/etc
 2 dr-xr-xr-x   2 root  wheel     1 Aug 15 19:42 home
 2 dr-xr-xr-x   2 root  wheel     1 Aug 15 19:42 net
 0 drwxr-xr-x@  6 root  wheel   204 Jan 18  2015 private
 0 drwxr-xr-x@ 59 root  wheel  2006 Apr 28 21:05 sbin
 8 lrwxr-xr-x@  1 root  wheel    11 Jan 18  2015 tmp -> private/tmp
 0 drwxr-xr-x@ 12 root  wheel   408 Jan 18  2015 usr
 8 lrwxr-xr-x@  1 root  wheel    11 Jan 18  2015 var -> private/var

```

The second column corresponds to the permissions details for each file/folder. For the first line:

```
drwxrwxr-x+
```
We're not going to talk about the `d` letter at the start or the `+` at the end of each line for the moment. Just pay attention to the nine letters between.

The important part in this set of characters is:

```
rwxrwxr-x
```

This can be read:
```
rwx rwx r-x
```
This breaks down like this:

- first group of three letters corresponds to the owner permission,
- the second group of three letters corresponds to the owner group permission,
- the last group of three letters corresponds to others permission,

# `chmod`

To modify a file's permissions you need to use the `chmod` command.

Only the owner of a file may use chmod to alter a file's permissions.

chmod has the following syntax:

```
chmod [options] mode file(s)
```

The 'mode' part specifies the new permissions for the file(s) that follow as arguments. A mode specifies which user's permissions should be changed, and afterwards which access types should be changed. Let's say for example:

```
chmod a-x file.txt
```

This means that the execute bit should be cleared (-) for all users - owner, group and the rest of the world. The permissions start with a letter specifying what users should be affected by the change, and this might be any of the following:


* u the owner user
* g the owner group
* o others (neither u, nor g)
* a all users

You might have encountered things like `chmod 755 a_file.txt`.

You can change the entire permission pattern of a file in one go using one number like the one in this example. Every mode has a corresponding code number, and as we shall see, there is a very simple way to figure out what number corresponds to any mode.


Every single digit in the triplet corresponds to the level of authorization for a group (user, group and others). Every digit is the addition of the rights for this group, and every level of permission corresponds to a number:

* 4 for r.
* 2 for w.
* 1 for x.

So if a file has rwxr-xr-x permissions we do the following calculation:

* Triplet for u: rwx => 4 + 2 + 1 = *7*
* Triplet for g: r-x => 4 + 0 + 1 = *5*
* Triplet for o: r-x => 4 + 0 + 1 = *5*
Which makes : 755

So, 755 in UNIX permissions means 'I don't mind if other people read or run this file, but only I should be able to modify it' while 777 means 'everyone has full access to this file'


## Customize the Terminal

## When using bashrc

When a terminal session starts, there are some configurations read at the start of the session. The configuration is written in a file that has a specific name. As we run `bash`, the file name for this type of shell is called `.bashrc` and is located in the user folder, so every user for the same machine can have different configurations. `rc` stands for "Run Control" and is an old Unix convention.

If you open the file `.bashrc` using the command `code ~/.bashrc`, you'll see your own config file for bash.

You can add code to this file and it will be parsed and/or executed every time you open a new window/tab.  You can add custom commands, aliases, redefine your path etc.

One of the most important params in this file is the `$PATH` definition, let's see what this is about in the next section.


# $PATH

You’ll hear about _shell path_ (or $PATH) when working with the command line. The _shell path_ in OS X (or Linux) refers to a list of folders in the file system that contains files or executables that will be used by certain applications and programs.

The $PATH is useful in a way that you will not need to type to absolute path  of a command if the folder where this command is contained is already in the path.

When a command is typed in the terminal, as search will be performed by the OS to see if the command exists in the folders referenced by the path.

For example, the path that allows you to run the command `git` in the terminal like this:

```bash
$ git
```

Instead of having to run:

```bash
$ /usr/local/bin/git
```

The $PATH contains several absolute paths, and they are all separated by colons **:**

The _path_ is a bunch of absolute paths of the file system separated by colons **:**


You can show your $PATH by typing

```bash
$ echo $PATH
```

The result should be something like:

```bash
/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin
```

The path above is actually a list of 5 different paths:

* /usr/bin
* /bin
* /usr/sbin
* /sbin
* /usr/local/bin


#### Customizing the path

You can add folders in the $PATH by adding in the bash (or zsh) config file. If you open you terminal config file, you’ll see a line looking like:

```bash
export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:~/bin:$PATH"
```

(the folders may be different in your PATH)

Let’s describe this line:

* `export PATH=""` : This tells the terminal to send the variable named PATH to the terminal sessions so that the variable is always accessible.
* `/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:~/bin` This is the list of folders that are defined in the path.
* `:$PATH` : the PATH variable can be defined is several files and by different programs, so at the end of re-defining the path, adding `:$PATH` means that all the PATH definitions made in other config files will be added to the new definition.

In this path definition, we could add a new path to a folder, for example, if we transform this path:

```bash
export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:~/bin:$PATH"
```

...to this path:

```bash
export PATH="/a/b/c:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:~/bin:$PATH"
```

Now every new terminal session will include the commands (executable files) in the folder `/a/b/c`


The orders of the folders in the path matters. For example, in the path above, if there is one executable file called `wdi` in the folder `/a/b/c` and another one with the same name in the folder `/usr/local/bin`, then the one executed when the command `wdi` is invoked and will be the command in the folder `/a/b/c` because of the precedence in the path.

