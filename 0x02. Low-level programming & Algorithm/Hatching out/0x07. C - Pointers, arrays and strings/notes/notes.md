# Pointer to pointer

```c
#include <stdio.h>
 
int main () {

   int  var;
   int  *ptr;
   int  **pptr;

   var = 3000;

   /* take the address of var */
   ptr = &var;

   /* take the address of ptr using address of operator & */
   pptr = &ptr;

   /* take the value using pptr */
   printf("Value of var = %d\n", var );
   printf("Value available at *ptr = %d\n", *ptr );
   printf("Value available at **pptr = %d\n", **pptr);

   return 0;
}
```

when compiled and run, results will be: 

```c
Value of var = 3000
Value available at *ptr = 3000
Value available at **pptr = 3000
```

When a pointer holds the address of another pointer then such type of pointer is known as pointer-to-pointer or double pointer

## What is a double pointer?
A double pointer is a variable that holds the address of a pointer.

**syntax**  
```c
int **ptr;
```

ptr is a pointer to another pointer.  
  
Let's take another example:  
```c
#include <stdio.h>
int main()
{
     int num=123;

     //A normal pointer pr2
     int *pr2;

     //This pointer pr2 is a double pointer
     int **pr1;

     /* Assigning the address of variable num to the
      * pointer pr2
      */
     pr2 = #

     /* Assigning the address of pointer pr2 to the
      * pointer-to-pointer pr1
      */
     pr1 = &pr2;

     /* Possible ways to find value of variable num*/
     printf("\n Value of num is: %d", num);
     printf("\n Value of num using pr2 is: %d", *pr2);
     printf("\n Value of num using pr1 is: %d", **pr1);

     /*Possible ways to find address of num*/
     printf("\n Address of num is: %p", &num);
     printf("\n Address of num using pr2 is: %p", pr2);
     printf("\n Address of num using pr1 is: %p", *pr1);

     /*Find value of pointer*/
     printf("\n Value of Pointer pr2 is: %p", pr2);
     printf("\n Value of Pointer pr2 using pr1 is: %p", *pr1);

     /*Ways to find address of pointer*/
     printf("\n Address of Pointer pr2 is:%p",&pr2);
     printf("\n Address of Pointer pr2 using pr1 is:%p",pr1);

     /*Double pointer value and address*/
     printf("\n Value of Pointer pr1 is:%p",pr1);
     printf("\n Address of Pointer pr1 is:%p",&pr1);

     return 0;
}
```

output

```c
Value of num is: 123
 Value of num using pr2 is: 123
 Value of num using pr1 is: 123
 Address of num is: 0x7ffe816802ec
 Address of num using pr2 is: 0x7ffe816802ec
 Address of num using pr1 is: 0x7ffe816802ec
 Value of Pointer pr2 is: 0x7ffe816802ec
 Value of Pointer pr2 using pr1 is: 0x7ffe816802ec
 Address of Pointer pr2 is:0x7ffe816802e0
 Address of Pointer pr2 using pr1 is:0x7ffe816802e0
 Value of Pointer pr1 is:0x7ffe816802e0
 Address of Pointer pr1 is:0x7ffe816802d8
```

## simple logic to understand better
+ num == *pr2 == **pr1
+ &num == pr2 == *pr1
+ &pr2 == pr1



## What is a double pointer?
A double pointer, also known as a pointer to a pointer, is a concept in C that allows you to store the address of a pointer variable. In other words, a double pointer holds the memory address of another pointer variable.  

Here's an example of how you can declare and use a double pointer:

```c
#include <stdio.h>

int main() {
    int value = 42;
    int *ptr = &value;       // Pointer to an integer variable
    int **doublePtr = &ptr;  // Double pointer to an integer pointer
    
    // Accessing the value using double pointer
    printf("Value: %d\n", **doublePtr);
    
    // Modifying the value using double pointer
    **doublePtr = 100;
    
    // Accessing the modified value
    printf("Modified Value: %d\n", **doublePtr);
    
    return 0;
}
```

In this example, we have an integer variable `value` with a value of `42`. We declare a pointer `ptr` and assign the memory address of `value` to it using the `&` operator. Then, we declare a double pointer `doublePtr` and assign the memory address of `ptr` to it using another `&` operator.

To access the value pointed to by the double pointer, we use the `**` operator. The expression `**doublePtr` dereferences the double pointer to access the value pointed to by the pointer `ptr`, which is the value of `value`. We can print this value using `printf()`.

Similarly, we can modify the value pointed to by the double pointer by assigning a new value to `**doublePtr`. In the example, we change the value to `100`.

When you run this program, it will output:

```
Value: 42
Modified Value: 100
```

## why doublel pointers?
The double pointer allows you to indirectly access and modify variables through multiple levels of indirection. It can be useful in scenarios where you need to dynamically allocate and deallocate memory or when you want to modify pointer variables within a function.
