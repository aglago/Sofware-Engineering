# C libraries
+ C libraries are collections of prewritten code that programmers can use in their C programs. They contain functions and tools that help with common tasks like input/output, math calculations, working with text, managing memory, networking, graphics, and more.

+ By using C libraries, programmers can save time and effort by reusing existing code instead of writing everything from scratch. These libraries are usually provided as ready-to-use files that programmers include in their programs.

+ Learning C libraries is important because they offer many benefits.
+ They allow programmers to use tested and optimized code, which can make their programs run faster and more efficiently.
+ Libraries also provide standardized functions that work on different computer systems, making programs portable and easier to share.

+ Overall, C libraries are valuable tools that simplify programming tasks and make it easier to create robust and efficient C programs. 

# Types of C libraries
There are 2 primary types of C libraries: 
1. Static Libraries
2. Dynamic Libraries

## C Static Library
A C static library, also known as a "static library" or "archive library," is a type of library in the C programming language. It is a compiled collection of object files that contain precompiled functions and code that can be linked directly into a program during the compilation process.

### Key characteristics and aspects of C static libraries

1. Compilation: A static library is created by compiling multiple C source files into object files (.o files) using a compiler, such as GCC (GNU Compiler Collection), Clang, or MSVC (Microsoft Visual C++ Compiler). Each source file typically corresponds to a separate module or functionality.

2. Archiving: The object files are then bundled together into a single archive file using a tool like "ar" (ar stands for "archive"). The resulting file usually has the extension .a on Unix-like systems (e.g., libexample.a) or .lib on Windows systems (e.g., example.lib).

3. Static Linking: When a program is compiled and linked with a static library, the necessary object files from the library are extracted and merged directly into the final executable. This means that the code from the library becomes a part of the program itself. The resulting executable is self-contained and does not depend on the presence of the library at runtime.

4. Symbol Resolution: Static libraries contain compiled object code but do not include the full definitions of the functions they provide. Instead, they store references to the functions, which are resolved during the linking process when the program is built. The linker resolves these references by matching them with the actual function definitions in the library.

5. Portability: Static libraries are platform-specific, and the library compiled for one platform may not be directly compatible with another. However, the source code used to build the library can usually be compiled on different platforms to generate the appropriate static library for each platform.

6. Advantages: Static libraries offer several advantages. They provide a self-contained distribution of code, making it easier to distribute and deploy programs. They also ensure that the program will use the specific version of the library it was linked with, avoiding potential conflicts with different versions of the same library.

7. Disadvantages: One drawback of static libraries is that each program using the library will have its own copy of the library's code, potentially resulting in larger executable files. Additionally, if a bug is discovered or a new version of the library is released, each program needs to be recompiled and relinked with the updated library to benefit from the changes.

Overall, C static libraries offer a way to package and distribute precompiled code that can be directly linked into C programs. They provide code encapsulation, ease of distribution, and platform-specific functionality.


## C Dynamic Library
A C dynamic library, also known as a shared library or DLL (Dynamic Link Library), is a compiled collection of object files that contains precompiled code and functions. It is designed to be linked and loaded at runtime when a program is launched or when the library functions are called.

Key features of a C dynamic library include:

1. Dynamic Linking: Dynamic libraries are linked dynamically at runtime, allowing multiple programs to share the same library file. The library code is not embedded directly into the executable but is loaded into memory by the operating system when needed.

2. Separation from Executables: Dynamic libraries are separate files with their own file extension, such as `.dll` on Windows or `.so` (shared object) on Unix-like systems. They exist independently of the programs that use them.

3. Symbol Resolution: When a program that uses a dynamic library is launched, the operating system resolves the symbols (function addresses) referenced by the program to the corresponding symbols in the dynamic library.

4. Runtime Dependency: Dynamic libraries introduce a runtime dependency, as the program requires the presence of the dynamic library file(s) on the system in order to run successfully.

5. Code Sharing and Modularity: Dynamic libraries allow for better code sharing among multiple programs. If multiple programs use the same dynamic library, they can share the same instance of the library code in memory. This reduces the size of individual program executables and promotes code modularity.

Dynamic libraries provide flexibility in updating and maintaining code. Changes to the dynamic library can be made independently of the programs using it, enabling bug fixes or updates to be applied without recompiling all programs.
  
Overall, C dynamic libraries offer code sharing, modularity, and runtime flexibility, allowing programs to access additional functionality provided by the shared library during program execution.

