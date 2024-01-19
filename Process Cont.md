# Process Cont

## 3 Steps That Makes a Process a Process
1. Program from storage loaded to memory
2. Create Process Structure (how we maintain process state)
  - Registeres
  - Open Files
  - Process State
  - Memory layout
3. Context Switch

## Context Switch
DEF: When a kernel grants advanced kernel privileges to a program when a syscall is performed.

## Three States of a Process (non-preemptive)
1. Ready --> Registeres are restored and memory layout is set
2. Running --> When a context swith happens, the process has full control of the CPU.
   - The number of procesess running is the # of available cores.
   - A timer can take a running process back into the ready state.
   - - A timer is dependent on the core
3. Waiting --> The kernel moves the process into a waiting state while the kernel waits for the I/O to finish a read or write)
4. Back to ready after waiting state is completed

### Two Other States (Not needed to know)
1. Init (before ready state)
2. Terminate When process is running and the exit syscall is executed. It asks for cleanup and will live as a zombie until it is cleaned up.

## API 
1. FORK: duplicates a running process into a child process and parent prcesess.
2. EXEC:
     - execl --> Takes const char *pathname (path to a file), const char *arg, ... (more args)
       ``` C
       int main() {
          execl("usr/bin/ls", "ls", argv[1], NULL)
       }
       ```
     - execlp does the same but takes an array of arguments.


## Char* argv[]
  - It is a pointer to an array of pointers
  - sizeof(char*) will return the size an integer (%ld for reference)
