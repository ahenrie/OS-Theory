# Address Space
TOP TO BOTTOM
**Address 0**
  1. Text Section --> The loaded program.
  2. Read Only Data Section --> This section is also known as the ".rodata" section. The data stored in this section cannot be modified at runtime; it remains constant throughout the execution of the program.
  3. Globals
  4. **End of Statically Allocated Memory** (Everything else below this space is dynamically allocated)
  5. Heap --> Address space that is allocated positively. As the program needs more space, it will add space towards N-1.
  6. Available Space
  7. Stack --> Address space that is allowcated negatively. As more space is needed, it will be added negatively or towards 0.
**Address N-1**

## Limited Direct Execution
DEF: The process has control of the CPU but is limited by the limits set in its mode.
EX: Certain memory is allocated to the process and that is it. Each process can only acess its own memory.
EX: Context switching, the kernel steps in and changes the state of the process so it can run another process on the CPU. This is conducted by a timer interupt.

### But How is LDE Possible?
**Special Hardware**
1. Timer interupt --> The CPU has a timer that will wait and call the kernel
2. Hardware interupt --> Keyboards, hardrives, network cards, pretty much anything that can stop the CPU from running a process.
3. Exception Interupts --> Often referred to as CPU interupts, occurs when a process tries to do soemthing outside its mode.
                           EX: Process tries to acess memory that does not exists or is not in its address space.
                           EX: On Intel CPUs, when a number is divided by 0, a divide by zero interupt occurs. The kernel then is called by the interupt and kills the process.
                           **Kernel Panic**: When the kernel throws an exception interupt

## Kernel Architecture
1. Monolithic -->  In a monolithic kernel, the entire operating system is implemented as a single, large and complex kernel. All the core services, such as process management, memory management, file system, and device drivers, are part of this single kernel space.
2. Micro --> The kernel is minimalistic and provides only essential functions, such as inter-process communication and basic scheduling. Additional services, such as device drivers and file systems, are implemented as separate user-space processes.

## System Calls
In the kernel there are two tables, 
1. The interrupt table or the interrupt vector is an array of pointer to kernel functions that are interrupt handlers that live elsewhere in the kernel. (SPECIFIC TO THE HARDWARE) (LOCATED AT A SPECIFIC MEMORY ADDRESS FOR TABLE)
2. The system call table is a vector of pointers to system calls. It is managed by the system call interupt handler. (HANDLE KERNEL SERVICES) (IT IS SOMEHWERE IN THE KERNEL)
3. System call loads a system call number into a register then calls the interrupt syscall.
4. Interrupt Disable: Special instruction that disables interrupts. 

## Scheduler
DEF: Is an algorithm that decides out of a list of processes which process should run next.

### First in First Out (OLDER)
1. Depends on the state of the current runnig process.
2. Depends on the state of the next process.
3. Simply walks through the list until it is over.
4. Nonpremptive: DOES NOT RELY ON A CPU CLOCK
5. When the process that is currently running causes a system call, the kernel can step in and use the scheduler. (A cooperative operation)

#### JOBS
1. Turnaround Time --> The finish time - submission time (when it was submitted to the job list)
2. Turnaround Time Avg --> The average of all the turnaround times.
3. Convoy Effect --> When large Jobs with long turnaround times is followed by a small and fast job. The short job can not get ahead and is stuck. The avg turnaround time is ruined.
4. Wait Time --> Turnaround Time - Runtime
5. Response Time --> Start Time - Submission Time. Submission Time is when the job was submitted to the scheduler.







?s
Interrupt handlers return what to where? How does the kernel kill the process?
What does a hybrid kernel look like?
When would the kernel disable interrupts?
