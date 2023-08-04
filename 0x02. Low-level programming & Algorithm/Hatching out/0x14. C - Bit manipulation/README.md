# C - Bit Manipulation
This repository contains detailed notes on Bit Manipulation in C, serving as a comprehensive resource for software engineering enthusiasts, students, and professionals.

## Table of Contents
+ [Requirements](#requirements)
+ [Resources](#resources)
+ [Learning Objectives](#learning-objectives)
+ [Notes](#Notes)
+ [Project](#project)
+ [Summary](#summary)
+ [Next Lesson](#next-lesson)

## Requirements
+ Linux perating system: Ubuntu 20.04
+ Ubuntu 20.04 (at Microsoft Store for windows users)
+ Allowed editors: vi, vim, emacs
+ All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
+ All your files should end with a new line
+ There should be no errors and no warnings during compilation
+ You are not allowed to use system
+ Your codes should use the Betty style.

### Betty Linter
To run Betty linter with command: `betty <filename>`
+ Go to the [Betty](https://intranet.alxswe.com/rltoken/QkZtBg3ps5iLBlUdX-CPJQ) repository
+ Clone the [repo](https://intranet.alxswe.com/rltoken/QkZtBg3ps5iLBlUdX-CPJQ) to your local machine
+ `cd` into the Betty directory
+ Install the linter with `sudo ./install.sh`
+ `emacs` or `vi` a new file called betty, and copy the script below:

```bash
#!/bin/bash
# Simply a wrapper script to keep you from having to use betty-style
# and betty-doc separately on every item.
# Originally by Tim Britton (@wintermanc3r), multiargument added by
# Larry Madeo (@hillmonkey)

BIN_PATH="/usr/local/bin"
BETTY_STYLE="betty-style"
BETTY_DOC="betty-doc"

if [ "$#" = "0" ]; then
    echo "No arguments passed."
    exit 1
fi

for argument in "$@" ; do
    echo -e "\n========== $argument =========="
    ${BIN_PATH}/${BETTY_STYLE} "$argument"
    ${BIN_PATH}/${BETTY_DOC} "$argument"
done
```
+ Once saved, exit file and change permissions to apply to all users with `chmod a+x betty`
+ Move the `betty` file into `/bin/` directory or somewhere else in your `$PATH` with `sudo mv betty /bin/`  
You can now type `betty <filename>` to run the Betty linter!


## Resources
### Read or watch:
+ [Everything you need to know to start with C](https://intranet.alxswe.com/rltoken/8zpFqe7xb3eRZGK3WferKg)
+ [Dennis Ritchie](https://en.m.wikipedia.org/wiki/Dennis_Ritchie)
+ [“C” Programming Language: Brian Kernighan](https://youtu.be/de2Hsvxaf8M)
+ [Why C Programming Is Awesome](https://youtu.be/smGalmxPVYc)
+ [Learning to program in C part 1](https://youtu.be/rk2fK2IIiiQ)
+ [Learning to program in C part 2](https://youtu.be/FwpP_MsZWnU)
+ [Understanding C program Compilation Process](https://youtu.be/VDslRumKvRA)
+ [Betty Coding Style](https://github.com/alx-tools/Betty/wiki)
+ [Hash-bang under the hood](https://twitter.com/unix_byte/status/1024147947393495040?t=4uEbR3x01VMxYKvyn8mT5Q&s=19)
+ [Linus Torvalds on C vs. C++](http://harmful.cat-v.org/software/c++/linus)
  
## man or help:
+ `gcc`
+ `printf (3)`
+ `puts`
+ `putchar`

## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:
+ Why C programming is awesome
+ Who invented C
+ Who are Dennis Ritchie, Brian Kernighan and Linus Torvalds
+ What happens when you type gcc main.c
+ What is an entry point
+ What is main
+ How to print text using printf, puts and putchar
+ How to get the size of a specific type using the unary operator sizeof
+ How to compile using gcc
+ What is the default program name when compiling with gcc
+ What is the official C coding style and how to check your code with betty-style
+ How to find the right header to include in your source code when using a standard library function
+ How does the main function influence the return value of the program


## Notes
+ [Go through notes here](./notes/)

  
## Projects
+ [ALX PROJECT TASKS AND SOLUTIONS](./projects.md)

## Summary
The C "Hello, World!" program is a simple program that serves as a starting point for learning the C programming language. It typically consists of a few lines of code that display the message "Hello, World!" on the screen. Here's a summary of the program:  
  
1. **Include the necessary header file**: In C, we begin by including the necessary header files that provide the required functions and definitions. For the "Hello, World!" program, we need to include the `<stdio.h>` header file, which provides the standard input/output functions.  
  
2. **Write the main function**: In C, every program starts execution from the `main` function. The `main` function serves as the entry point for the program. It has a return type of `int`, indicating that it should return an integer value.  

3. **Write the code to display the message**: Inside the `main` function, we use the `printf` function from the `<stdio.h>` header file to display the "Hello, World!" message on the screen. The `printf` function takes a format string as an argument, which contains the text to be displayed. In this case, the format string is "Hello, World!\n".  

4. **Return from the main function**: After displaying the message, we use the `return` statement to exit the `main` function and return a value to the operating system. In the case of the "Hello, World!" program, we usually return `0` to indicate successful execution.  
  
Here's the code for the "Hello, World!" program in C:

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
When you compile and run this program, it will display the message "Hello, World!" on the screen. The program is often used as a first step in learning C and verifying that the development environment is set up correctly.


## Next Lesson
[0x01. C - Variables, if, else, while](../)
