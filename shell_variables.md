# Shell Variables

## Printing Variables - Challenge 1
### This challenge requires printing the value of a shell variable.

**Flag:** `pwn.college{QRabHC5zbR5so0i79Ni9yJyzP4M.QX3UTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using `echo $VARIABLE`.

```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{QRabHC5zbR5so0i79Ni9yJyzP4M.QX3UTN0wyMwkjNzEzW}
```

## What I Learned

I learned that prefixing a variable name with `$` expands its value and echo prints it to the terminal.

## References

None

---

## Setting Variables - Challenge 2
### This challenge requires setting a shell variable.

**Flag:** `pwn.college{I9jxGxeKoxVZkyWueTF3Bi3d3yx.QX5UTN0wyMwkjNzEzW}`

The process of obtaining the flag involved assigning a value to a variable.

```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{I9jxGxeKoxVZkyWueTF3Bi3d3yx.QX5UTN0wyMwkjNzEzW}
```

## What I Learned

I learned that I assign shell variables without a $ and with no spaces around =, and that variable names and values are case-sensitive.

## References

None

---

## Multi-word Variables - Challenge 3
### This challenge requires setting a variable with multiple words.

**Flag:** `pwn.college{YOChNNkVZve8N9ACxBz2isXpR6H.QXwYTN0wyMwkjNzEzW}`

The process of obtaining the flag involved quoting the value.

```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YOChNNkVZve8N9ACxBz2isXpR6H.QXwYTN0wyMwkjNzEzW}
```

## What I Learned

I learned how to set and print variables with spaces using quotes.

## References

None

---

## Exporting Variables - Challenge 4
### This challenge requires exporting a variable to the environment.

**Flag:** `pwn.college{0tggpPT-ctxtm8Kr0nOL4XgGVpb.QXyYTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using `export`.

```
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$  /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{0tggpPT-ctxtm8Kr0nOL4XgGVpb.QXyYTN0wyMwkjNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```

## What I Learned

I learned how to export a variable to the environment. A plain VAR=value stays only in the current shell. $ is only for reading variables

## References

None

---

## Printing Exported Variables - Challenge 5
### This challenge requires printing an exported variable.

**Flag:** `pwn.college{g7pN1MW0TfpGnsXxKoDV5HkmWtZ.QX4UTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using `printenv` or `env`.

```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=1329c10edee3eaa05ad7070d6a70090bbe508062acb054fa93e79b2da17b6b3a
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{g7pN1MW0TfpGnsXxKoDV5HkmWtZ.QX4UTN0wyMwkjNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```

## What I Learned

I learned how to print exported variables using `env`.

## References

None

---

## Storing Command Output - Challenge 6
### This challenge requires storing command output in a variable.

**Flag:** `pwn.college{8e_SmsXsSrjwG74-ajBXPy_TL94.QX1cDN1wyMwkjNzEzW}`

The process of obtaining the flag involved using command substitution.

```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{8e_SmsXsSrjwG74-ajBXPy_TL94.QX1cDN1wyMwkjNzEzW}
```

## What I Learned

I learned to use command substitution $() to capture a command's output into a variable

## References

None

---

## Reading Input - Challenge 7
### This challenge requires reading input into a variable.

**Flag:** `pwn.college{8AC6gWxHror1e3PhoJPifZ9pgS6.QX4cTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using `read`.

```
hacker@variables~reading-input:~$ read PWN
echo $COLLEGE
You've set the PWN variable, but it does not look like the value is correct.
Make sure that the value is COLLEGE!
hacker@variables~reading-input:~$ COLLEGE
bash: COLLEGE: command not found
You've set the PWN variable, but it does not look like the value is correct.
Make sure that the value is COLLEGE!
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{8AC6gWxHror1e3PhoJPifZ9pgS6.QX4cTN0wyMwkjNzEzW}
```

## What I Learned

I learned how to use `read` to get input from the user in a shell and store it in a variable.

## References

None

---

## Reading Files - Challenge 8
### This challenge requires reading a file's contents into a variable.

**Flag:** `pwn.college{Mf32H1kzMWF8Qa1FxKxm-eUJGut.QXwIDO0wyMwkjNzEzW}`

The process of obtaining the flag involved using command substitution with `cat`.

```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Mf32H1kzMWF8Qa1FxKxm-eUJGut.QXwIDO0wyMwkjNzEzW}
```

## What I Learned

learned how to read the contents of a file into a shell variable by using the input redirection operator (<) with the read command. Using this way also we dont need to use the `cat` command.

## References

None
