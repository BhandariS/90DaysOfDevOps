i>> Basic Loop Syntax
>>
for variable in list
do
    commands
done

| Part       | Purpose                                     |
| ---------- | ------------------------------------------- |
| `for`      | Starts loop                                 |
| `variable` | Temporary variable (changes each iteration) |
| `in`       | Defines list                                |
| `do`       | Start block                                 |
| `done`     | End block                                   |

>> Loop through numbers <<
eg :
>> for num in {1..5}
do
    echo $num
done

her {1..5} means Generate numbers from 1 to 5.

or other example for this

#!/bin/bash

for (( i=1; i<=10; i++ ))
do
    echo "Iteration: $i"
done

>> here (( )) - this is arithmetic expression
>> i=1 - initialization start with 1
>> i<=10 - value should be less than equal to 10 or count till 10
>> i++ - increment value by 1 untill reached 10

TASK 2 <!-- countdown.sh -->

eg : 
#!/bin/bash

read -p "Enter a number: " num

//Here putting a check that if num entered is 0 print nothing and if num is negative print error then exit

if [ $num -eq 0 ]; then
        echo "Nothing to count"
        exit 0
elif [ $num -lt 0 ]; then
        echo "Number should not be negative"
        exit 1
fi
while [ $num -gt 0 ]
do
        echo "Countdown: $num"
        //arithematic expression $((...)) you can do add/multiple/subst/divide/modulus inside this
        num=$((num-1))
done
echo "Done!"

>> <!-- Command line Arguments -->

>> ./script.sh value1 value2
       $0        $1     $2

>> | Variable | Meaning                                     |
   | -------- | ------------------------------------------- |
   | `$0`     | Script name                                 |
   | `$1`     | First argument                              |
   | `$2`     | Second argument                             |
   | `$3`     | Third argument                              |
   | `$#`     | Total number of arguments                   |
   | `$@`     | All arguments                               |
   | `$*`     | All arguments (slightly different behavior) |
>> eg
#!/bin/bash

if [ $# -lt 2 ]; then
        echo "Usage: ./greet1.sh <first_name> <last_name>"
        exit 1
fi

echo "Hello, $1 $2"


    