# How to create C static library using `ar` (archive) and `ranlib`
To create a C static library using the `ar` (archive) and `ranlib` tools, you can follow these steps:

1. Compile the source code files: Compile the C source code files (.c files) that you want to include in the library into object files (.o files). For example, if you have two source files `file1.c` and `file2.c`, you can compile them using the following commands:
```shell
gcc -c file1.c
gcc -c file2.c
```
This will produce `file1.o` and `file2.o` object files.

2. Create the static library: Use the `ar` tool to create the static library archive file and add the object files to it. The basic syntax is:
```shell
ar rcs libname.a file1.o file2.o
```
Replace `libname.a` with the desired name of your library. The `r` option specifies that the files should be inserted or replaced, the `c` option creates the archive if it doesn't exist, and the `s` option updates the symbol table.

For example:
```shell
ar rcs mylib.a file1.o file2.o
```
This will create a static library file called `mylib.a` that includes `file1.o` and `file2.o`.

3. Index the library: The `ranlib` command is used to generate an index (or table of contents) for the library, which improves efficiency when accessing functions in the library. Run the following command:
```shell
ranlib libname.a
```
For example:
```shell
ranlib mylib.a
```
This will generate an index for the static library `mylib.a`.

After following these steps, you should have a C static library file (e.g., `mylib.a`) that you can link with your programs during the compilation process. Remember to specify the library using the `-l` option and provide the library name without the `lib` prefix and the `.a` extension. For example, to link with `mylib.a`, use `-lmylib` during compilation:
```shell
gcc myprogram.c -L/path/to/library -lmylib -o myprogram
```
  
**Note**: The steps provided here assume a Unix-like environment. On Windows systems, the commands and tools may have different names and extensions.

## Difference between static and dynamic libraries
The key difference between dynamic and static libraries lies in how they are linked to programs during the compilation and execution phases. Let's explore each type and their characteristics:

Static Libraries (Static Linking):
1. Compilation: Static libraries are created by compiling multiple source code files into object files, just like dynamic libraries.
2. Linking: During the linking phase, the object code from the static library is directly merged into the final executable at compile time. The resulting executable becomes self-contained, containing all the necessary code for the program to run.
3. Independence: Once linked, the program does not rely on the presence of the static library during runtime. All required code from the library is embedded into the executable, making it portable and standalone.
4. Advantages: Static linking provides simplicity and ease of distribution, as there is no need to distribute external library files separately. It also guarantees that the program will use a specific version of the library, avoiding compatibility issues with different library versions.
5. Disadvantages: Static libraries can result in larger executable files, as the library code is duplicated across multiple programs. If a bug is found or an update is released for the library, each program using the library must be recompiled and relinked to incorporate the changes.

Dynamic Libraries (Dynamic Linking):
1. Compilation: Dynamic libraries are compiled similarly to static libraries, creating object files from source code.
2. Linking: During the linking phase, the program is linked with a reference to the dynamic library instead of merging the library code into the executable. The actual library code is loaded and linked at runtime, when the program is launched or when the library functions are called.
3. External Dependency: Dynamic libraries exist as separate files and are not embedded in the executable. Therefore, the dynamic library file(s) must be present on the system at runtime for the program to run correctly.
4. Advantages: Dynamic linking reduces executable file size, as the library code is shared among multiple programs. It allows for better code organization and modularity, as multiple programs can share a single version of the library. Additionally, updates or bug fixes to the library can be applied without recompiling all programs using the library.
5. Disadvantages: Dynamic linking introduces a runtime dependency on the library files. If the required library is missing or incompatible, the program will fail to run. Dynamic libraries may also introduce potential version conflicts if different programs rely on different library versions.

In summary, static libraries are merged into the executable at compile time, making the program self-contained but potentially resulting in larger executables. Dynamic libraries are linked at runtime, allowing for code sharing, modularity, and flexibility, but introducing a dependency on external library files. The choice between static and dynamic linking depends on factors such as the size and distribution requirements of the program, flexibility for updates, and potential conflicts with different library versions.

## Command used to list symbols stored in a static library
1. To list the symbols stored in a static library, you can use the `nm` command in Unix-like systems. The `nm` command allows you to examine the symbol table of an object file or an archive (static library). Here's how you can use it:

```shell
nm libname.a
```

