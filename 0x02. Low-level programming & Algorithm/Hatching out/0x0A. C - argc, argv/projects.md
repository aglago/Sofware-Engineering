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
+ Write a program that prints its name, followed by a new line.
	+ If you rename the program, it will print the new name, without having to compile it again
	+ You should not remove the path before the name of the program

### Program behaviour
```bash
amimanye@Manye:~0x0A-argc_argv$ vi 0-whatsmyname.c
amimanye@Manye:~/0x0A-argc_argv$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 0-whatsmyname.c -o mynameis
amimanye@Manye:~/0x0A-argc_argv$ ./mynameis
./mynameis
amimanye@Manye:~/0x0A-argc_argv$ mv mynameis mynewnameis
amimanye@Manye:~/0x0A-argc_argv$ ./mynewnameis
./mynewnameis
amimanye@Manye:~/0x0A-argc_argv$
```

### My solution
+ syntax of main function with arguments is: `int main(int argc, char *argv[])`
+ `argv[0]` prints the name of any program
+ casting the `argc` variable inside the main function tells the compiler that that variable was intensionally not used.

### Program
```c
#include <stdio.h>

/**
 * main - entry point
 *
 * desc: program to print program's name using arguments to main function
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        (void)argc; /** casted argc to void to indicate it is intentionally unused */
        printf("%s\n", argv[0]);

        return (0);
}
```

## Task 1.
### Instructions
