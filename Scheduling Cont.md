# Scheduling

## Non-Preemptive Alogirithms, Can be run without a clock
1. First in First Out --> Suffers from the convoy effect
2. Shortest Job First --> Suffers from starvation
   - Makes assumptions on how long a job will run based in the past.
   - There is a queue that compares the runtimes of the job that are in the queue.
   - The one with the shortest runtime is picked first.
   - When the last runtimes are equal, the job first loaded into the queue is loaded.

## Preemptive Alogorithms
1. Shortest Runtime Next: the shortest job first but preempts when the process arrives.
EX: When a new job arrives, the current running job stops and runtime is deducted from its total runtime that it has accomplished.
  - New jobs are added first then leftover jobs are added

2. Round Robin: Prempts on timer interval or the quantum. (First come first serve)
   - Time Quantum: a value assigned to each job that outlines how long a job runs before interrupt.
   - After a job runs its quantum, it is placed at the bottom of the queue with its leftover time.
   - Does not allow starvation for bigger jobs
  
  Turnaround = JobEnd - Submission
