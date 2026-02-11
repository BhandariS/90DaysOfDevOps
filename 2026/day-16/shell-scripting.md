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
>> With variables we can use same script in multiple environments
>> we can define jenkins parameters in scripts

// eg 
#!/bin/bash

Name="Shubham"
Role="DevOps"

echo "Hello, I am $Name and I am a $Role"

<!-- User Input -->
>> read pauses the script, waits for input from the user, and stores that input in a variable.
>> What -p does -- Prints the prompt before waiting for input Avoids using a separate echo

#eg : 
#!/bin/bash

read -p "Enter your Name :" Name
read -p "Enter your Fav Tool :" Tool

echo " Hello $Name, your fav tool is $Tool"

<!-- If--else Condition -->
>> There must be a space after [ and before  ] as [ is a command and command requires space between arguments
#eg:
#!/bin/bash

read -p "Enter no:" No

if [ $No -gt 0 ]; then
        echo "No is Positive"
elif [ $No -lt 0 ]; then
        echo "No is Negative"
else
        echo "No is Zero"
fi


<!-- Check if file exist -->
>> -f -- check regular files , returns true if file exist
>> -d -- check for directory
>> -l -- logical Not , check if directory exists
>> -s -- checks if file is not empty, ensuring deployment manifest has content
>> -z -- checks if a string is EMPTY (zero length). helpful when passing an argument
>> File test operators (core ones)
Operator	Meaning	            DevOps use
-f	      File exists	        Config/package check
-d	      Directory exists	  Workspace validation
-s	      File not empty	    Ensure content exists
-r	      Readable	          Permission check
-w	      Writable	          Log / artifact check
-x	      Executable	        Script/tool check

#eg: 
#!/bin/bash

read -p "Enter File Name:" filename

if [ -f "$filename" ]; then
        echo "File Exist : $filename"
else
        echo "$filename File does not exist"
fi

<!--server_check -->
>> systemctl is-active --quiet "$SERVICE" -- Here is-active checks if service is running and quiet only shows exit code not the output.
eg :  0 → service is running
     1 → service not running
>> If you are using stings for comparison in if command the it has to be this way eg : if [ "$choice" = "y" ]; then
eg :
>> Create server_check.sh that:
Stores a service name in a variable (e.g., nginx, sshd)
Asks the user: "Do you want to check the status? (y/n)"
If y — runs systemctl status <service> and prints whether it's active or not
If n — prints "Skipped."

#!/bin/bash

Service="nginx"

read -p "Do you want to check status of $Service? (y/n): " choice

if [ "$choice" = "y" ]; then
        systemctl is-active --quiet "$Service"
        
  >> is-active → checks if service is running
  >> --quiet → no output, only exit code
  >> Exit code: 0 → service is running
                1 → service not running
         
        if [ $? -eq 0 ]; then
        
        >> $? = exit status of last command & -eq 0 = success
        
                echo "$Service is running"
        else
                echo "$Service is not running"
        fi

elif [ "$choice" ="n" ]; then
        echo "Skipped."

else
        echo "Invalid input. Please enter y 0r n."
fi
