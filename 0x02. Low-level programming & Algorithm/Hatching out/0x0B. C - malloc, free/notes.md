# Memory allocation in C
Memory allocation in C refers to the process of reserving a portion of the computer's memory to store data during program execution. It involves setting aside a block of memory to hold variables, arrays, data structures, and other objects needed by a program.

## Table of content
+ [Types of Memory allocation](#types-of-memory-allocation)
+ [Dynamic Memory allocation](#dynamic-memory-allocation)
+ [Why allocate memory dynamically? Use cases](#why-allocate-memory-dynamically-use-cases)
+ [malloc](#malloc)
+ [free](#free)
+ [What is a memory leak?](#what-is-a-memory-leak)
+ [How to check for memory leaks](#how-to-check-for-memory-leaks)
+ [Get In touch With Me](#get-in-touch-with-me)


## Types of Memory allocation
1. **Static memory allocation**: Static memory allocation happens automatically during the compilation and linking process. Memory is allocated for static variables, global variables, and local variables with the `static` keyword. The size and lifetime of these variables are determined at compile time. The memory for static variables is allocated in the data segment or the stack, depending on the scope and storage duration. It is automatic because it happens during the compilation process.

2. **Dynamic memory allocation**: Dynamic memory allocation, on the other hand, is intentional and happens at runtime. It involves explicitly requesting and managing memory during program execution. Memory is allocated from the heap using functions like `malloc`, `calloc`, and `realloc`. Dynamic memory allocation allows for flexibility in handling variable sizes, varying memory requirements, and dynamic data structures.

## Dynamic Memory allocation
Dynamic memory allocation is a process in computer programming that allows you to request and use memory at runtime, as opposed to static memory allocation, where memory is allocated at compile time. Dynamic memory allocation provides flexibility in managing memory resources, allowing programs to adapt to varying memory requirements during program execution.

In dynamic memory allocation, memory is allocated from a region of memory called the heap. The heap is a large pool of memory that is available for dynamic allocation. The key functions used for dynamic memory allocation in C are `malloc`, `calloc`, and `realloc`. These functions allow you to allocate memory of a specified size and **return a pointer to the allocated memory block**.

Here's a brief overview of the main functions used for dynamic memory allocation:

1. `malloc`: It stands for "memory allocation." It allocates a block of memory of a specified size in bytes. It takes the size of the memory block as an argument and returns a void pointer (`void*`) to the beginning of the allocated memory block. You can cast the returned pointer to the appropriate data type.

2. `calloc`: It is similar to `malloc` but also initializes the allocated memory block with zeros. It takes the number of elements and the size of each element as arguments and returns a void pointer to the beginning of the allocated and initialized memory block.

3. `realloc`: It is used to resize an existing dynamically allocated memory block. It takes a pointer to the memory block to be resized and the desired new size as arguments. It returns a void pointer to the resized memory block. If the reallocation fails, it returns a null pointer.

After dynamically allocating memory, you can use the allocated memory for storing data or creating data structures as needed. It's important to note that you are responsible for managing the allocated memory, including proper deallocation using the `free` function when the allocated memory is no longer needed. Failing to free dynamically allocated memory can lead to memory leaks, where memory is not properly released, resulting in inefficient memory usage.


## Why allocate memory dynamically? Use cases
In a function, when a local variable is declared, it is statically allocated in memory. When the function completes, this memory that was allocated to the local variable is deallocated and is no longer valid. 

Here are some scenarios where returning a local variable from a function can cause issues:

1. Returning a pointer to a local variable: If you declare a local variable within a function and try to return a pointer to it, the memory allocated for that variable will be deallocated when the function returns. As a result, the returned pointer will become invalid, and accessing it will result in undefined behavior.

**FOR EXAMPLE** 
```c 
int *getLocalVariable() {
    int value = 42;
    return &value;  // Returning a pointer to a local variable
}

int main() {
    int *ptr = getLocalVariable();
    printf("%d\n", *ptr);  // Accessing the returned pointer
    return 0;
}
```

+ `getLocalVariable` function declares a local variable `value` and tries to return a pointer to it.  
+ however, when the function completes at `}` the memory that was allocated to `value` is then freed and no longer exists.
+ accessing this memory location that no longer exists will give `null`


To avoid these issues, you can use dynamic memory allocation (e.g., `malloc`) to allocate memory on the heap for the variable and return a pointer to it. In that case, the responsibility of deallocating the memory will fall on the caller of the function.  
  
Alternatively, you can pass a pointer to a pre-allocated memory block to the function, allowing it to modify the contents of the block rather than returning a local variable directly.

# Returning values
+ it is okay to return a local variable by value, that way a copy of the variable's value is made and returned from the function to wherever it is called. **For example**:  

```c
#include <stdio.h>

int add(int a, int b) {
    int sum = a + b;
    return sum;  // Returning the local variable 'sum' by value
}

int main() {
    int result = add(3, 5);
    printf("The result is: %d\n", result);
    return 0;
}
```
+ as you can see here, even though `sum` is a local variable, it is perfectly fine to return it's value. this is becuase we will be returning it by value and not by reference.
+ what this means is, we are not trying to return the value stored in `sum` from it's memory, but we are copying the value stored in `sum` and returning the copied value.
+ if we tried to return the value from it's memory, that is when we would have a problem, because after the function ends, this memory is no longer valid.
  
**WHAT IF WE WANTED TO RETURN THE VALUE OF** `sum` **FROM IT'S MEMORY?**  
that is when we will need to dynamically allocate memory from the heap so that even when the function completes, the memory will still be valid until it is deallocated!

# malloc
`malloc` and `free` are functions commonly used in the C programming language for dynamic memory allocation and deallocation. They are part of the standard C library `stdlib.h`.

- `malloc` stands for "memory allocation." It is used to dynamically allocate a block of memory of a specified size on the heap. The syntax for `malloc` is:
  ```c
  void *malloc(size_t size);
  ```
  Here, `size` represents the number of bytes to allocate. The function returns a void pointer (`void *`) to the allocated memory block if successful, or a null pointer (`NULL`) if the allocation fails.

  Example usage:
  ```c
  int *ptr = (int *)malloc(5 * sizeof(int));
  ```
  In the example above, `malloc` is used to allocate memory for an array of 5 integers (`5 * sizeof(int)`). The returned void pointer is then typecast to `int *` for convenience.
  
The statement "The function returns a void pointer (void *) to the allocated memory block if successful, or a null pointer (NULL) if the allocation fails" refers to the return value of the `malloc` function in C.

When you call `malloc` to allocate memory dynamically, it attempts to reserve a block of memory of the specified size on the heap. If the allocation is successful, `malloc` returns a pointer to the beginning of the allocated memory block. This pointer has a type of `void *` (void pointer) because `malloc` does not know the specific type of data you intend to store in the memory block. It's up to you to assign the returned pointer to an appropriate pointer type based on your data's type.

However, if the memory allocation fails, typically due to insufficient available memory, `malloc` returns a null pointer (`NULL`). A null pointer is a special pointer value that indicates that no memory could be allocated. It allows you to handle the allocation failure and take appropriate action in your program.

Here's an example to illustrate the usage of `malloc` and the return value:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr = malloc(5 * sizeof(int));
    if (ptr != NULL) {
        printf("Memory allocation successful.\n");
        // Use the allocated memory here
        // ...
        free(ptr); // Deallocate the memory when no longer needed
    } else {
        printf("Memory allocation failed.\n");
    }
    return 0;
}
```

In the above code, `malloc` is used to allocate memory for an array of 5 integers (`5 * sizeof(int)`). The return value of `malloc` is assigned to the pointer `ptr`. After the allocation, the code checks if `ptr` is not `NULL`, indicating a successful memory allocation. If `ptr` is not `NULL`, you can proceed to use the allocated memory. On the other hand, if `ptr` is `NULL`, the memory allocation failed, and you can handle the failure accordingly.

Remember to free the allocated memory using `free` when you are done using it to avoid memory leaks.

## `free`
- `free` is used to deallocate memory that was previously allocated dynamically using `malloc`, `calloc`, or `realloc`. The syntax for `free` is:
  ```c
  void free(void *ptr);
  ```
  Here, `ptr` is the pointer to the memory block that needs to be deallocated. After calling `free`, the memory block is released and can be reused for other purposes.

  Example usage:
  ```c
  free(ptr);
  ```
  In this example, `ptr` is the pointer to the dynamically allocated memory block, and calling `free(ptr)` deallocates the memory.

It's important to note that when using `malloc` and `free`, you should ensure that you free the allocated memory when you no longer need it to avoid **memory leaks**. Additionally, `free` should only be called on memory that was dynamically allocated using `malloc`, `calloc`, or `realloc`. Calling `free` on memory that was not allocated dynamically can result in undefined behavior.

## What is a memory leak?
A memory leak occurs when dynamically allocated memory is not properly deallocated or freed when it is no longer needed. As a result, the memory remains allocated and unavailable for reuse, leading to a loss of memory resources over time.

In situations where memory leaks occur, the program continues to consume memory without releasing it back to the system or heap. Over time, if memory leaks are not addressed, they can cause the program to consume excessive amounts of memory and potentially lead to performance degradation or crashes.

Memory leaks can happen for various reasons, such as:

1. Forgetting to free dynamically allocated memory: When memory is allocated using functions like `malloc`, `calloc`, or `realloc`, it is crucial to free that memory using the `free` function when it is no longer needed. Forgetting to free such memory results in a memory leak.

2. Losing track of pointers to allocated memory: If pointers to dynamically allocated memory are overwritten or lost without being freed, the allocated memory becomes inaccessible, leading to a memory leak.

3. Circular references or reference cycles: In systems involving complex data structures or objects with interdependencies, circular references can occur. If not managed properly, circular references can prevent the proper deallocation of memory, resulting in memory leaks.

Detecting memory leaks can be challenging, especially in large and complex programs. Memory profiling tools or debugging tools can assist in identifying memory leaks by tracking allocated memory and reporting any memory that is not properly released.

To prevent memory leaks, it's important to follow good memory management practices:

- Always pair memory allocation with proper deallocation using `free`.
- Keep track of dynamically allocated memory and ensure all allocated memory is freed when it is no longer needed.
- Avoid losing or overwriting pointers to allocated memory.
- Use automated testing and debugging tools to detect and address memory leaks.

By being diligent in managing memory and ensuring proper deallocation, you can prevent memory leaks and maintain efficient memory usage in your programs.


## How to check for memory leaks
To check for memory leaks in a C program, you can use memory profiling tools or debugging tools. These tools can help detect memory leaks by tracking memory allocations and deallocations, and identifying any memory that is not properly released.

One popular memory profiling tool for C programs is Valgrind. Valgrind provides a suite of tools, including Memcheck, which is designed for detecting memory errors, including memory leaks.

Here's a general process for checking memory leaks using Valgrind:

1. Install Valgrind: Install Valgrind on your system. The installation steps may vary depending on your operating system.

2. Compile the program with debug symbols: Compile your C program with debugging symbols enabled. This is typically done by including the `-g` flag during compilation. For example:
   ```
   gcc -g -o program program.c
   ```

3. Run the program with Valgrind: Use the Valgrind command to run your program and check for memory leaks. The basic command syntax is:
   ```
   valgrind --leak-check=full ./program
   ```
   The `--leak-check=full` option instructs Valgrind to perform detailed leak checking.

4. Analyze the Valgrind output: Valgrind will analyze your program's execution and provide detailed information about memory leaks, including the exact locations in the code where the leaked memory was allocated. It will also report other memory errors and warnings, helping you identify and fix issues.

Here's an example of a Valgrind command and its output:
```
$ valgrind --leak-check=full ./program
```
```
==12345== Memcheck, a memory error detector
==12345== ...
==12345== LEAK SUMMARY:
==12345==    definitely lost: X bytes in Y blocks
==12345==    indirectly lost: Z bytes in W blocks
==12345==      possibly lost: A bytes in B blocks
==12345==    still reachable: P bytes in Q blocks
==12345==         suppressed: S bytes in R blocks
==12345== ...
```
The output provides information about the number of bytes lost in memory leaks and the number of blocks involved. It also categorizes the memory leaks as "definitely lost," "indirectly lost," "possibly lost," and "still reachable." You can examine these details to identify the source of the leaks.

It's important to carefully analyze the Valgrind output, locate the source of the memory leaks, and fix them by ensuring proper memory deallocation using `free` when memory is no longer needed.

Note that Valgrind is just one example of a memory profiling tool. There are other tools available as well, depending on your specific requirements and platform.


# Get In Touch With Me
Feel free to get in touch if you have problem understanding any section of the notes.  
Twitter: [@ami_aglago](https://twitter.com/ami_aglago)  
WhatsApp: [+233 (0) 509581027](https://wa.me/233509581027?text=Kindle%20be%20brief%20and%20straightforward)  
LinkedIn: [Samuella Manye Aglago](https://www.linkedin.com/in/aglago) 
