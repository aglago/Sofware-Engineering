# Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

## General
- What is a PID

A PID, or process ID, is a unique identifier that's assigned to each process on a Unix-like operating system, like Ubuntu. The PID is used by the operating system to keep track of all of the running processes, and it can be used to control and manage those processes. For example, you can use the "ps" command to list all of the running processes and their PIDs. You can also use the "kill" command to terminate a process based on its PID.


- What is a process

In Linux, a process is an instance of a program that's running on the system. When you run a program, the operating system creates a process for it, and the process will continue to run until it's terminated. Processes can be in different states, like "running", "sleeping", or "stopped". A process can also have multiple threads, which are separate execution paths within the same process. A process ID (PID) is used to uniquely identify each process on the system.


- How to find a process’ PID

There are a few different ways to find the PID of a process in Linux. The "ps" command is one of the most common ways to do this. With the "ps" command, you can list all of the running processes and their PIDs. For example, you could use the command "ps -e" to list all of the running processes. You can also use the "pidof" command to find the PID of a specific process by its name.


- How to kill a process

To kill a process in Linux, you can use the "kill" command. This command takes the PID of the process as an argument, and it sends a signal to the process telling it to terminate. The "kill" command can send different signals depending on the situation. For example, the "SIGTERM" signal is a polite way of asking the process to terminate, while the "SIGKILL" signal is more forceful.


- What is a signal

In Linux, a signal is a notification that's sent to a process to inform it of an event. There are many different types of signals, and each one has a specific purpose. For example, the "SIGTERM" signal indicates that the process should terminate, while the "SIGPIPE" signal indicates that a pipe has been broken. Signals are sent using the "kill" command, and they're handled by the process using signal handlers.


- What are the 2 signals that cannot be ignored

There are two signals that can't be ignored in Linux: "SIGKILL" and "SIGSTOP". The "SIGKILL" signal is a forceful way of telling the process to terminate immediately, and it can't be blocked or ignored by the process. The "SIGSTOP" signal tells the process to stop all activity, and it can't be ignored either. These signals are important because they can be used to terminate processes that are stuck or not responding.

