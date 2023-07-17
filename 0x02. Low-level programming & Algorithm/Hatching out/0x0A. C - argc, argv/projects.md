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
+ Write a program that multiplies two numbers.
	+ Your program should print the result of the multiplication, followed by a new line
	+ You can assume that the two numbers and result of the multiplication can be stored in an integer
	+ If the program does not receive two arguments, your program should print `Error`, followed by a new line, and return `1`

### Program behaviour
```shell
amimanye@Manye:~/0x0A-argc_argv$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 3-mul.c -o mul
amimanye@Manye:~/0x0A-argc_argv$ ./mul 2 3
6
amimanye@Manye:~/0x0A-argc_argv$ ./mul 2 -3
-6
amimanye@Manye:~/0x0A-argc_argv$ ./mul 2 0
0
amimanye@Manye:~/0x0A-argc_argv$ ./mul 245 3245342
795108790
amimanye@Manye:~/0x0A-argc_argv$ echo $?
0
amimanye@Manye:~/0x0A-argc_argv$ ./mul
Error
amimanye@Manye:~/0x0A-argc_argv$ ./mul 3 78 49
Error
amimanye@Manye:~/0x0A-argc_argv$ echo $?
1
amimanye@Manye:~/0x0A-argc_argv$
```

### My solution
+ remember that arguments to the main function are only strings?
+ this time we are asked to multiply two numbers
+ `atoi` converts a string to a number and it is from the standard library and `stdlib.h` header file

### Program
```c
#include <stdio.h>
#include <stdlib.h>

/**
 * main - entry point
 *
 * desc: program to multiply two numbers and print results
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        if (argc != 3)
        {
                printf("Error\n");
                return (1);
        }
        else
        {
                printf("%d\n", atoi(argv[1]) * atoi(argv[2]));
        }

        return (0);
}
```

## ## Task 4.
### Instructions
+ Write a program that adds positive numbers.
	+ Print the result, followed by a new line
	+ If no number is passed to the program, print `0`, followed by a new line
	+ If one of the number contains symbols that are not digits, print `Error`, followed by a new line, and return `1`
	+ You can assume that numbers and the addition of all the numbers can be stored in an `int`

### Program behaviour
```shell
amimanye@Manye:~/0x0A-argc_argv$ ./add 1 1
2
amimanye@Manye:~/0x0A-argc_argv$ ./add 1 10 100 1000
1111
amimanye@Manye:~/0x0A-argc_argv$ echo $?
0
amimanye@Manye:~/0x0A-argc_argv$ ./add 1 2 3 e 4 5
Error
amimanye@Manye:~/0x0A-argc_argv$ echo $?
1
amimanye@Manye:~/0x0A-argc_argv$ ./add
0
amimanye@Manye:~/0x0A-argc_argv$ ./add 1 0
1
amimanye@Manye:~/0x0A-argc_argv$ echo $?
0
amimanye@Manye:~/0x0A-argc_argv$
```

### My solution
+ so basically, the arguments taken into the main function are all strings.
+ in order to add them, we have to convert them to integers.
+ I found 3 ways to convert strings to integers

#### Way 1 : `sscanf`
+ `sscanf()`: used to parse strings into numbers.
+ **syntax**: `sscanf (const char* str, const format, ....)` 

```c
#include <stdio.h>

/**
 * main - entry point
 *
 * desc: program to add two positive numbers and print
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        int i, arg, sum = 0;

        if (argc == 1)
                printf("0\n");
        else
        {
                for (i = 1; i < argc; i++)
                {
                        if (sscanf(argv[i], "%d", &arg) == 1)
                                sum += arg;
                        else
                        {
                                printf("Error\n");
                                return (1);
                        }
                }
                printf("%d\n", sum);
        }

        return (0);
}
```
  
  
+ `scanf` function takes the string argument, parses it into an integer by specifying it's format as `%d` and passes the value the the integer varialble `arg`.
+ on successfully parsing, `sscanf` returns `1` which I used as a condition to calculate the sum.

#### Why it was not the best option for this task
+ this worked for almost everything but arguments that have a mixture of numbers and other characters/
+ running the code with arguments: 36 78 9e8 76 prints out 199 instead of `Error`
	+ when `sscanf` gets to the `9e8`, it first parses `9`, when it gets to `e`, it is not a valid character to be converted to a number so `sscanf` stops there and returns `9` and moves to the next argument.
+ `sscanf()` is not betty compliant.
+ betty suggests the use of a less complex function for the problem stated.
+ even so, I am glad I had my own exeperience with the `sscanf()` function.
  
Betty suggests avoiding `sscanf` in favor of simpler and more explicit alternatives, such as `atoi` or `strtol`, which provide clearer intent, better error handling, and improved type safety. By following these recommendations, code readability and maintainability can be enhanced. However, it's important to note that the specific coding conventions may vary depending on the project or organization, so it's always a good practice to follow the style guidelines established by the project you're working on.
  
