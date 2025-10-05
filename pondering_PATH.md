# Pondering PATH

## The PATH Variable - Challenge 1
**Flag:** `pwn.college{Uq-EZbK6stl8AQZkqlj9K_ADhhn.QX2cDM1wyMwkjNzEzW}`

The process of obtaining the flag involved printing the PATH variable.

```
hacker@path~the-path-variable:~$ export PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{Uq-EZbK6stl8AQZkqlj9K_ADhhn.QX2cDM1wyMwkjNzEzW}
```

## What I Learned
I understood that if PATH is empty, the shell can't find commands like ls or rm. For a change to a variable to affect a child process, I must use the export command. I exported an empty PATH, which caused the /challenge/run script to fail because it couldn't locate the rm.

## References
None

---

## Setting PATH - Challenge 2
**Flag:** `pwn.college{Y89eg8x4oMT7hkPtxzPms9-nrhI.QX1cjM1wyMwkjNzEzW}`

The process of obtaining the flag involved setting the PATH variable.

```
hacker@path~setting-path:~$ export PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{Y89eg8x4oMT7hkPtxzPms9-nrhI.QX1cjM1wyMwkjNzEzW}
```

## What I Learned
I learned how to set the PATH variable.

## References
None

---

## Finding Commands - Challenge 3
**Flag:** `pwn.college{EbdagzuAfrdykfMl6Je2flMGkXE.01NzEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `which`.

```
hacker@path~finding-commands:~$ which win
/challenge/paths/22748/win
hacker@path~finding-commands:~$ cat /challenge/paths/22748/win/flag
cat: /challenge/paths/22748/win/flag: Not a directory
hacker@path~finding-commands:~$ cat /challenge/paths/22748/flag
pwn.college{EbdagzuAfrdykfMl6Je2flMGkXE.01NzEzNxwyMwkjNzEzW}
```

## What I Learned
I learned how to find command locations using `which` command.

## References
None

---

## Adding Commands - Challenge 4
**Flag:** `pwn.college{IeT80zpfsOk1CLnUuvC3dgsp5-a.QX2cjM1wyMwkjNzEzW}`

The process of obtaining the flag involved adding a directory to PATH.

```
hacker@path~adding-commands:~$ mkdir /tmp/myscripts
hacker@path~adding-commands:~$ echo '#!/bin/bash' > /tmp/myscripts/win
hacker@path~adding-commands:~$ echo '/bin/cat /flag' >> /tmp/myscripts/win
hacker@path~adding-commands:~$ chmod +x /tmp/myscripts/win
hacker@path~adding-commands:~$ export PATH=/tmp/myscripts
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{IeT80zpfsOk1CLnUuvC3dgsp5-a.QX2cjM1wyMwkjNzEzW}
```

## What I Learned
I learned how to create a custom command by writing a shell script, making it executable with chmod +x, and adding its location to the $PATH.

## References
GOOGLE GEMINI

---

## Hijacking Commands - Challenge 5
**Flag:** `pwn.college{AWu4FgEIIJUkmvdLenGAoNv5SIi.QX3cjM1wyMwkjNzEzW}`

The process of obtaining the flag involved hijacking a command by placing a script earlier in PATH.

```
hacker@path~hijacking-commands:~$ mkdir /tmp/fake_bin
hacker@path~hijacking-commands:~$ echo '#!/bin/bash' > /tmp/fake_bin/rm
hacker@path~hijacking-commands:~$ echo 'echo " "' >> /tmp/fake_bin/rm
hacker@path~hijacking-commands:~$ chmod +x /tmp/fake_bin/rm
hacker@path~hijacking-commands:~$ export PATH=/tmp/fake_bin:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /tmp/fake_bin/rm. Executing!

hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /tmp/fake_bin/rm. Executing!

hacker@path~hijacking-commands:~$ cat /flag
cat: /flag: Permission denied
hacker@path~hijacking-commands:~$ echo 'cat /flag' > /tmp/fake_bin/rm
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /tmp/fake_bin/rm. Executing!
pwn.college{AWu4FgEIIJUkmvdLenGAoNv5SIi.QX3cjM1wyMwkjNzEzW}
```

## What I Learned
I learned how PATH order affects command execution. I made a fake rm to stop a script from deleting a file. like the shell searches for variables from left to right so I put the fake rm before the real one, so when run tried to delete the flag it ran the fake command and nothing was deleted. 

## References
GOOGLE GEMINI
