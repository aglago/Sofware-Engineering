# Arguments to main function C
This repository contains detailed notes on main function arguments, serving as a comprehensive resource for software engineering enthusiasts, students, and professionals.

## Table of Contents
+ [Requirements](#requirements)
+ [Resources](#resources)
+ [Learning Objectives](#learning-objectives)
+ [Notes](#Notes)
+ [Exercises](#exercises)
+ [Project](#project)
+ [Summary](#summary)
+ [Next Lesson](#next-lesson)

## Requirements
To learn about the main function arguments in C, you should have a basic understanding of the following concepts:
+ C programming language fundamentals, including variables, data types, functions, and control flow.
+ Command-line interface (CLI) and how command-line arguments are passed to programs.
+ Arrays and pointers in C, as the main function's `argv` parameter is an array of character pointers.
+ Standard library functions such as `strcmp`, `fopen`, `fclose`, `printf`, etc., which are commonly used when working with command-line arguments.
+ String manipulation and basic file handling in C.

## Resources
+ [Arguments to main](https://publications.gbdirect.co.uk//c_book/chapter10/arguments_to_main.html)
+ [argc and argv](http://crasseux.com/books/ctutorial/argc-and-argv.html)
+ [What does argc and argv mean?](https://www.youtube.com/watch?v=aP1ijjeZc24)
+ [how to compile with unused variables](https://www.google.com/webhp?q=unused+variable+C)


## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:
+ How to use arguments passed to your program
+ What are two prototypes of main that you know of, and in which case do you use one or the other
+ How to use __attribute__((unused)) or (void) to compile functions with unused variables or parameters


## Notes
+ [Go through notes here](./notes.md)

## Exercises
Below are some practices you can try your hands on to test your understanding of the resources you learnt.
+ [TEST YOUR UNDERSTANDING](./exercises.md) 

## Projects
+ [ALX PROJECT TASKS AND SOLUTIONS](./projects.md)

## Summary
- The main function in C can take two arguments: `int argc` and `char *argv[]`.
- `argc` represents the number of command-line arguments passed to the program and is always at least 1.
- `argv` is an array of character pointers (strings) that holds the command-line arguments.
- The first element of `argv` (`argv[0]`) is the name of the program itself.
- Additional elements of `argv` (`argv[1]`, `argv[2]`, etc.) hold the command-line arguments provided by the user.

Compiling with unused variables:
- In C, when you compile your program, the compiler may generate warnings if you have declared variables that are not used.
- To compile a C program and ignore the warnings for unused variables, you can use the `-Wno-unused-variable` compiler flag.
- For example, if you are using the GCC compiler, you can compile your program with the following command: `gcc -Wno-unused-variable your_program.c -o your_program`
- The `-Wno-unused-variable` flag tells the compiler to suppress warnings related to unused variables, allowing you to compile your program without these warnings.
- It's important to note that while ignoring warnings for unused variables during compilation can be useful in certain situations, it's generally a good practice to remove or properly utilize unused variables in your code to ensure cleaner and more maintainable code.

## Next Lesson
[0x0A. C - argc, argv](../)