While Betty discourages the use of `sscanf` in general, it doesn't mean that you can never use `sscanf`. The Betty style checker provides guidelines to promote code simplicity, readability, and best practices, but it does not enforce hard rules.

#### Way 2: `atoi`
+ `atoi` converts string to integer
+ `atoi` returns the integer after conversion and returns 0 when conversion is not successful
+ there can be a conflict where `atoi` returns 0. but is this zero because the conversion was not successful, this 0 is because `atoi` converted a string "0" and the return was zero?
  
**FIRST TRY**  
```c
#include <stdio.h>
#include <stdlib.h>

/**
 * main - entry point
 *
 * desc: program to add two positive numbers and print
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        int i, sum = 0;
        int arg;

        if (argc == 1)
                printf("0\n");
        else
        {
                for (i = 1; i < argc; i++)
                {
                        arg = atoi(argv[i]);
                        if (arg < 0 || (arg == 0 && argv[i][0] != '0'))
                        {
                                printf("Error\n");
                                return (1);
                        }
                        else
                                sum += arg;
                }
                printf("%d\n", sum);
        }

        return (0);
}
```

#### Why this approach failed
+ this worked for almost everything but arguments that have a mixture of numbers and other characters.
+ running the code with arguments: 36 78 9e8 76 prints out 199 instead of `Error`
	+ when `atoi` gets to the `9e8`, it first parses `9`, when it gets to `e`, it is not a valid character to be converted to a number so `atoi` stops there and returns `9` and moves to the next argument.
+ decided to first, loop through all the characters first to find if all are numbers before making the addition or printing `Error` itself.
  
  
  
#### WHay 3: `atoi`
+ Iteration through all characters of arguments to see if each of them is a number.
+ If the iteration meets a character which is not a number, then the sum should be invalid so `Error` is printed
+ If the iteration meets only numbers in all the arguments, then sum will be valid  
  
  
### Progam
```c
#include <stdio.h>
#include <stdlib.h>

/**
 * main - entry point
 *
 * desc: program to add two positive numbers and print
 *
 * @argc: parameter argument count
 * @argv: parameter argument vector
 *
 * Return: 0 for success
 */

int main(int argc, char *argv[])
{
        int i, j, sum = 0;

        if (argc == 1)
                printf("0\n");
        else
        {
                for (i = 1; i < argc; i++)
                {
                        for (j = 0; argv[i][j] != '\0'; j++)
                        {
                                if (argv[i][j] < '0' || argv[i][j] > '9')
                                {
                                        printf("Error\n");
                                        return (1);
                                }
                        }
                        sum += atoi(argv[i]);
                }
                printf("%d\n", sum);
        }

        return (0);
}
```


## Task 5.

### Program
```c
#include <stdio.h>
#include <stdlib.h>

/**
 * main - entry point
 *
 * desc: program returns minimum coins
 * required for change for a given amt
 *
 * @argc: argument count
 * @argv: argument array
 *
 * Return: always 0 if success
 */

int main(int argc, char *argv[])
{
        int i, j, coins = 0, cents;
        int deno[] = {25, 10, 5, 2, 1};

        /** checks for valid number of arguments */
        if (argc != 2)
        {
                printf("Error\n");
                return (1);
        }

        /** checking if each character is a number */
        for (j = 0; argv[1][j] != '\0'; j++)
        {
                if (j == 0 && argv[1][j] == '-')
                {
                        j++;
                        continue;
                }
                if (argv[1][j] < '0' || argv[1][j] > '9')
                {
                        printf("Error\n");
                        return (1);
                }
        }

        /** parsing string to number */
        cents = atoi(argv[1]);

        /** cents should be greater than 1 */
        if (cents < 1)
        {
                printf("0\n");
                return (0);
        }

        /** finding minimum coins */
        for (i = 0; i < 5; i++)
        {
                coins = coins + cents / deno[i];
                cents = cents % deno[i];
        }
        printf("%d\n", coins);

        return (0);
}
```

+ I did this and I love this more because I validate each character of the argument to see if they are numbers. Betty did not allow this because function was more than 40 lines.

### Program
```c
#include <stdio.h>
#include <stdlib.h>

/**
 * main - entry point
 *
 * desc: program returns minimum coins
 * required for change for a given amt
 *
 * @argc: argument count
 * @argv: argument array
 *
 * Return: always 0 if success
 */

int main(int argc, char *argv[])
{
        int i, j, coins = 0, cents;
        int deno[] = {25, 10, 5, 2, 1};

        /** checks for valid number of arguments */
        if (argc != 2)
        {
                printf("Error\n");
                return (1);
        }

        /** parsing string to number */
        cents = atoi(argv[1]);

        /** cents should be greater than 1 */
        if (cents < 1)
        {
                printf("0\n");
                return (0);
        }

        /** finding minimum coins */
        for (i = 0; i < 5; i++)
        {
                coins = coins + cents / deno[i];
                cents = cents % deno[i];
        }
        printf("%d\n", coins);

        return (0);
}
```
+ this was accepted because it was less than 40 lines. but this does not validate if `cents` is a valid number or not. *try ./cents 8e9*
