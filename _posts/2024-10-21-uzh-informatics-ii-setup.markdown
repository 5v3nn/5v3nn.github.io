---
layout: post
title:  "Setup of Informatics II"
date:   2024-10-21 16:20:00 -0400
categories: uzh informatics-ii c
---

This is WIP. 

# Setup of the C Environment

Even though the focus is on algorithms and data structures, the students should
develop a basic to medium understanding in the C programming language. This
post explains how to setup a develop environment for C and the basics in C
(until and excluding pointers and strucutres because they will be explained
later).


## Installation

Find out how to install the `gcc` compiler for your operating system (OS). You
can check if it is installed by opening a terminal (or cmd) and executing the
following command:

```bash
gcc --version
```
 
The output should look something like this:

```
gcc (GCC) 14.2.1 20240805
Copyright (C) 2024 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```


Alternatively, you can use any IDE like C-Lion (or VS Code). However, it is
really fun to play around with the terminal. Also it is a good idea to already
get familiar with this, because in later courses you will have to use it more
extensively. For this blog, I assume you use the terminal to compoile C
scripts.


## Compiling and Running a C Script

Speaking of compiling, what is that? You might be familiar with
Python. Assuming you executed Python scripts in the terminal you would have
used something like this:

```bash
python3 ./my-script.py
```

I do not want to dive into the difference between interpreted languages (like
Python) and compiled languages (like C). I want to use the link to Python as a
nice pickup, in order to show the comparison to compiling and running C
scripts.


C scripts first have to be compiled before they can be run. That is a fancy
word for translating the C script, which is human readable, to a machine
readable file, which can be executed. Without going too deep into compiling,
the naive way to compile a given C script is using the following
command. Please note that you have to navigate to the directory (folder) where
the `my-script.c` is saved, otherwise it will not work. 

```bash
gcc my-script.c
```

You might notice, that after executing that, nothing happened. That is a good
thing. If something failed, you would now see error. But still, where is the
compiled file? That is written by default to a new file called `a.out`. When we
execute the `ls` command, which lists all things in the current directory, we
can see this `a.out` file. Alternatively, you can open your file explorere (or
finder) and navigate to the directory where you executed the compile command
above. You can run the `a.out` file by executing the following command.

```bash
./a.out
```

Note that the `./` in front of the `a.out` are important. We need to explicitly
say that we want to execute a file in the current directory (`./`). For who
want a more detailed explanation, if we do not do that, the OS will saearch in
the `PATH` for an `a.out` command (i.e., file), which it obviously will not
find.





