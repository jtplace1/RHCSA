Create simple shell scripts

# Create simple shell scripts

env6
- 
**BASH scripting** 

| **Executing scripts** |                                                              |
| --------------------- | ------------------------------------------------------------ |
| Source myscript.sh    | Runs the script in the current shell (environment variable will be available in the shell) |
| ./myscripts.sh        | Runs the script in a different shell, after the script is done the environment variables aren’t available anymore |

| **Process script inputs ($1, $2, etc.)** |                      |
| ------------------------ | -------------------- |
| $0                    | Name of the script itself when executed in a script          |
| $1, $2 etc.           | Arguments that you can pass into a script                    |
| $?                    | Display the error level                                      |
| $#                    | the number of parameters with which the script has been called |
| $$                    | The PID number of the current running shell                  |

| **Processing output of shell commands within a script** |                      |
| ------------------------ | -------------------- |
| -f                       | If a file exist      |
| -d                       | If a directory exist |
|                          |                      |
|                          |                      |

| **Processing shell command exit codes** |                      |
| ------------------------ | -------------------- |
| -f                       | If a file exist      |
| -d                       | If a directory exist |
|                          |                      |
|                          |                      |

| **Conditionally execute code (use of: if, test, [], etc.)** |                      |
| ------------------------ | -------------------- |
| -f                       | If a file exist      |
| -d                       | If a directory exist |
|                          |                      |
|                          |                      |

| **Use Looping constructs (for, etc.) to process file, command line input** |                      |
| ------------------------ | -------------------- |
| -f                       | If a file exist      |
| -d                       | If a directory exist |
|                          |                      |
|                          |                      |

