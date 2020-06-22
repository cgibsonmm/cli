# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  SOFTWARE ENGINEERING IMMERSIVE


# Terminal
Working with the MacOS Terminal.


# Objectives
*After this lesson, students will be able to:*
- Understand what the MacOS Terminal is
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


1. My present location is `/Users/username/ga/lessons` and now I want to change directory to `/Users/username/ga`.

  * Using relative path: `cd ..`
  * Using absolute path: `cd /Users/username/ga`

2. My present location is `/Users/username/ga/lessons` and I want to change the location to `/Users/username/ga/labs`

  * Using relative path: `cd ../labs`
  * Using absolute path: `cd /Users/username/ga/labs`

# More Commands

| Command   | Explanation                                                                     |
|-----------|---------------------------------------------------------------------------------|
| `pwd`     | shows in which directory you're currently in                                    |
| `mkdir`   | creates a new directory                                                         |
| `ls`      | lists the contents of the current directory you're in                           |
| `cd`      | moves you to the specified directory*                                           |
| `cd ..`   | goes back one directory                                                         |
| `cd ~`    | takes you to your home directory                                                |
| `touch`   | creates an empty file                                                           |
| `cp`      | copies an existing specified file and pastes it with whatever name you give it  |
| `mv old/path new/path`      | moves an existing specified file to a specified destination   |
| `mv path/filename path/newname` | if paths are the same with a differeent file name, the file's name will be changed                   |
| `rm`      | deletes the specified file                                                      |
| `rm -r`   | deletes the specified directory and all of its contents                         |
| `man`     | open a help manual for a particular command                                     |
| `history` | shows the history of the commands you've typed in your terminal                 |
| `ctrl + r`| search through history of your commands (press enter to execute it)             |
| `ctrl + u`| delete command line                                                             |
| `df -h`   | displays free disk space                                                        |


*Note: If you are using Zsh, you can leave out the `cd` entirely; the directly name itself will move you into it.  

### Examples

Copy command - `cp`

`cp hello.txt bye.txt`


Move command - `mv`

moves an existing specified file to a specified destination

`mv bye.txt ga/`


Manual - `man`

open a help manual for a particular command

`man ls`

