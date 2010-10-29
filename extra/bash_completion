# bash completion for @
# very basic at the moment

#have @ &&
_monkey-tail()
{
 local cmds cur prev
 cmds=$( @ list-commands | tr '\n' ' ' )

 COMPREPLY=()

 cur=${COMP_WORDS[COMP_CWORD]}
 prev=${COMP_WORDS[COMP_CWORD-1]}

 if [[ "$prev" == "@" ]]; then
  COMPREPLY=( $( compgen -W "$cmds" -- "$cur" ) )
 else
  case "${prev}" in
   help-on)
    COMPREPLY=( $( compgen -W "$cmds" -- "$cur" ) )
   ;;
  esac

  _filedir 
 fi
} &&
complete -F _monkey-tail -o filenames @
