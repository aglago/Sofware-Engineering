+ Inspired by [ALX](https://www.alxafrica.com/)

# Table of Content
+ [Task 0](#task-0)
+ [Task 1](#task-1)
+ [Task 2](#task-2)
+ [Task 3](#task-3)
+ [Task 4](#task-4)
+ [Task 5](#task-5)
+ [Task 6](#task-6)
+ [Task 7](#task-7)
+ [Contact](#get-in-touch-with-me)

## Task 0.
### Instructions
+ Write a function that creates an array of chars, and initializes it with a specific char.
	+ Prototype: char \*create_array(unsigned int size, char c);
	+ Returns NULL if size = 0
	+ Returns a pointer to the array, or NULL if it fails
+ To test your function, you can test it against this C program below
```c
#include "main.h"
#include <stdio.h>
#include <stdlib.h>

/**
 * simple_print_buffer - prints buffer in hexa
 * @buffer: the address of memory to print
 * @size: the size of the memory to print
 *
 * Return: Nothing.
 */
void simple_print_buffer(char *buffer, unsigned int size)
{
    unsigned int i;

    i = 0;
    while (i < size)
    {
        if (i % 10)
        {
            printf(" ");
        }
        if (!(i % 10) && i)
        {
            printf("\n");
        }
        printf("0x%02x", buffer[i]);
        i++;
    }
    printf("\n");
}

/**
 * main - check the code for ALX School students.
 *
 * Return: Always 0.
 */
int main(void)
{
    char *buffer;

    buffer = create_array(98, 'H');
    if  (buffer == NULL)
    {
        printf("failed to allocate memory\n");
        return (1);
    }
    simple_print_buffer(buffer, 98);
    free(buffer);
    return (0);
}
```

### Program behaviour
```
amimanye@Manye:~/0x0a. malloc, free$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 0-main.c 0-create_array.c -o a
amimanye@Manye:~/0x0a. malloc, free$ ./a 
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
0x48 0x48 0x48 0x48 0x48 0x48 0x48 0x48
amimanye@Manye:~/0x0a. malloc, free$
```

### My solution
+ from the prototype, the function is supposed to return a pointer to an array
+ this array is goint to be locally created in the function `create_array`
+ returning a locally declared or initiallized array would have been impossible because the memory location will no longer be valid after the function completes (for more information on this, visit [notes](./notes.md)
+ in order to solve that, I am going to allocate memory from the heap which will later be freed when the variable is no longer in need.

### Program
```c
#include "main.h"
#include <stdlib.h>

/**
 * create_array - creates a local array
 * @size: size of locally created array
 * @c: character to be inserted into new array
 *
 * desc: using malloc, I am able to return a pointer to a locally created array
 * Return: returns the locally created array
 */

char *create_array(unsigned int size, char c)
{
        unsigned int i;
        char *array;

        if (size == 0)
                return (NULL);

        array = malloc(size * sizeof(char));
        if (array == NULL)
                return (NULL);
        for (i = 0; i < size; i++)
                array[i] = c;
        return (array);
}
```


## Task 1.
### Instructions
+ Write a function that returns a pointer to a newly allocated space in memory, which contains a copy of the string given as a parameter.
	+ Prototype: char *_strdup(char *str);
	+ The _strdup() function returns a pointer to a new string which is a duplicate of the string str. Memory for the new string is obtained with malloc, and can be freed with free.
	+ Returns NULL if str = NULL
	+ On success, the _strdup function returns a pointer to the duplicated string. It returns NULL if insufficient memory was available
+ FYI: The standard library provides a similar function: strdup. Run man strdup to learn more.

**TEST AGAINST THIS C PROGRAM**  
```c
#include "main.h"
#include <stdio.h>
#include <stdlib.h>

/**
 * main - check the code for ALX School students.
 *
 * Return: Always 0.
 */
int main(void)
{
    char *s;

    s = _strdup("ALX SE");
    if (s == NULL)
    {
        printf("failed to allocate memory\n");
        return (1);
    }
    printf("%s\n", s);
    free(s);
    return (0);
}
```

### Program behavior
```
amimanye@Manye:~/0x0a. malloc, free$ gcc -Wall -pedantic -Werror -Wextra -std=gnu89 1-main.c 1-strdup.c -o s
amimanye@Manye:~/0x0a. malloc, free$ ./s 
ALX SE
amimanye@Manye:~/0x0a. malloc, free$
```

### My solution

### Program
