---
title: The In & Out of File I/O
author: Jacob Gadberry
---


# About This Section
This guide will show you how to use File I/O in your C programs.

# What is File I/O?
File I/O stands for File Input/Output. When using C, we can use files outside our program to do different things. For example, we could use a file to read in information to test a program. Alternativley, we could also print information to a file.

Having the ability to read and write to files becomes very helpful when you:
1. Don't want to spend loads of time inputing test cases in the terminal

2. You don't want loads of output clogging up the terminal.
---
# The Code:

```c
#include <stdio.h>

int main(){

    FILE ptr*;
    ptr = fopen("example.txt", "r");

    //Code that does something with the file

    return 0;
}
```

Everything above should look pretty familiar, however two lines are probably new to you. Let's break them down.

```c
    FILE ptr*;
```
Here we declare a reference to a file.

```c
    ptr = fopen("example.txt", "r");
```
Next, we point our pointer at the file we would like to look at.
```c
    fopen("example.txt", "r");
```
fopen takes in two parameters: 
1. The name of the file you are looking for.
2. What kind of file mode you want to be in.

## Quick Aside About File Modes
While there are many different file modes, for COP 3223, you will only need to worry about two main ones: "r" and "w".

|Mode       |           |
|:----------|:----------|
|"r"        |     Stands for Read. Opens a file and allows the programmer to READ information from the file. Programmer will not be able to change the contents of the file itself.      |
|"w"         |    Stands for Write. Opens a file and allows the programmer to WRITE information onto the file. **Becareful! If you write to an already written file, the old contents will be overwritten!**       |

---

# One Important Check Before We Start
Before we start to do anything with our files, we need to check that our computer found the file in the first place.

```c
    if(ptr == NULL){
        printf("File not found!");
        return 0;
    }
```
We add this line of code to act as a safegaurd against a file pointer that points to nothing. If the pointer is NULL then we can't do anything, so it is appropriate to break out of our main function.

# Using The Read Mode
When reading from a file 

# Using The Write Mode
When reading from a file 