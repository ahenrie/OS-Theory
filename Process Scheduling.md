# Scheduling

## Useful Bash Key
1. CTRL + D = End of file
2. CTRL + C = Terminate program
3. CTRL + Z = Sleeps process

## Bash Redirector
1. < = Redirects the file to stdin
2. > = Redirects the output or stdout to a file.
3. >> = Appends stdout to a file


### Chart to Build

First submission time is when the chart starts.

```C
#include<stdio.h>

#define MAX_JOBS (100)

void fifo(int count, int subTimes[], int runTimes[]) {
  int totalTA = 0, totalWait = 0, totalResp = 0;
  int clock = 0;
  for (int i; i < count; i++) {
    if(clock < subTimes[i] clock = subTimes[i];
    int finish = clock + runTimes[i];
    totalTA = finish - subTimes[i];
    totalWait += finish - subtTimes[i] - runTimes[i];
    totalResp += clock - subTimes[i];
    clock = finish;
  }

  printf("Avg. T.A: %.2f, Avg. Wait: %.2f, Avg. Resp: %.2f\n", (double)totalTA / count, (double)totalWait / count, (double)totalResp / count);
}

int main (int argc, char* argv[]) {
  int submissions[MAX_JOBS], runtimes[MAX_JOBS];
  int subTime, runTime;
int jobNum = 0;
FILE* fp = stdin;
if (argc > 1) {
  fp = fopen (argv[1], "r");
  if (fp == NULL) {
    perror ("Failure to open file");
    return -1;
    }
  }

  while (fscanf(fp, "%d%d", &subTime, &runTime) == 2) {
    submissions[jobNum] = subTime;
    runtimes[jobNum] = runTime;
    jobNum += 1;
  }

  fifo(jobNum, submissions, runtimes);
}
```
