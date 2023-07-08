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
+ Write a program that prints the number of arguments passed into it.
	+ Your program should print a number, followed by a new line

### Program behavior
```bash
amimanye@Manye:~/0x0A-argc_argv$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 1-args.c -o nargs
amimanye@Manye:~/0x0A-argc_argv$ ./nargs
0
amimanye@Manye:~/0x0A-argc_argv$ ./nargs hello
1
amimanye@Manye:~/0x0A-argc_argv$ ./nargs "hello, world"
1
amimanye@Manye:~/0x0A-argc_argv$ ./nargs hello, world
2
amimanye@Manye:~/0x0A-argc_argv$
```
  
### My solution
+ `argc` variable prints the number of arguments but this includes the `argc[0]`
+ since the name of the program is not an argument, we should exclude it.

### Program
```c
#include <stdio.h>

/**
 * main - entry point
 *
 * desc: program to print the number of arguments passed to the main function
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        (void)argv;
        /**
         * casted argv to void to say that argv
         * is intensionally not used in the program
         */

        printf("%d\n", argc - 1);

        return (0);
}
```
  
  
  
## Task 2.
### Instructions
+ Write a program that prints all arguments it receives.
	+ All arguments should be printed, including the first one
	+ Only print one argument per line, ending with a new line

### Program behaviour
```shell
amimanye@Manye:~/0x0A-argc_argv$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 2-args.c -o args
amimanye@Manye:~/0x0A-argc_argv$ ./args
./args 
amimanye@Manye:~/0x0A-argc_argv$ ./args You can do anything, but not everything.
./args
You
can
do
anything,
but
not
everything.
amimanye@Manye:~/0x0A-argc_argv$
```

### My solution
+ `argv[]` is an array of strings
+ just like I would print all elements in an array, I will print all the arguments received by the function
+ index will start from `0` till `argv - 1`

### Program
```c
#include <stdio.h>

/**
 * main - entry point
 *
 * desc: program to print all arguments it receives
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        int i;

        for (i = 0; i < argc; i++)
                printf("%s\n", argv[i]);

        return (0);
}
```


## Task 3.
### Instructions
