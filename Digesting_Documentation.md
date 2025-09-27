# Digesting Documentation

## Learning From Documentation - Challenge 1
### This challenge requires us to invoke a command followed by an argument correctly to get the flag.

**Flag:** `pwn.college{0j9uv0s6GH-r7tKgHoBn2OT7nTd.QX0ITO0wyMwkjNzEzW}` 

The process of obtaining the flag involved switching to SSH on the pwn.college challenge first, then using the given command along with --giveflag argument.

```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{0j9uv0s6GH-r7tKgHoBn2OT7nTd.QX0ITO0wyMwkjNzEzW}
```

## What I Learned

This challenge highlighted the importance of using the precise syntax required for a command to function properly.

## References

None

## Learning Complex uses - Challenge 2
### This challenge requires us to use the --printfile command with the /flag argument.

**Flag:** `pwn.college{0tC8sGrKPcy_3ZcB3XNxoPdOCCH.QX1ITO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the /challenge/challenge --printfile /flag command.

```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile
You must pass a file for --printfile to read!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/flag
Correct argument! Here is the /challenge/flag file:
cat: /challenge/flag: No such file or directory
hacker@man~learning-complex-usage:~$ cat: /challenge/flag
bash: cat:: command not found
hacker@man~learning-complex-usage:~$ cat /challenge/flag
cat: /challenge/flag: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile flag
Correct argument! Here is the flag file:
cat: flag: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile flag.txt
Correct argument! Here is the flag.txt file:
cat: flag.txt: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{0tC8sGrKPcy_3ZcB3XNxoPdOCCH.QX1ITO0wyMwkjNzEzW}
```

## What I Learned

I discovered that certain commands demand careful thought and sometimes more complex approaches. Missing the '/' before 'flag' led to several mistakes on my part.

## References

None

## Reading Manuals - Challenge 3
### This challenge requires us to go through a manual of a commands which will give us the flag.

**Flag:** `pwn.college{ML4z_kvHAK3qZEJ-5u_ETzG4ByP.QX0EDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using man command for challenge and finding the secret command to use to obtain the flag.

```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ challenge 435
bash: challenge: command not found
hacker@man~reading-manuals:~$ challenge --zkvquz 435
bash: challenge: command not found
hacker@man~reading-manuals:~$ /challenge/challenge --zkvquz 435
Correct usage! Your flag: pwn.college{ML4z_kvHAK3qZEJ-5u_ETzG4ByP.QX0EDO0wyMwkjNzEzW}
```

## What I Learned

I realized that consulting the manual for a command can be extremely helpful, as it often provides the exact guidance needed.

## References

None

## Searching Manuals - Challenge 4
### This challenge requires us to go through a manual of a commands which will give us the flag.

**Flag:** `pwn.college{whud7rau3HnXqvGgZ9ntHHIJ2aY.QX1EDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using man command for challenge and finding USING ? or / the secret command to use to obtain the flag.

```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --hxu
Initializing...
Correct usage! Your flag: pwn.college{whud7rau3HnXqvGgZ9ntHHIJ2aY.QX1EDO0wyMwkjNzEzW}
```

## What I Learned

I learned that using '/' or '?' to search for specific terms within manuals is a very effective way to quickly locate information.

## References

None

## Searching For Manuals - Challenge 5
### This challenge requires us to go through a manual of man itself to find the manual thats disguised which will give us the flag.

**Flag:** `pwn.college{8os3-ayS8pNHSSBKsfwhCtUKbaD.QX2EDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using man of MAN itself to find the afoaht and use ITS manual to get the command to print the flag to obtain the flag.

```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
osaypsfwht (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man osaypsfwht
hacker@man~searching-for-manuals:~$ /challenge/challenge --osayps 435
Incorrect usage! Please read the hidden challenge man page!
hacker@man~searching-for-manuals:~$ man osaypsfwht
hacker@man~searching-for-manuals:~$ /challenge/challenge --osayps 838
Correct usage! Your flag: pwn.college{8os3-ayS8pNHSSBKsfwhCtUKbaD.QX2EDO0wyMwkjNzEzW}
```

## What I Learned

Reviewing the manual for 'man' itself proved valuable, as it clarified how to use more advanced features of the tool.

## References

None

## Helpful Programs - Challenge 6
### This challenge requires us to use the --help to read and get the flag.

**Flag:** `pwn.college{o-uTKxY7E26ouJt9_CRCvsYtPp0.QX3IDO0wyMwkjNzEzW}` 

The process of obtaining the flag the --help command to get the correct value to use as an arg to another command.

```
hacker@man~helpful-programs:~$ --help
bash: --help: command not found
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -g GIVE_THE_FLAG
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: invalid int value: 'GIVE_THE_FLAG'
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 726
hacker@man~helpful-programs:~$ /challenge/challenge -g 726
Correct usage! Your flag: pwn.college{o-uTKxY7E26ouJt9_CRCvsYtPp0.QX3IDO0wyMwkjNzEzW}
```

## What I Learned

I found that using the '--help' option can sometimes provide the necessary command information more efficiently than reading the full manual.

## References

None

## Help For Builtins - Challenge 7
### This challenge requires us to use the help command using the in-built ones in the shell.

**Flag:** `pwn.college{0N9RZLfUN1preFJKt1LBmMcIxWO.QX0ETO0wyMwkjNzEzW}` 

The process of obtaining the flag using the built in help commands for the challenge command and use the secret cmd obtained further for the flag.

```
hacker@man~help-for-builtins:~$ help
GNU bash, version 5.2.37(1)-release (x86_64-pc-linux-gnu)
These shell commands are defined internally.  Type `help' to see this list.
Type `help name' to find out more about the function `name'.
Use `info bash' to find out more about the shell in general.
Use `man -k' or `info' to find out more about commands not in this list.

A star (*) next to a name means that the command is disabled.

 job_spec [&]                                          history [-c] [-d offset] [n] or history -anrw [fil>
 (( expression ))                                      if COMMANDS; then COMMANDS; [ elif COMMANDS; then >
 . filename [arguments]                                jobs [-lnprs] [jobspec ...] or jobs -x command [ar>
 :                                                     kill [-s sigspec | -n signum | -sigspec] pid | job>
 [ arg... ]                                            let arg [arg ...]
 [[ expression ]]                                      local [option] name[=value] ...
 alias [-p] [name[=value] ... ]                        logout [n]
 bg [job_spec ...]                                     mapfile [-d delim] [-n count] [-O origin] [-s coun>
 bind [-lpsvPSVX] [-m keymap] [-f filename] [-q name>  popd [-n] [+N | -N]
 break [n]                                             printf [-v var] format [arguments]
 builtin [shell-builtin [arg ...]]                     pushd [-n] [+N | -N | dir]
 caller [expr]                                         pwd [-LP]
 case WORD in [PATTERN [| PATTERN]...) COMMANDS ;;].>  read [-ers] [-a array] [-d delim] [-i text] [-n nc>
 cd [-L|[-P [-e]] [-@]] [dir]                          readarray [-d delim] [-n count] [-O origin] [-s co>
 challenge [--fortune] [--version] [--secret SECRET>   readonly [-aAf] [name[=value] ...] or readonly -p
 command [-pVv] command [arg ...]                      return [n]
 compgen [-abcdefgjksuv] [-o option] [-A action] [-G>  select NAME [in WORDS ... ;] do COMMANDS; done
 complete [-abcdefgjksuv] [-pr] [-DEI] [-o option] [>  set [-abefhkmnptuvxBCEHPT] [-o option-name] [--] [>
 compopt [-o|+o option] [-DEI] [name ...]              shift [n]
 continue [n]                                          shopt [-pqsu] [-o] [optname ...]
 coproc [NAME] command [redirections]                  source filename [arguments]
 declare [-aAfFgiIlnrtux] [name[=value] ...] or decl>  suspend [-f]
 dirs [-clpv] [+N] [-N]                                test [expr]
 disown [-h] [-ar] [jobspec ... | pid ...]             time [-p] pipeline
 echo [-neE] [arg ...]                                 times
 enable [-a] [-dnps] [-f filename] [name ...]          trap [-lp] [[arg] signal_spec ...]
 eval [arg ...]                                        true
 exec [-cl] [-a name] [command [argument ...]] [redi>  type [-afptP] name [name ...]
 exit [n]                                              typeset [-aAfFgiIlnrtux] name[=value] ... or types>
 export [-fn] [name[=value] ...] or export -p          ulimit [-SHabcdefiklmnpqrstuvxPRT] [limit]
 false                                                 umask [-p] [-S] [mode]
 fc [-e ename] [-lnr] [first] [last] or fc -s [pat=r>  unalias [-a] name [name ...]
 fg [job_spec]                                         unset [-f] [-v] [-n] [name ...]
 for NAME [in WORDS ... ] ; do COMMANDS; done          until COMMANDS; do COMMANDS-2; done
 for (( exp1; exp2; exp3 )); do COMMANDS; done         variables - Names and meanings of some shell varia>
 function name { COMMANDS ; } or name () { COMMANDS >  wait [-fn] [-p var] [id ...]
 getopts optstring name [arg ...]                      while COMMANDS; do COMMANDS-2; done
 hash [-lr] [-p pathname] [-dt] [name ...]             { COMMANDS ; }
 help [-dms] [pattern ...]
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "0N9RZLfU".
hacker@man~help-for-builtins:~$ challenge --secret 0N9RZLfU
Correct! Here is your flag!
pwn.college{0N9RZLfUN1preFJKt1LBmMcIxWO.QX0ETO0wyMwkjNzEzW}
```

## What I Learned

I learned that the 'help' command for built-in shell functions is a fast way to resolve questions about their usage. arguements can also be passed to the help command (here I passed challenge arguement)

## References


None
