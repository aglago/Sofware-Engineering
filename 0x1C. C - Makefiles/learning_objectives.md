# Makefiles

- What are make, Makefiles
- When, why and how to use Makefiles
- What are rules and how to set and use them
- What are explicit and implicit rules
- What are the most common / useful rules
- What are variables and how to set and use them

## What are make, Makefiles
### Make
"Make" is a command used in programming to build and manage software projects. It automates tasks like compiling code, linking files, and managing dependencies, making development more efficient. It reads a file called a "Makefile" to understand what actions to perform.

### Makefiles
A Makefile is a set of instructions used by the "make" command in programming. It lists rules for compiling source code into executable programs. Each rule specifies dependencies (like source files) and actions (like compilation commands). When you run "make," it checks the Makefile, executes necessary actions, and updates files as needed.

##  When, why and how to use Makefiles
### When to use Makefiles
You use Makefiles in programming projects to automate tasks like compiling code, linking files, and managing dependencies. They're handy for projects with multiple source files or complex build processes, saving time and ensuring consistency in development.

### Why to use Makefiles
Makefiles are used in programming for several reasons:

1. **Automation:* They automate repetitive tasks like compiling code, linking files, and managing dependencies, reducing manual effort and saving time.

2. **Consistency:** Makefiles ensure that the build process is consistent across different environments and developers, reducing errors and improving reliability.

3. **Efficiency:** By only rebuilding parts of a project that have changed, Makefiles can speed up the build process, especially in large projects.

4. **Dependency Management:** Makefiles track dependencies between files, so they know when a file needs to be rebuilt based on changes in other files.

Overall, Makefiles streamline the development process, improve reliability, and make it easier to manage complex projects.

### How to use makefiles

There are a few basic steps to using a makefile. First, you need to create a makefile in the root directory of your project. Then, you need to add the targets that you want to build. Each target should have a list of "prerequisites," which are files that need to be built before the target can be built. Finally, you need to add the commands that will be run when the target is built. Once the makefile is created, you can use the "make" command to build the targets.
