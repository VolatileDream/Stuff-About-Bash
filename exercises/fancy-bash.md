
# Brace Expansion

 1) If you make a typo in a file name, how can you correct this using the `mv` command and a brace expansion?

 2) What brace expansion can be used to generate the following sequences, hint there are multiple answers.

    * "abe ae e"
    * "00a 00b 01a 01b 02a 02b 03a 03b 04a 04b"
    * "00ate 00are 02ate 02are 04ate 04are 06ate 06are 08ate 08are"
    * "017 02357 02457 067"

 3) What brace expansions can be used to generate the reverse order of the previous questions sequences?
    Given "abe ae e" generate "e ae abe".

 4) Find two different sequences to generate the sequence: "00 01 " ... " 98 99".

# Arrays

 1) Write a bash script that counts numbers it has seen from standard input. Numbers will be provided one per line.
    Once it has processed all of standard input, it should output the counts in the form: "<number>: <count>", with a single record per line.
    It should output all numbers between the smallest and largest number that have been seen. Numbers that have not been seen should have a count of zero.
    It should print out the numbers in numerical order (from smallest to largest).

    Bonus: Instead of numerical order (smallest to largest), it should print out numbers by the number of occurrences (most to least).

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

