
# Fancy Bash

## Brace Expansion

[See here](https://www.gnu.org/software/bash/manual/bash.html#Brace-Expansion).

    > echo a{b,c{d,e}f,g}h
    abh acdfh acefh agh

Similar to Globbing, Brace Expansion allows for shorter pieces of text to be expanded in fairly predictable ways. They can be constructed in one of two ways:

 * A range and optional increment: {start..end[..increment]}
 * A list: {thing1,thing2,...,thingN}

Brace Expansions can be nested, and treat every character within them as text (except for quotes). This is important, because Brace Expansion happens _before_ any other type of expansion (like Variables and Globbing). And Brace Expansion is _not_ Globbing, no file needs to exist that matches the Brace Expansion.

### Ranges of Numbers


* `{start..end}` when `start` and `end` are both numbers, this expands to the range of numbers from `start` to `end` incrementing or decrementing by 1.
* `{start..end..incr}` when `start`, `end` and `incr` are all numbers, this expands to the range of numbers from `start` to `end` incrementing or decrementing by `incr`.

* `{start..end}` == `{start..end..1}`

* When `start` or `end` has a leading zero, the range of numbers will be padded with zeros. It pads to the same length as the `start` or `end` padding. 

* `{01..10}` -> 01 02 03 04 05 06 07 08 09 10
* `{1..010}` -> 001 002 003 004 005 006 007 008 009 010

### Ranges of Characters

* `{start..end}` when `start` and `end` are single letters, they expand to ASCII character range between the two letters.

### Lists

Lists behave as you would expect them to, expanding to each of the items within.

* `{a,b}` == "a b"
* `{a,b,c}` == "a b c"

### Preamble and Postscript

All Brace Expansions have an optional preamble and optional postscript. This lets you attach something to the beginning of the expansion, and something at the end.

* `a{c,t,r}e` == "ace ate are"

The preamble and postscript can be another brace expansion.

* `{1,2}{3,4}` == "13 23 14 24"

### Other Things About Brace Expansion

There are a few important things to remember about Brace Expansion:

 * An incorrect expansion gets left alone
 * If it starts with ${ it gets left alone (because it looks like a variable)
 * They can't be quoted

## Arrays

There are two types of Arrays in Bash: indexed, and associative. Indexed arrays (with numbers) are the default unless you explicitly declare an associative array using `declare -A VARIABLE_NAME`.

### Indexed Arrays


    declaration:
        array=(value1 value2 ... valueN) ; valueX is of the form "[index]=value" or "value"

Indexed arrays are sparse, meaning that they do not contain elements that have not been set (or that have been removed).

### Associative Arrays

    declaration:
        declare -A array=(value1 value2 ... valueN) ; valueX is of the form "[index]=value"

### In General

Array elements can be removed with: `unset array[index]`. Or the entire array can be removed: `unset array`.

You can see all the keys contained in an array with: `${!array[@]}`. And the array length: `${#array[@]}`

Note that normal variables can be implicitly converted to indexed arrays. Their prior value is converted to the item for the 0 index.

## shopt-ing


