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

Certainly! Here's a breakdown of the command `ar rcs libname.a file1.o file2.o` in simple language:

- `ar`: It's a command used to manage archive files.
  
- `rcs`: These letters are options for the `ar` command, and they mean the following:
    - `r`: Replace or add files to the archive. If a file with the same name is already in the archive, it will be replaced.
    - `c`: Create a new archive if it doesn't already exist.
    - `s`: Write an index or symbol table for the archive.

- `libname.a`: It's the name you choose for your library file. It should start with "lib" and have the `.a` extension. Replace "libname" with the name you want.

- `file1.o`, `file2.o`: These are the object files you want to include in the library. They contain compiled code that provides specific functionality.

So, when you run this command, it creates or updates a library file called `libname.a` and adds the object files `file1.o` and `file2.o` to it. The library file serves as a container that holds the compiled code and functions from the object files. This library can then be used by other programs during the compilation process to access the functionality provided by the included object files.

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

# How to create dynamic libraries
To create a dynamic library in C/C++, you'll typically follow these steps:

1. **Write Your Code:** First, you need to write the source code for your library. Create one or more C or C++ source files that contain the functions and data you want to include in the library.

2. **Compile the Source Code:** Compile the source code into object files. For creating a dynamic library, you should use the `-fPIC` (Position Independent Code) flag to ensure that the code can be loaded into memory at any address. For example:

   ```bash
   gcc -c -fPIC mylib.c -o mylib.o
   ```

   Replace `mylib.c` with your source file.

3. **Create the Dynamic Library:** Now, you can create the dynamic library using the compiled object file. You typically use the `-shared` flag to specify that you're creating a shared library (dynamic library). For example:

   ```bash
   gcc -shared -o libmylib.so mylib.o
   ```

   This command will generate the dynamic library named `libmylib.so`.

4. **Set Library Path (Optional):** If you want to use your dynamic library without specifying the full path every time, you can set your library path using the `LD_LIBRARY_PATH` environment variable. For example:

   ```bash
   export LD_LIBRARY_PATH=/path/to/library:$LD_LIBRARY_PATH
   ```

   Replace `/path/to/library` with the actual path to your library.

5. **Use the Library:** You can use your dynamic library in your C/C++ programs. When compiling your program, you need to specify the library using the `-l` flag, followed by the library name without the "lib" prefix and the ".so" extension. For example:

   ```bash
   gcc my_program.c -o my_program -lmylib
   ```

   This will link your program with the `libmylib.so` dynamic library.

6. **Run Your Program:** You can now run your program, and it will load the dynamic library at runtime.

That's how you create and use a dynamic library in C/C++. The process might vary slightly depending on your development environment, but these are the general steps.

## Similarities between static and dynamic libraries

1. **Code Reusability:** Both static and dynamic libraries promote code reusability. You can create functions, classes, or modules that can be used in multiple programs.

2. **Pre-compiled Code:** Both types of libraries contain pre-compiled code, allowing developers to utilize existing functionality without recompiling the entire source code.

## Difference between static and dynamic libraries

**1. Linking Stage:**
   - **Static Libraries:** Static libraries are linked at compile time. When you compile your program, the linker includes the entire library's code in the executable, making the executable self-contained.
   - **Dynamic Libraries:** Dynamic libraries are linked at compile time, but they are not included in the executable. Instead, a reference to the library is added. The actual loading of the library occurs at runtime.

**2. Executable Size:**
   - **Static Libraries:** Executables linked with static libraries tend to be larger because they include all the library's code.
   - **Dynamic Libraries:** Executables linked with dynamic libraries are smaller because they only contain references to the libraries.

**3. Independence:**
   - **Static Libraries:** Executables linked with static libraries are fully independent. They do not rely on external library files.
   - **Dynamic Libraries:** Executables linked with dynamic libraries depend on the presence of the library files on the system where they are run.

**4. Version Control:**
   - **Static Libraries:** No versioning concerns. Once an executable is built with a static library, it doesn't change unless you recompile.
   - **Dynamic Libraries:** Versioning is crucial because dynamic libraries can be updated independently of the executables that depend on them. Different versions of the library can coexist.

**5. Updates:**
   - **Static Libraries:** Any change to the library requires recompiling all executables that use it.
   - **Dynamic Libraries:** You can update a dynamic library without recompiling the executables. This is especially useful for patching security vulnerabilities or fixing bugs.

**6. Memory Usage:**
   - **Static Libraries:** Executables linked with static libraries consume more memory because they load all library code into memory.
   - **Dynamic Libraries:** The memory footprint of dynamic libraries is smaller because they are loaded on demand.

**7. Loading Time:**
   - **Static Libraries:** Executables start faster since all the code is already included.
   - **Dynamic Libraries:** Executables might have a slightly longer startup time because they need to load dynamic libraries.

In summary, while both static and dynamic libraries provide code reusability, they differ in terms of linking stage, executable size, independence, version control, updates, memory usage, and loading time. The choice between them depends on specific project requirements, such as the need for standalone executables or the ability to update libraries independently.

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
