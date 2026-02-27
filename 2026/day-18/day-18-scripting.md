>> What is function?
-- A function is just a reusable block of code, it helps in grouping the code and call it instead of repeating the code.

>> Simple eg
#!/bin/bash

//defining function
function greet() {
    echo "Hello DevOps"
}

//calling function
greet

** Simple Regex
[[ "$age" =~ ^[0-9]+$ ]] - 

| Part    | Meaning                                     |
| ------- | ------------------------------------------- |
| `[[ ]]` | Advanced test condition (better than `[ ]`) |
| `=~`    | Regex match operator                        |
| `^`     | Start of string                             |
| `[0-9]` | Any digit                                   |
| `+`     | One or more digits                          |
| `$`     | End of string                               |

>> Means == Match string that starts and ends with digits only.


##Arrays

*Accessing Elements - echo "${fruits[0]}"
*Print All Elements - echo "${fruits[@]}"
*Declare Associative Array - declare -A userinfo
-A = Associate array

*Access Values - echo "${userinfo[name]}"
*Print all keys - echo "${!userinfo[@]}"
*Print all values - echo "${userinfo[@]}"

*Loop Through Key-Value
eg : for key in "${!userinfo[@]}"
do
    echo "$key → ${userinfo[$key]}"
done

# ${!array[@]} → gives keys
# ${array[$key]} → gives value
