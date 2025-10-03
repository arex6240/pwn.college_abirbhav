# Chaining Commands

## Chaining with Semicolons - Challenge 1
**Flag:** `pwn.college{0INbVdjrnhG6C0F5aedR0eDLzKq.QX1UDO0wyMwkjNzEzW}`

The process of obtaining the flag involved chaining commands with `;`.

```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn;/challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{0INbVdjrnhG6C0F5aedR0eDLzKq.QX1UDO0wyMwkjNzEzW}
```

## What I Learned
I learned how to chain commands with semicolons so they run one after another regardless of success or failure.

## References
None

---

## Building on Success - Challenge 2
**Flag:** `pwn.college{kfvBCRRHuTy0TgtuVBx-Dj9aVnK.0lM0MDOxwyMwkjNzEzW}`

The process of obtaining the flag involved chaining commands with `&&`.

```
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{kfvBCRRHuTy0TgtuVBx-Dj9aVnK.0lM0MDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to chain commands so the next runs only if the previous succeeds using the `&&` operator.

## References
None

---

## Handling Failure - Challenge 3
**Flag:** `pwn.college{4KwjhKhjcERWYLX9P3J1JHB-5HR.01M0MDOxwyMwkjNzEzW}`

The process of obtaining the flag involved chaining commands with `||`

```
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{4KwjhKhjcERWYLX9P3J1JHB-5HR.01M0MDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to chain commands so the next runs only if the previous fails using `||` operator.

## References
None

---

## Your First Shell Script - Challenge 4
**Flag:** `pwn.college{YIjzok6Reu3Jm-5lAGSNMFLkc0m.QXxcDO0wyMwkjNzEzW}`

The process of obtaining the flag involved writing a shell script and running it.

```
hacker@chaining~your-first-shell-script:~$ echo -e "/challenge/pwn\n/challenge/college" > x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{YIjzok6Reu3Jm-5lAGSNMFLkc0m.QXxcDO0wyMwkjNzEzW}
```

## What I Learned
I learned how to write and run a basic shell script. it is like instead of typing commands one by one, I can save a sequence of them in a file (like x.sh). This allows me to automate complex or repetitive tasks

## References
None

---

## Redirecting Script Output - Challenge 5
**Flag:** `pwn.college{AN9dsDVwpPqPqZj3yUn9-MeNbjd.QX4ETO0wyMwkjNzEzW}`

The process of obtaining the flag involved redirecting output from a shell script.

```
hacker@chaining~redirecting-script-output:~$ echo -e "/challenge/pwn\n/challenge/college" > script.sh
hacker@chaining~redirecting-script-output:~$ bash script.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{AN9dsDVwpPqPqZj3yUn9-MeNbjd.QX4ETO0wyMwkjNzEzW}
```

## What I Learned
I learned how to redirect script output to a file. In this case, I piped the output of a script containing multiple commands into a final program

## References
None

---

## Executable Shell Scripts - Challenge 6
**Flag:** `pwn.college{M6rQDDNIPI9VEsg6a0qpPs1XPOj.QX0cjM1wyMwkjNzEzW}`

The process of obtaining the flag involved making a shell script executable.

```
hacker@chaining~executable-shell-scripts:~$ echo "/challenge/solve" > solve.sh
hacker@chaining~executable-shell-scripts:~$ chmod +x solve.sh
hacker@chaining~executable-shell-scripts:~$ ~/solve.sh
You must make a shellscript in your home directory that will launch
/challenge/solve, make it executable, and invoke it without explicitly
specifying 'bash'!
hacker@chaining~executable-shell-scripts:~$ ./solve.sh
Congratulations on your shell script execution! Your flag:
pwn.college{M6rQDDNIPI9VEsg6a0qpPs1XPOj.QX0cjM1wyMwkjNzEzW}
```

## What I Learned
I learned how to make a shell script executable and run it directly. Instead of always typing bash script.sh, I can use chmod +x script.sh to give the file execute permissions. After that, I can run it directly by referencing its path 

## References
None

---

## Understanding Shebangs - Challenge 7
**Flag:** `pwn.college{YHQoO_aI2pbi41tD9D7ZStuNTX2.0VOzMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using a shebang (`#!`) in a shell script.

```
hacker@chaining~understanding-shebangs:~$ echo -e '#!/bin/bash\necho "hack the planet"' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{YHQoO_aI2pbi41tD9D7ZStuNTX2.0VOzMDOxwyMwkjNzEzW}
```

## What I Learned
I learned how a shebang specifies the interpreter for a script. By placing `#!/bin/bash` as the very first line in my file, I'm telling the Linux kernel that whenever this file is executed, it should be interpreted using the /bin/bash program

## References
None

---

## Scripting with Arguments - Challenge 8
**Flag:** `pwn.college{gOb1K-UT-ANhm2Z0-Vr3_-SfubM.0VNzMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved passing arguments to a shell script.

```
hacker@chaining~scripting-with-arguments:~$ echo -e '#!/bin/bash\necho $2 $1' > /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ /home/hacker/solve.sh first second
second first
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{gOb1K-UT-ANhm2Z0-Vr3_-SfubM.0VNzMDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to use positional parameters in shell scripts. I can access the arguments passed to my script using special positional parameter variables like  $1 for the first argument, $2 for the second, etc.

## References
None

---

## Scripting with Conditionals - Challenge 9
**Flag:** `pwn.college{Mi8V0TvAjjcgwbcqhADk220l_mx.0lNzMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using conditionals (`if`, `then`, `else`) in a shell script.

```
hacker@chaining~scripting-with-conditionals:~$ echo -e '#!/bin/bash\nif [ "$1" == "pwn" ]\nthen\n\techo "college"\nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ /home/hacker/solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ /home/hacker/solve.sh foo
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{Mi8V0TvAjjcgwbcqhADk220l_mx.0lNzMDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to use conditionals in shell scripts. I also learned to be careful with the syntax, especially the required spaces inside the brackets.

## References
GOOGLE GEMINI

---

## Scripting with Default Cases - Challenge 10
**Flag:** `pwn.college{Y0N8BEQC9017MAEXy4kupQL0xMm.01NzMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using default cases in a shell script.

```
hacker@chaining~scripting-with-default-cases:~$ echo -e '#!/bin/bash\nif [ "$1" == "pwn" ]\nthen\n\techo "college"\nelse\n\techo "nope"\nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ /home/hacker/solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ /home/hacker/solve.sh hack
nope
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{Y0N8BEQC9017MAEXy4kupQL0xMm.01NzMDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to set default values for variables in shell scripts.

## References
None

---

## Scripting with Multiple Conditions - Challenge 11
**Flag:** `pwn.college{kxRKN5I9KA2o3aPUKOODEF6he-V.0FOzMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using multiple conditions in a shell script.

```
hacker@chaining~scripting-with-multiple-conditions:~$ echo '#!/bin/bash; if [ "$1" == "hack" ]; then echo "the planet"; elif [ "$1" == "pwn" ]; then echo "college"; elif [ "$1" == "learn" ]; then echo "linux"; else echo "unknown"; fi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /home/hacker/solve.sh hack
bash: /home/hacker/solve.sh: cannot execute: required file not found
hacker@chaining~scripting-with-multiple-conditions:~$ echo -e '#!/bin/bash\nif [ "$1" == "hack" ]; then echo "the planet"; elif [ "$1" == "pwn" ]; then echo "college"; elif [ "$1" == "learn" ]; then echo "linux"; else echo "unknown"; fi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /home/hacker/solve.sh hack
the planet
hacker@chaining~scripting-with-multiple-conditions:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{kxRKN5I9KA2o3aPUKOODEF6he-V.0FOzMDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to use multiple conditions in shell scripts. I can also write complex conditional logic on a single line by using semicolons as command separators

## References
GOOGLE GEMINI LLM

---

## Reading Shell Scripts - Challenge 12
**Flag:** `pwn.college{MRvNuznBprnglYQbbShiZvfRlsv.0lMwgDOxwyMwkjNzEzW}`

The process of obtaining the flag involved reading and understanding a shell script.

```
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{MRvNuznBprnglYQbbShiZvfRlsv.0lMwgDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to read and interpret shell scripts. sensitive information, like passwords or API keys, should never be hardcoded directly into a script

## References
None
