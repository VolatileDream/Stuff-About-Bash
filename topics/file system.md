
# The File System is Scary: your file names contain whitespace and newlines

(See this)[http://www.dwheeler.com/essays/fixing-unix-linux-filenames.html].

Not quoting variables or forgetting that filenames can contain whitespace, is one of the biggest mistakes that gets made by people who are new to shell scripting.

This generally occurs in the following form:

    bash-function *
    
    # write out all the files
    bash-function(){
        while [ $# -gt 0 ]; do
            cat $1
            shift
        done
    }

What happens if one of the files is named something malicous?

## Quote everything

    "When in doubt, quote it." --glgambet

If something comes from input somewhere it will probably contain spaces.

## It gets worse

Not only can filenames or options given to your programs contain whitespace, they can also contain other characters that will make your life sad. Like newlines, or leading dashes.

## Using Find

When fighting with file names, the best command to use is `find`. The `-print0` option is particularly useful when file names are going to be hard to work with.


