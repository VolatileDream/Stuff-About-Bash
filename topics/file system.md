
# The File System is Scary: your file names contain whitespace and newlines

(See this)[http://www.dwheeler.com/essays/fixing-unix-linux-filenames.html].

Not quoting variables or forgetting that filenames can contain whitespace, is one of the biggest mistakes that gets made by people who are new to shell scripting.

## Quote everything

    "When in doubt, quote it." --glgambet

If something comes from input somewhere it will probably contain spaces.

## It gets worse

Not only can filenames or options given to your programs contain whitespace, they can also contain other characters that will make your life sad. Like newlines, or leading dashes.


