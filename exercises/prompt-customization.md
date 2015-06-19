
# Customizing your Prompt


Easy prompt variable changing:


  in a file called var_func:
    #!/usr/bin/env bash
    
    var_func(){
        if [ $# -gt 0 ]; then
            export some_var="$*"
        else
            echo -n "[$some_var] "
        fi
    }
    if [ "$_" = "$0" ]; then
        var_func "$@"
        exit $?
    fi


  and in your prompt (after executing `source var_func`):
    '$(var_func)'

This will all you to set the variable in your prompt by running `var_func content`.
