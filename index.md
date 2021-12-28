# Linux Fundamentals

## High Level Goals

By the end of this lesson, you will be familiar with the following:

1. A Bit of Background on Kali Linux
2. What is Terminal and running our first few commands
3. File System commands
4. Searching for Files
5. starting with Shell Operators

## A Bit of Background on Kali Linux

Kali Linux is an open-source project that aims to provide advanced Penetration Testing and security auditing tools. It contains hundreds of tools that are designed to address various security tasks, such as Computer Forensics and Security Research.

## What is Terminal and running our first few commands

The "Terminal" it is a text-based interface that allows you to enter commands, execute them, and view the results.

    → This is what a terminal looks like
    ┌──(tetra㉿kali)-[~]
    └─$ enter commands here

Let's get started with two of the first commands, which I have broken down in the table below:

| Command | Description                                      |
| ------- | ------------------------------------------------ |
| echo    | Output any text that we provide                  |
| whoami  | Find out what user we're currently logged in as! |

    → Using echo
    ┌──(tetra㉿kali)-[~]
    └─$ echo Hello World
     Hello World

    → using whoami
    ┌──(tetra㉿kali)-[~]
    └─$ whoami
     tetra

## File System commands

| Command | Full Name               |
| ------- | ----------------------- |
| ls      | listing                 |
| cd      | change directory        |
| cat     | concatenate             |
| pwd     | print working directory |

### Listing Files in Our Current Directory (ls)

This `ls` command will help us identify the contents of all files and folders in our system.

    → Using "ls" to to list the contents of the current directory
    ┌──(tetra㉿kali)-[~]
    └─$ ls
    'Download' 'My Documents' 'Notes' 'Pictures'

> _Pro tip: You can list the contents of a directory without having to navigate to it by using **ls** and the name of the directory. I.e. `ls Pictures`_

### Changing Our Current Directory (cd)

we need to use the **`cd`** command (short for **c**hange **d**irectory) to change to that directory.

     → using cd
    ┌──(tetra㉿kali)-[~]
    └─$ cd Pictures

    ┌──(tetra㉿kali)-[~/Pictures]
    └─$ ls
    dog_picture1.jpg cat_picture1.jpg dog_picture2.jpg cat_picture2.jpg

### Outputting the Contents of a File (cat)

In this tutorial, we'll talk about a command called **cat**, which will output the contents of text files.
┌──(tetra㉿kali)-[~/Documents]
└─$ ls
todo.txt
→ Using cat
┌──(tetra㉿kali)-[~/Documents]
└─$ cat todo.txt
This is the what cat showing for us!

We've applied some knowledge from earlier in this section to do the following:

1. Used **`ls`** to let us know what files are available in the "Documents" folder of this machine. In this case, it is called "todo.txt".
2. We have then used `cat todo.txt` to concatenate/output the contents of this "todo.txt" file, where the contents are "Here's something important for me to do later

> _Pro tip: You can also output the contents of a file without having to navigate it by using cat.. `cat /home/Kali/Documents/todo.txt`_

### Finding out the full Path to our Current Working Directory (pwd)

It's easy to lose track of where we are on the file system exactly, which is why I want to introduce **`pwd`**. This stands for **p**rint **w**orking **d**irectory.

    ┌──(tetra㉿kali)-[~/Documents]
    └─$ pwd
    /home/tetra/Documents

## Searching for Files

One fantastic way to show just how efficient you can be with systems like this is using a set of commands to quickly search for files across the entire system that our user has access to. No need to consistently use `cd` and `ls` to find out what is where. we can will use command `find`.

### **Using Find**

Take the snippet below, we can see a list of directories available to us:

    ┌──(tetra㉿kali)-[~]
    └─$ ls
    Desktop Documents Pictuers folder1

    ┌──(tetra㉿kali)-[~]
    └─$ find -name passwords.txt
    ./folder1/passwords.txt

**"Find"** has managed to _find_ the file — it turns out it is located in folder1/passwords.txt.

We can use what's known as a wildcard **(\*)** to search for anything that has .txt at the end.

    ┌──(tetra㉿kali)-[~]
    └─$ find -name *.txt
    ./folder1/passwords.txt
    ./Documents/todo.txt

Find has managed to _find_:

1. "passwords.txt" located within "folder1"
2. "todo.txt" located within "Documents"

## starting with Shell Operators

**Shell-operator** is a tool for running event-driven scripts in a Kubernetes cluster.

| Symbol / Operator | Description                                                                                                                                      | How we use it                                                                                                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| &                 | This operator allows you to run commands in the background of your terminal.                                                                     | The "&" shell operator allows us to execute a command and have it run in the background (such as this file copy) allowing us to do other things!                                            |
| &&                | This operator allows you to combine multiple commands together in one line of your terminal.                                                     | for example `command1 && command2`. However, it's worth noting that `command2` will only run if `command1` was successful.                                                                  |
| >                 | This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere. | Let's say we wanted to create a file named "welcome" with the message "hello world". We can run `echo hello world > welcome` where we want the file created with the contents "hello world" |
| >>                | This operator does the same function of the `>` operator but appends the output rather than replacing (meaning nothing is overwritten).          | The `>>` operator allows to append the output to the bottom of the file — rather than replacing the contents `echo hello >> welcome`                                                        |

## Practice

You Can answer these Question in this form [add Google form]

1. What year was the first release of a Linux operating system?

2. If we wanted to output the text "**MerakiAcademy**", what would our command be?

3. If we wanted to run a command in the background, what operator would we want to use?

4. If I wanted to replace the contents of a file named "passwords" with the word "password123", what would my command be?

5. Now if I wanted to add "MerakiAcademy" to this file named "passwords" but also keep "passwords123", what would my command be.
