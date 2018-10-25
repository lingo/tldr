# getopt

> Parse commandline options.

- Handle short options '-h' and '-v':

`getopt -o 'hv' -- "$@"`

- Handle long options '--help' and '--verbose':

`getopt -o 'hv' --long 'help,verbose' -- "$@"`

- Specify an option that requires a value:

`getopt -o 'o:' --long 'output:' -- "$@"`

- Set the program name getopt uses to report errors (rather than 'getopt'):

`getopt -n "{{myprogram}}" -o 'hv' -- "$@"`

- Specify an option that *may* take a value:

`getopt -n "{{myprogram}}" -o 'hv::' --long 'help,verbose::' -- "$@"`

- To use getopts in your program, execute as follows, then loop through "$@", matching against '-{{option}|--{{long_option}}':

`args=$(getopt -o 'hv::' --long 'help,verbose::' -- "$@"); eval set -- "$args"`
