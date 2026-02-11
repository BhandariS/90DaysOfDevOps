>> Basic Loop Syntax
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
