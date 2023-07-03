# Linux Navigation
## What is "the Shell"?
Simply put, the shell is a program that takes commands from the keyboard and gives them to the operating system to perform. Examplese: Bash (Bourne Again SHell), ksh, tcsh, zsh.

## What is a "Terminal"?
a program that opens a window and lets you interact with the shell.

## First 3 Linux commands
+ `pwd` : prints the current working directory
+ `cd` : changes directory
+ `ls` : lists files and directories

### `pwd`
The directory we are standing in is called the working directory. To see the name of the working directory, we use the pwd command.
+ When we first log on to our Linux system, the working directory is set to our home directory. 
+ This is where we put our files. 
+ On most systems, the home directory will be called `/home/user_name`

### `ls` 
+ To list the files in the working directory, we use the ls.


### `cd`
+ To change the working directory, we use the `cd` command. 
+ To do this, we type `cd` followed by the pathname of the desired working directory.

*PRACTISE-01*
+ change the working directory on your terminal to `usr/bin`
+ list the files and directoriesin the `usr/bin` directory.

## shortcuts
+ `cd` followed by nothing takes you to the home directory
+ `cd ~user_name` will also take you to the home directory.
+ `cd -` changes working directory to the previous directory you visited.

## File names facts
+ file names beginning with a dot, example .git are hidden. In order to get hidden files, we use the `-a` option of the `ls` command.
+ file names are case sensitive.


# Looking Around
## Popular options of ls command
+ `-l`: lists files in long format. this displays the file name, date modified, size of file in bytes, group, owner, file permissions. (will be discussed later)

## `less`
used to view content of text tiles
+ *syntax*: `less text_file` where `text_file` is the name of the file you want to view it's content.
+ the less command displays content of files one page at a time.
+ **Page Up or b**: scrolls back one page
+ **Page Down or space**: scrolls forward one page
+ **G**: goes to the end of the file
+ **1G**: goes to the beginning of the text file.
+ **/characters**: searches forward in the text file all the occurences of `characters` in `/characters`
+ **n**: repeat previous search
+ **h**: displays complete list less commands and options
+ **q**: quits the viewing of the file.

## `file`
used to determine what type of data a file contains.  
  
Forexample: 
+ in my directory below, I have 2 files. 
+ `myfile1` contains plain text
+ `myfile2` contains a shell script

**BONUS COMMAND**  
`cat`: the `cat` command is used to display the content of a file.


![picture of terminal showing the files](./images/filetype1.png)

### How the file commands work
+ the file command looks at the contents of a file and checks it against a set of rules to figure out what type of file it is. 
+ these rules are stored in a file called the "magic" file. 
+ By comparing the patterns and characteristics of the file to the rules in the "magic" file, the file command can tell you if it's an image, a text file, a compressed archive, or something else. 
+ It's like a detective that examines the file and uses clues to determine its type.

### how to create custom file types
+ since the `file` command uses rules stored in a magic file, we can create a magic file and define a rule.
+ Forexample, we want all files starting with the word "Ami" to be identified as Ami file type.
+ 