Replace `libname.a` with the name of your static library. This command will display a list of symbols along with their corresponding addresses and types. The symbol table includes functions, variables, and other symbols defined in the library.

The `nm` command provides different options to control the output format. Here are some commonly used options:

- `-g` or `--extern-only`: Shows only external symbols, excluding local symbols.
- `-p` or `--portability`: Displays symbol names without any decoration or special formatting.
- `-C` or `--demangle`: Demangles C++ symbol names, making them more readable.
- `-t` or `--radix=format`: Sets the output format for addresses. Common formats include `d` (decimal), `x` (hexadecimal), or `o` (octal).

For example, to display only external symbols without any decoration, you can use the following command:

```shell
nm -g -p libname.a
```

By using the `nm` command, you can explore and analyze the symbols stored in a static library, helping you understand its contents and usage.

2. In addition to the `nm` command, another commonly used command to list symbols in a static library is `ar`. The `ar` command is primarily used for managing archive files, including static libraries. Here's how you can utilize it to list symbols:

```shell
ar -t libname.a
```

Replace `libname.a` with the name of your static library. The `-t` option specifies the "table of contents" mode, which lists the symbols stored in the library.

Executing the above command will display a list of symbols contained within the static library. Each symbol represents a function, variable, or other entities defined in the library. The output will typically include the symbol names.

Note that the `ar` command primarily lists the symbols' names and not their addresses or types. If you require more detailed information about the symbols, such as their addresses or types, using the `nm` command is recommended.

## How libraries work with header files
In the compilation process, the inclusion of the header file (`math.h`) in the source code (`math.c`) provides the necessary function declarations and definitions to the compiler. However, including the header file alone does not automatically link the program with the corresponding library.

To ensure that the program knows to link with the math library, you need to specify the library explicitly during the compilation and linking process. The math library is typically named `libm.a` (on Unix-like systems) or `libm.lib` (on Windows systems). 

To compile and link the program `math.c` that uses functions from the math library, you would typically use the following command:

```shell
gcc math.c -lm -o math
```

In the above command:
- `gcc` is the command for the GCC compiler.
- `math.c` is the source file.
- `-lm` is the flag used to link with the math library (`libm.a` on Unix-like systems). The `-l` flag indicates the library to link with, and `m` refers to the math library. Note that the naming convention for libraries is usually `lib` followed by the library name without the extension.
- `-o math` specifies the output executable name (optional).

By specifying `-lm` during the compilation and linking process, the compiler and linker will search for the math library and resolve the references to the math functions used in the program, such as `sqrt()`. The actual implementation of these functions resides in the math library file.

To summarize, including the header file (`math.h`) provides the necessary function declarations and definitions to the compiler, but specifying the library during the compilation and linking process ensures that the program is linked with the corresponding library, allowing it to access the implementations of the functions provided by the library.

## Let's create a library together
### Instructions
Let us create a static library called "mylib" that provides a single function to caculate the factorial of a number.

### Solution
Certainly! Let's create a simple library together. We'll create a library called "mylib" that provides a function to calculate the factorial of a number. Here's how you can do it:

+ Step 1: Write the Source Code:
Create a source code file called `mylib.c` with the following content:

```c
#include "mylib.h"

unsigned long long factorial(int n) {
    if (n <= 1)
        return 1;
    else
        return n * factorial(n - 1);
}
```

+ Step 2: Create the Header File:
Create a header file called `mylib.h` with the following content:

```c
#ifndef MYLIB_H
#define MYLIB_H

unsigned long long factorial(int n);

#endif
```

+ Step 3: Compile into Object File:
Compile `mylib.c` into an object file using the following command:

```shell
gcc -c mylib.c -o mylib.o
```

This command compiles `mylib.c` into `mylib.o`, which contains the compiled implementation of the `factorial` function.

+ Step 4: Create the Library:
Create the library file `libmylib.a` by archiving the object file using the following command:

```shell
ar rcs libmylib.a mylib.o
```

This command creates `libmylib.a`, which is the library file that includes the compiled object file `mylib.o`.
  
Congratulations! You have created a simple library called "mylib" with a factorial function.
  
To use this library in another program, you will need to include the `mylib.h` header file in your program's source code and link the program with `libmylib.a` during the compilation and linking process.
  
Please note that this is a basic example for demonstration purposes. In practice, libraries may contain multiple source files and more complex functionality.
