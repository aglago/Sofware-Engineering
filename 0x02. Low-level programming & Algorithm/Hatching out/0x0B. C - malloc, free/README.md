# Malloc and free functions
This repository contains detailed notes on `malloc` and `free` functions, serving as a comprehensive resource for software engineering enthusiasts, students, and professionals.

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
To learn about memory allocation and memory dellocation, you should have a basic understanding of the following concepts:
+ Basic knowledge of C programming.
+ Understanding of pointers and their usage.
+ Familiarity with memory management concepts.
+ Knowledge of dynamic memory allocation.
+ Understanding the purpose and functionality of malloc and free.
+ Ability to handle memory allocation failures.
+ Awareness of memory leaks and how to avoid them.
+ Knowledge of appropriate use cases for dynamic memory allocation.
+ Understanding the potential risks and challenges associated with dynamic memory allocation.


## Resources
+ [Dynamic memory allocation in C - malloc calloc realloc free (stop at 6:50)](https://www.youtube.com/watch?v=xDVC3wKjS64)

### man or help:
+ `malloc`
+ `free`

## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:
+ What is the difference between automatic and dynamic allocation
+ What is malloc and free and how to use them
+ Why and when use malloc
+ How to use valgrind to check for memory leak

## Notes
+ [Go through notes here](./notes.md)

## Exercises
Below are some practices you can try your hands on to test your understanding of the resources you learnt.
+ [TEST YOUR UNDERSTANDING](./exercises.md) 

## Projects
+ [ALX PROJECT TASKS AND SOLUTIONS](./projects.md)

## Summary
In summary, `malloc` and `free` are functions in the C programming language that facilitate dynamic memory allocation and deallocation.

- `malloc` (Memory Allocation) is used to dynamically allocate a block of memory on the heap. It takes the size of the memory block to allocate as an argument and returns a void pointer (`void*`) to the beginning of the allocated memory block. It allows you to request memory at runtime and is commonly used when the size of the memory needed is not known in advance.

- `free` is used to deallocate memory that was previously allocated dynamically using `malloc`, `calloc`, or `realloc`. It takes a pointer to the memory block as an argument and releases the memory, making it available for reuse. It's essential to free dynamically allocated memory to prevent memory leaks and efficiently manage memory resources.

Together, `malloc` and `free` provide a mechanism for managing memory dynamically during program execution. They enable you to allocate and deallocate memory blocks as needed, allowing for flexibility in memory usage. However, it's important to use them carefully to avoid issues such as memory leaks, accessing freed memory, or undefined behavior.


## Next Lesson
[Professional Social Presence](../)
