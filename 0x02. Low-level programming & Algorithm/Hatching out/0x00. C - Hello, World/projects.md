+ Inspired by [ALX](https://www.alxafrica.com/)

# Table of Content
+ [Task 0](#task-0)
+ [Task 1](#task-1)
+ [Task 2](#task-2)
+ [Task 3](#task-3)
+ [Task 4](#task-4)
+ [Task 5](#task-5)
+ [Task 6](#task-6)
+ [Contact](#get-in-touch-with-me)

## Task 0.
### Instructions
Write a script that runs a C file through the preprocessor and save the result into another file.

+ The C file name will be saved in the variable `$CFILE`
+ The output should be saved in the file c`

## Task 1.
Write a script that compiles a C file but does not link.

+ The C file name will be saved in the variable $CFILE
+ The output file should be named the same as the C file, but with the extension .o instead of .c.
+ Example: if the C file is main.c, the output file should be main.o

## Task 2.
### Instructions
Write a script that generates the assembly code of a C code and save it in an output file.

The C file name will be saved in the variable $CFILE
The output file should be named the same as the C file, but with the extension .s instead of .c.
Example: if the C file is main.c, the output file should be main.s

## Task 3.
### Instructions
Write a script that compiles a C file and creates an executable named cisfun.

The C file name will be saved in the variable $CFILE

## Task 4.
### Instructions
Write a C program that prints exactly "Programming is like building a multilingual puzzle, followed by a new line.

Use the function puts
You are not allowed to use printf
Your program should end with the value 0

### Exoected behavior
![puts](../images/puts.png)

### solution
[Task 4 file]()

### Note
+ puts() is a function that prints out a string
+ the use of backslash is used to escape special characters


`puts()` is a standard library function in C that is used to write a string to the standard output (stdout). It is declared in the `<stdio.h>` header file.
  
The syntax of puts() is as follows:

```c
int puts(const char *str);
```
str is a pointer to the null-terminated string that you want to print.
The function returns a non-negative value on success, or EOF (which is typically -1) on failure.

Here's an example of how you can use `puts()`:

```c
#include <stdio.h>

int main() {
    const char *message = "Hello, World!";
    
    puts(message);
    
    return 0;
}
```
In this example, the string "Hello, World!" is assigned to the message pointer. The `puts()` function is then used to print the string to the standard output. 
+ The trailing newline character is automatically appended by `puts()`. 
+ Finally, the program returns 0 to indicate successful execution.
  
When you run this program, it will output:

```
Hello, World!
```
Note that `puts()` is a simple function and does not provide the same level of control and flexibility as other output functions like `printf()`. It is primarily used for simple string printing purposes.
