# Virtual Memory

## Von Neumann Model
1. The CPU uses the Bus to communicate to the rest of the system
2. The Buss is connected to the memory. 
  - When the CPU wants something out of memory, The cpu writes to the memory address register (48 bits in size)
  - It is then copied to the memory data register (64 bits size) and read.
  - The CPU will stall when waiting for data to come from memory.
  - Cache is a piece of memory that is close to the CPU
  - L1 Cache is the closest and the smallest in size typically. Each core has a L1 cache. (measured in KB and operates in the nanoseconds).
  - L2 Cache is not directly next to the registers. It is shared between cores. Usually measured in the MB. 
  - L3 Cache is connected between CPUs and measured in the MB. 

## Back in Time
**Multiprogramming**: Multiple jobs are loaded in memory. Jobs could see the entire address range in memory. 

**Address Translation In the Memory Managment Unit (MMU)**
- To fix this, each job is given a base value idicating the beginning of that job. 
- The CPU then loads the base value plus the address values the program is trying to access.
- This occurs everytime memory is accessed.

1. Virtual/Logical Addresses: Relative to what the base register is set to.
2. Physical Address: Actual address in memory.
3. Base register: sets where the process begins in memory.
4. Limit register: specifies how much memory space is allocated to the process.
5. Only the kernel can change base and limit registers.
6. If process tries to load memory from outside the limit, the CPU will stop and kill the process.
7. Memory segment: the bounds in memory that a process can access.
8. External Fragmentation: Outside of the processes, there is memory that can not be used since it is fragmented to sizes that are too small to be used by a process.

## Process Arch and Base Limit Scheme
1. Text
2. Read Only Data
3. Global Data
4. Heap grows up
5. Stack grows down

The text and read only data sections of the process are mapped to memory in a Base and Limit Scheme in the segment registers.
