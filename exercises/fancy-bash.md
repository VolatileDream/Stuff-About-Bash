
# Brace Expansion

 1) If you make a typo in a file name, how can you correct this using the `mv` command and a brace expansion?

 2) 

# Arrays

 1) Write a bash script that counts numbers it has seen from standard input. Numbers will be provided one per line.
    Once it has processed all of standard input, it should output the counts in the form: "<number>: <count>", with a single record per line.
    It should output all numbers between the smallest and largest number that have been seen. Numbers that have not been seen should have a count of zero.
    It should print out the numbers in numerical order (from smallest to largest).

    Bonus: Instead of numerical order (smallest to largest), it should print out numbers by the number of occurances (most to least).

 2) Write a bash script that accepts the following commands on standard input:
    "+ key value" : store the mapping between the given key, and value
    "- key"       : remove the stored value for this key
    "? key"       : output the value for this key, if the value does not exist print "<NOT FOUND>"
    "load file"   : read from 'file', and execute commands in it as if they came from standard input. It will only contain "+ key value" commands.
    "save file"   : write the currently stored mappings to 'file', outputting only "+ key value" commands.
    "exit"        : exits the program
    Note that running the following command sequence should behave as if it never happened:
        "save file"
        "exit"
        <restart the program>
        "load file"

# shopt

