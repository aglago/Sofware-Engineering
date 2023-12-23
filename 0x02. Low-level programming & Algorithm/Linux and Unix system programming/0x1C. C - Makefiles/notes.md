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

```
Targets Specification
    >>>> all:hello
        >> Target: all
        >> Dependency: hello

    >>>> hello:hello.c
        >> Target: hello
        >> Dependency: hello.c
```

Let's break it down step by step. The "all:hello" line is telling Make that the "all" target depends on the "hello" target. So when you run the make command, it will try to build the "hello" target. The "hello" target depends on the "hello.c" file, so Make will try to find that file. Once it has the "hello.c" file, it will run the recipe, which tells it to use the gcc compiler to build the "hello" executable. So the "hello.c" dependency tells Make what what files it needs to build the "hello" target. The recipe tells Make how to build the "hello" target. And the "all" target is the starting point that tells Make where to begin.

The "all" target is a special target that doesn't depend on any files. Instead, it's used to build other targets, like "hello". So if you were to run the make command without any arguments, it would try to build all of the targets in the makefile, starting with the "all" target. And the "all" target would then build the "hello" target. Does that make sense?

## When, why and how to use Makefiles

**When**

Makefiles are typically used when you have multiple source files that need to be compiled into one executable file. For example, if you had a project with a main.c file, a lib.c file, and a header.h file, you could use a Makefile to compile all of those files into a single executable file. Without a Makefile, you would need to manually compile each file yourself. A Makefile makes it easier to manage multiple source files and ensure that they are all compiled correctly.

**Why**

So why would you want to use a Makefile? There are several reasons. 
- First, Makefiles help to automate the build process. This can save you time and prevent mistakes. 

- Second, Makefiles allow you to specify different build configurations. For example, you could have a development build that includes debugging symbols, or a release build that is optimized for performance. Let's use an example to make it clearer. Let's say you have a C++ project with a main.cpp file, a lib.cpp file, and a header.h file. You could have two different build configurations: a development build and a release build. The development build would include extra information like debug symbols that would help you debug your code. The release build would be optimized for performance, so it would run faster. Using a Makefile, you could specify which build configuration to use when you run the make command. 

- Finally, Makefiles make it easier to build on different platforms or with different compilers. That way, you can be sure that your project will build correctly on any system.

**How**

I'll start with the basic structure of a Makefile. A Makefile is a text file with a specific syntax. The first line of the file must be the name of the target to build. This is typically "all", but it can be any name you choose. The next line should be the dependencies for the target. For example, if you had a target called "all", you could specify that it depends on "main.c", "lib.c", and "header.h". Then, you would need to specify the commands to build the target. For example, you could specify "g++ main.

Let's consider these files as part of our project files:

```
main.c
lib.c
header.h
```

let's write a makefile to compile them. 

We'll go through it step by step! First, we'll need to create a new text file and name it "Makefile". Then, we'll add the following lines:

```
all: main.o lib.o
main.o: main.c
lib.o: lib.c
```

The first line tells Make that the "all" target depends on the "main.o" and "lib.o" targets. The second line tells Make that the "main.o" target depends on the "main.c" file. And the third line tells Make that the "lib.o" target depends on the "lib.c" file. Now, we need to specify the commands to build each target. For the "main.o" target, we'll need to use the "g++" command to compile the "main.c" file. And for the "lib.o" target, we'll need to use the "g++" command to compile the "lib.c"  file.

Okay, now we're getting to the fun part! To complete the "all" target's recipe, we need to link the "main.o" and "lib.o" targets together. To do this, we'll use the "g++" command again, with the "-o" option to specify the output file name. Our final recipe will look like this:

```
all: main.o lib.o
main.o: main.c
lib.o: lib.c
g++ main.o lib.o -o all.exe
```

This will build the "all.exe" executable, but it doesn't do anything with the "header.h" file. To include the "header.h" file, we'll need to add another line to the recipe:

```
header.h:
include main.o lib.o
```

This tells Make to include the contents of the "header.h" file into the "all.exe" executable. Now, we have a complete recipe for our "all" target!


## What are rules and how to set and use them

Rules are the core building blocks of a Makefile. They specify the steps that are needed to create a target. We can add rules to our Makefile by using the "rule" keyword. For example, we could add a rule to our "main.o" target like this:

```
main.o: main.c
g++ -c main.c -o main.o
```

This rule tells Make that to create the "main.o" target, it needs to compile the "main.c" file. And it tells Make to use the "g++" command with the "-c" option to create an object file. 

Basically, what we were referring to earlier as recipes 🤗.


## What are explicit and implicit rules

An explicit rule is a rule that you define explicitly in your Makefile. For example, the rules we've looked at so far are all explicit rules. An implicit rule is a rule that is not defined in your Makefile, but is instead defined by Make itself. For example, the "g++" command we've been using has an implicit rule that tells Make how to build a ".o" object file from a ".c" source file.

An implicit rule is a rule that is defined by Make itself, based on the extension of the target file. In our example, the rule that turns a ".c" file into a ".o" file is an implicit rule because it's not defined in our Makefile. Instead, it's defined by the "g++" command itself. So, whenever we try to create a ".o" file, Make will automatically use the implicit rule to create it from a ".c" file. We don't need to define this rule explicitly because Make already knows how to create it.

