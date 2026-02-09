//Learning Shell
What is Shell?
  >> A shell is a progrwam that takes your commands and tell linux what to do.
  >> Most common shell in DevOps --> Bash

//Some Basic Commands

*pwd - Prints your current directory, before running scripts or deployments one should confirm location.
*ls - List files and folder in the current directory,  It is used to check build artifacts/logs/deploymentpackages
*mkdir <name> - Creates a directory, Create folder for Logs/builds/releases/backups
*cd <directoryname> - Changes Directory, Switching into -  repofolder/release folder/script/folder
*touch <filename> - Creats an empty file, use .sh with file name for shell executables, It creats scripts/log files/marker files(flags)
*nano <filename.sh> - Opens a terminal-based text editor simple UI for quick actions
*vim <filename.sh> - Opens a terminal for text editor , good for programmming , fast 
*#!/bin/bash - Shebang - A shebang (#!) is the first line in a Unix-like script that tells the operating system which interpreter to use (e.g., bash, python, perl) to execute the code.
*echo "Txt" - Prints text to terminal
*chmod - chmod +x filename.sh - makes the file executable (Change mode) =x will make fle executable for everyone
*bash file.sh - explicitly runs script with bash
*./file.sh - Runs the script from the current directory, it is standar execution style everywhere
* diff between bash file.sh and ./file.sh
| Aspect                | `bash file.sh` | `./file.sh`    |
| --------------------- | -------------- | ------------   |
| Interpreter           | Forced (bash)  | From shebang   |
| Executable permission | ❌ Not needed  | ✅ Required   |
| Shebang required      | ❌ No          | ✅ Yes        |
| Used in production    | ⚠️ Rare        | ✅ Always     |
| Jenkins / cron        | ❌             | ✅            |

// when using variable inside strings it hhas to be double quotes
  eg --> echo "Hello $Name"

<!-- Variables -->
// With variables we can use same script in multiple environments
// we can define jenkins parameters in scripts

// eg 
#!/bin/bash

Name="Shubham"
Role="DevOps"

echo "Hello, I am $Name and I am a $Role"

<!-- User Input -->
read pauses the script, waits for input from the user, and stores that input in a variable.
What -p does -- Prints the prompt before waiting for input Avoids using a separate echo

#eg : 
#!/bin/bash

read -p "Enter your Name :" Name
read -p "Enter your Fav Tool :" Tool

echo " Hello $Name, your fav tool is $Tool"
