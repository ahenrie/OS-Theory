# Processes 

An OS will abstract in 3 ways:
1. CPU
2. Memory
3. Devices

## CPU - Processes
A CPU is abstracted via processes. 
**Multi Processing**: When multiple processes run at the same time. 
A processes that manages other processes is called a **kernel**.
Processes do not directly access hardware anymore. They now perform **system calls**

**Systemcall**: 
- Write
- Read
- Fork(): process that creates a new process, returns an int. It takes the current running process and clones it. 
  If process 1 calles fork(), the new process becomes the child process. Process 1 is now a parent. 
- Wait(&int): Waits for child to be in a zombie state then cleans the child and returns to the parent.

Nondeterministic Behavior: Behavior that can not be predicted between two processes.
```C
#include<stdio.h>
#include<unistd.h>

int main(int argc, char* argc[]) {
  printf("this is the first printf\n")
  printf("this is the second prinf\n"

  return 0;
}
```

## Systemcall APIs
getpid()
getppid()
