# Processes and Jobs

## Listing Processes - Challenge 1
**Flag:** `pwn.college{cbKQHxrLLFS6HoUGeOMvEPnYqqx.QX4MDO0wyMwkjNzEzW`

The process of obtaining the flag involved using `ps`.

```
hacker@processes~listing-processes:~$ ps -ef | grep challenge
root         132       1  0 15:20 ?        00:00:00 /challenge/3663-run-29852
hacker       171     158  0 15:33 pts/1    00:00:00 grep --color=auto challenge
hacker@processes~listing-processes:~$ /challenge/3663-run-29852
Yahaha, you found me! Here is your flag:
pwn.college{cbKQHxrLLFS6HoUGeOMvEPnYqqx.QX4MDO0wyMwkjNzEzW}
Now I will sleep for a while (so that you could find me with 'ps')
```

## What I Learned
I learned how to list running processes.By piping the output of ps to grep, I can quickly filter the long list to find the specific process I'm looking for

## References
None

---

## Killing Processes - Challenge 2
**Flag:** `pwn.college{MCqIywGlFQatDsUZO9psCvLaBf5.QXyQDO0wyMwkjNzEzW}`

The process of obtaining the flag involved using `kill`.

```
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 17:06 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-i
root           7       1  0 17:06 ?        00:00:00 /run/dojo/bin/sleep 6h
root         135       1  0 17:06 ?        00:00:00 su -c /challenge/.launcher hacker
hacker       136     135  0 17:06 ?        00:00:00 /challenge/dont_run
hacker       137     136  0 17:06 ?        00:00:00 sleep 6h
hacker       139       0  0 17:06 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/
hacker       145     139  0 17:06 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       154       0  0 17:07 pts/1    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/
hacker       160     154  0 17:07 pts/1    00:00:00 /run/dojo/bin/bash --login
hacker       169     160  0 17:08 pts/1    00:00:00 ps -ef
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{MCqIywGlFQatDsUZO9psCvLaBf5.QXyQDO0wyMwkjNzEzW}
```

## What I Learned
I learned how to kill processes using their PID (which I can find by using the earlier pf -ef).

## References
None

---

## Interrupting Processes - Challenge 3
**Flag:** `pwn.college{QJO-w1LfukwFjOJGacBg6Ulm_MZ.QXzQDO0wyMwkjNzEzW}`

The process of obtaining the flag involved sending an interrupt signal using ctrl c.

```
hacker@processes~interrupting-processes:~$ ^C
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{QJO-w1LfukwFjOJGacBg6Ulm_MZ.QXzQDO0wyMwkjNzEzW}
```

## What I Learned
A process can be interrupted by using ctrl + c if it is unneeded at that moment.

## References
None

---

## Killing Misbehaving Processes - Challenge 4
**Flag:** `pwn.college{flag_here}`

The process of obtaining the flag involved using `kill`

```
hacker@processes~killing-misbehaving-processes:~$ ps -ef | grep decoy
hacker       215     205  0 17:25 pts/3    00:00:00 grep --color=auto decoy
hacker@processes~killing-misbehaving-processes:~$ kill decoy
bash: kill: decoy: arguments must be process or job IDs
hacker@processes~killing-misbehaving-processes:~$ kill 215
bash: kill: (215) - No such process
hacker@processes~killing-misbehaving-processes:~$ kill 205
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{MinEhVA7hnd8TXSyVnf-dxFtlT4.0FNzMDOxwyMwkjNzEzW}
```

## What I Learned
I combined the use of ps -ef to list the processes and piped that data into grep so that i get the process ID of the decoy. Then I killed the decoy process. Then I cat at the given location to get the flag. 

## References
None

---

## Suspending Processes - Challenge 5
**Flag:** `pwn.college{UmsakSBXuxEVOlPGmAmEQT2cgc-.QX1QDO0wyMwkjNzEzW}`

The process of obtaining the flag involved using ctrl + z .

```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         153     135  0 17:31 pts/0    00:00:00 bash /challenge/run
root         155     153  0 17:31 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         153     135  0 17:31 pts/0    00:00:00 bash /challenge/run
root         160     135  0 17:32 pts/0    00:00:00 bash /challenge/run
root         162     160  0 17:32 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{UmsakSBXuxEVOlPGmAmEQT2cgc-.QX1QDO0wyMwkjNzEzW}
```

## What I Learned
I learned that Ctrl Z is a way to suspend a running foreground process and send it to the background. This is different from Ctrl C which terminates it. Suspending a process frees up my terminal so I can run other commands

## References
None

---

## Resuming Processes - Challenge 6
**Flag:** `pwn.college{EluVpwqfKvt1yfXc8FLOTfXyOIM.QX2QDO0wyMwkjNzEzW}`

The process of obtaining the flag involved using `fg` to resume background processes.

```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{EluVpwqfKvt1yfXc8FLOTfXyOIM.QX2QDO0wyMwkjNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
```

## What I Learned
I learned how to take a background process into foreground to resume it again once its paused.

## References
None

---

## Backgrounding Processes - Challenge 7
**Flag:** `pwn.college{AyyqQ34tm7NVvXUtLsHTX5CSlNa.QX3QDO0wyMwkjNzEzW}`

The process of obtaining the flag involved running a program, suspending it, resuming it in the background, and then running a second instance of the program

```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         169 S+   bash /challenge/run
root         171 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         169 S    bash /challenge/run
root         179 S    sleep 6h
root         180 S+   bash /challenge/run
root         182 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{AyyqQ34tm7NVvXUtLsHTX5CSlNa.QX3QDO0wyMwkjNzEzW}

Goodbye!
```

## What I Learned
I learned how to resume a process in background using `bg`.

## References
None

---

## Foregrounding Processes - Challenge 8
**Flag:** `pwn.college{EluVpwqfKvt1yfXc8FLOTfXyOIM.QX2QDO0wyMwkjNzEzW}`

The process of obtaining the flag involved using `fg` to resume background processes.

```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
You resumed me into the foreground from suspension! Please resume me into the
background, and *then* swap me into the foreground directly from there (or
press Enter, and I'll exit).

hacker@processes~foregrounding-processes:~$ bg
bash: bg: current: no such job
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{Qd-9bDT9Uyiioo_0HMY0IPRmcx5.QX4QDO0wyMwkjNzEzW}
```

## What I Learned
I learned how to take a process to the background and then bring it to the foreground using `fg`.

## References
None

---

## Starting Backgrounded Processes - Challenge 9
**Flag:** `pwn.college{8lTYsyz0CFtaz6V2Dgqt13wv_7p.QX5QDO0wyMwkjNzEzW}`

The process of obtaining the flag involved starting a process directly in the background.

```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 163
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{8lTYsyz0CFtaz6V2Dgqt13wv_7p.QX5QDO0wyMwkjNzEzW}

Goodbye!
```

## What I Learned
learnt how to start a process directly from the background without bringing it to the foreground.

## References
None

---

## Process Exit Codes - Challenge 10
**Flag:** `pwn.college{gMsIqwfA3C1nWe11ld6INVacPRI.QX5YDO1wyMwkjNzEzW}`

The process of obtaining the flag involved using the exit code status of previously run command.

```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ /challenge/submit-code $?
CORRECT! Here is your flag:
pwn.college{gMsIqwfA3C1nWe11ld6INVacPRI.QX5YDO1wyMwkjNzEzW}
```

## What I Learned
I learned about command exit codes. Every command returns a status code when it finishes, which is 0 for success and a non-zero number for failure. I can access the exit code of the very last command using the special variable `$?`.

## References
None


