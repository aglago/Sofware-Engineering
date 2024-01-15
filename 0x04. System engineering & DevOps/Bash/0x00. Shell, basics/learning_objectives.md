# Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

### General

- What does RTFM mean?

RTFM is an acronym for "read the fine manual". It's a tongue-in-cheek way of saying that you should consult the documentation for more information. It's often used when someone asks a question that could be easily answered by reading the documentation. For example, if someone asked how to use the "slice()" method without providing the correct arguments, you might reply with "RTFM!" 😄

- What is a Shebang

A "shebang" is a special kind of comment at the beginning of a script file that tells the operating system how to execute the script. It's usually written as "#!" followed by the path to the interpreter that should be used to run the script. For example, a Python script might start with "#!/usr/bin/python3" to tell the operating system to use the "python3" interpreter to run the script. Without a "shebang", the operating system might not know how to execute the script.

### What is Shell
- What do the commands or built-ins `cd`, `pwd`, `ls` do
- How to navigate the filesystem
- What are the . and .. directories
- What is the working directory, how to print it and how to change it
- What is the root directory
- What is the home directory, and how to go there
- What is the difference between the root directory and the home directory of the user root
- What are the characteristics of hidden files and how to list them
- What does the command `cd -` do

### Looking Around
- What do the commands `ls`, `less`, `file` do
- How do you use options and arguments with commands
- Understand the ls long format and how to display it
- [A Guided Tour]()
- What does the `ln` command do

The "ln" command, also known as the "link" or "symbolic link" command, creates a shortcut or symbolic link to another file. When you run the "ln" command, it creates a new file that points to the original file. This allows you to access the original file by using the shortcut file. It's often used to create shortcuts to files in different locations on the same computer

- What do you find in the most common/important directories
- What is a symbolic link

A symbolic link, or "symlink", is a type of file that contains a reference to another file or directory. It's different from a regular file because it doesn't contain the contents of the original file - it just contains a pointer to the original file. This makes it useful for creating shortcuts to files or for sharing files between different locations on a computer. Symbolic links are often denoted with a special symbol, such as "→" or "⇒", to distinguish them from regular files.

- What is a hard link

A hard link, or "hardlink", is a type of file that is identical to the original file. Unlike a symbolic link, a hard link doesn't just contain a pointer to the original file - it's an exact copy of the original file. Hard links are useful for creating multiple names for the same file without creating multiple copies of the file. However, they can cause problems if you try to delete the original file but not the hard link. Are you working with hard links?

- What is the difference between a hard link and a symbolic link

The main difference between a hard link and a symbolic link is how they refer to the original file. A hard link contains the exact contents of the original file, while a symbolic link contains a reference to the original file. This means that if you change the original file, the changes will be reflected in the hard link, but not in the symbolic link. Also, if you delete the original file, the hard link will be broken, but the symbolic link will still exist. Is that clear?

### Manipulating Files
- What do the commands `cp`, `mv`, `rm`, `mkdir` do
- What are wildcards and how do they work
- How to use wildcards

### Working with Commands
- What do `type`, `which`, `help`, `man` commands do
- What are the different kinds of commands
- What is an alias
- When do you use the command help instead of man

### Reading Man Pages
- How to read a man page
- What are man page sections
- What are the section numbers for User commands, System calls and Library functions

### Keyboard Shortcuts for Bash
- Common shortcuts for Bash

### LTS
- What does `LTS` mean?
