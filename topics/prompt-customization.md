
# Customizing the Prompt

(See here)[https://www.gnu.org/software/bash/manual/bash.html#Controlling-the-Prompt].

There are 4 variables that you may be concerned about for prompt customization:

 * PS1 -- value of the prompt displayed for commands
 * PS2 -- when your command would contain a new line, this is used for subsequent lines
 * PS3 -- used during the `select` command
 * PS4 -- printed during trace (set -x), multiple times to denote nesting

Only PS1 is usually customized.

The simple default for the prompt is `\u@\h > `, this shows the current user, and current hostname.

There exists a way to talk to the surrounding terminal, to change the name of the window or tab:
    `\[\e]0;<<<YOUR STUFF HERE>>>\a\]`


Do not forget: all expansions can be done in your prompt strings!
