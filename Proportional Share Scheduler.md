# Proportional Share Scheduler

## Lottery Scheduler
- For each process there are a certian number of shares granted to each process.
- The scheuler puts the shares into a range then randomly grabs a ticket from the range.
- EX: p1 is given a 1/3 amount of the range and so does p2. p3 is given the most shares and space in the range.
---------------------------------------------------
|------p1--------|------p2-------|------p3--------|
---------------------------------------------------
- The kernel has a default share value and it remains until it is used until changed.

## Linux: --> Nice value between -20 and 20. 
- Child processes can only set its niceness in the posetive direction, lowering its shares.
- Every process has:
  1. pid
  2. ppid
  3. state
  4. nice
  5. owner

## Completely Fair Scheduler in Linux
- It uses a tree data structure using the red black tree
- A job gets added to the queue
- **virtual run time**: how much time a process has spent on a CPU
- The scheduler picks the job with the lowest virual run time.
- Schedule latency: how long a process runs before the scheduler considers a switch
- Only the runnable processes are kept in the tree (those in the ready state).
