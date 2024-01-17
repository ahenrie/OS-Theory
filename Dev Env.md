# Setting Up Dev Enviroment

## Makefile
Makefile:
1. Will make files that are not already there
2. Execute commands when ran

Within a makefile there are multiple rules. 
A rule has a target, a dependecy, and a command
It will check if the target exists. If it exists it will execute the command.

``` bash
file.txt: signal
        echo "Adding text to file" >> file.tct
# this will see if file.txt is older than the file called signal. If signal is older, the commands will not be executed. 
```

Every program in unix has three files associated with it:
1. Stdout - Console
2. Stderr - Console
3. Stdin - Keyboard

We can reasign the output of stdout to a file: `echo "this is a string" > file.txt`
Another redirect is using the stdout and connect it to the stdin of another program with the ' | '. 
EX: `echo "this is a string" | wc`
The pipe pipes the input to the program. 
EX: `wc < file.txt` will count the words and lines in file.txt.
