# Learning Objectives 

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- What are make, Makefiles
- When, why and how to use Makefiles
- What are rules and how to set and use them
- What are explicit and implicit rules
- What are the most common / useful rules
- What are variables and how to set and use them

# Answers

## What are make, Makefiles?

Make and Makefiles are related tools that are used in software development. Make is a tool that is used to automate the process of building and compiling software, while Makefiles are configuration files that are used by Make to specify the steps that should be taken to build the software. Make and Makefiles are particularly useful when you need to build large projects with many different files.

**Make**

Let's start with Make. As I mentioned, Make is a tool that automates the process of building software. When you use Make, you create a "makefile" that contains the instructions for how to build the software. This makefile can then be used to generate the executable file for the software. Make can also be used to rebuild the software if any of the source files have been changed.

Let's say you have a simple C program called "hello.c" that prints the message "Hello, world!" when it is executed. If you want to use Make to build this program, you would create a makefile that looks something like this:

all: hello
hello: hello.c
gcc hello.c -o hello

This makefile tells Make to build the program "hello" from the source file "hello.c". It also tells Make to use the gcc compiler to compile the program.

**Makefiles**
As I mentioned, Makefiles are configuration files that are used by Make. They use a special syntax to specify the steps that should be taken to build the program. For example, the "all" and "hello" lines in the makefile are targets specifications, whereas the "all" and "hello" keywords are called targets.These targets are the end goals of the makefile, in our example the "hello" target is what we want to build, is the executable file we want to end up with. Tha "all" target is a specual target that is used to build all of the other targets in the makefile like "docs" fkr documentations, "tests" target that runs unit tests.

The lines that start with ":" are called dependencies, and they tell Make which files are needed to build the target. 

Targets Specification
    >>>> all:hello
        >> Target: all
        >> Dependency: hello

    >>>> hello:hello.c
        >> Target: hello
        >> Dependency: hello.c

Let's break it down step by step. The "all:hello" line is telling Make that the "all" target depends on the "hello" target. So when you run the make command, it will try to build the "hello" target. The "hello" target depends on the "hello.c" file, so Make will try to find that file. Once it has the "hello.c" file, it will run the recipe, which tells it to use the gcc compiler to build the "hello" executable. So the "hello.c" dependency tells Make what what files it needs to build the "hello" target. The recipe tells Make how to build the "hello" target. And the "all" target is the starting point that tells Make where to begin.

The "all" target is a special target that doesn't depend on any files. Instead, it's used to build other targets, like "hello". So if you were to run the make command without any arguments, it would try to build all of the targets in the makefile, starting with the "all" target. And the "all" target would then build the "hello" target. Does that make sense?

## When, why and how to use Makefiles