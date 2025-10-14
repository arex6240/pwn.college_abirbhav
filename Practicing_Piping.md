# Practicing Piping

## Redirecting Output - Challenge 1
### This challenge requires redirecting standard output to a file.

**Flag:** `pwn.college{AuSvgcF3rFinWAWnDTqaArZzRJR.QX0YTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using the `>` operator to redirect output.

```
hacker@piping~redirecting-output:~$ echo COLLEGE > PWN
You may have created a PWN file instead of a COLLEGE file.
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{AuSvgcF3rFinWAWnDTqaArZzRJR.QX0YTN0wyMwkjNzEzW}
```

## What I Learned

learnt how to make a file and input words inside it using terminal and the echo command. Made a silly error that I create PWN file instead of COLLEGE.

## References

None

---

## Redirecting More Output - Challenge 2
### This challenge requires redirecting both stdout and stderr.

**Flag:** `pwn.college{U4lsSJ_z77ZIUk9tWyw4iY88yzY.QX1YTN0wyMwkjNzEzW}`

The process of obtaining the flag involved redirecting both outputs using `>`.

```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{U4lsSJ_z77ZIUk9tWyw4iY88yzY.QX1YTN0wyMwkjNzEzW}
```

## What I Learned

learned how to redirect a program’s standard output to a file while still seeing its standard error in the terminal.

## References

None

---

## Appending Output - Challenge 3
### This challenge requires appending output to a file.

**Flag:** `pwn.college{IvOeHfl1h52MNmvoIwgwhthX00V.QX3ATO0wyMwkjNzEzW}`

The process of obtaining the flag involved using the `>>` operator.

```
hacker@piping~appending-output:~$ /challenge/run > /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{IvOeHfl1h52MNmvoIwgwhthX00V.QX3ATO0wyMwkjNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
```

## What I Learned

learned to use append redirection (>>) so both the program’s direct file write and its later stdout write are preserved.

## References

None

---

## Redirecting Errors - Challenge 4
### This challenge requires redirecting standard error to a file.

**Flag:** `pwn.college{gLTN_lCIFubIHG1oKG3lLUoHPpD.QX3YTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using `2>` to redirect errors.

```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{gLTN_lCIFubIHG1oKG3lLUoHPpD.QX3YTN0wyMwkjNzEzW}
```

## What I Learned

learned to redirect stdout (FD 1) and stderr (FD 2) separately. ANd sending the flag to myflag and the program’s messages to instructions...

## References

None

---

## Redirecting Input - Challenge 5
### This challenge requires redirecting input from a file.

**Flag:** `pwn.college{o9VmiorkNfuwjIWx3qp12-yT8DO.QXwcTN0wyMwkjNzEzW}`

The process of obtaining the flag involved using `<` to provide input.

```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{o9VmiorkNfuwjIWx3qp12-yT8DO.QXwcTN0wyMwkjNzEzW}
```

## What I Learned

learned to use input redirection (<) so the program reads its input from the PWN file .

## References

None

---

## Grepping Stored Results - Challenge 6
### This challenge requires using `grep` on a file.

**Flag:** `pwn.college{YO1rv1GnnUj0UHcpDRve1bo1qA9.QX4EDO0wyMwkjNzEzW}`

The process of obtaining the flag involved using `grep` to search a file.

```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep -m1 'pwn.college' /tmp/data.txt
pwn.college{YO1rv1GnnUj0UHcpDRve1bo1qA9.QX4EDO0wyMwkjNzEzW}
```

## What I Learned

Redirect the program’s large output into /tmp/data.txt and use grep to search that file for the flag string. The -m1 is used to stop after finding the first match.

## References

OPENAI LLM

---

## Grepping Live Output - Challenge 7
### This challenge requires using `grep` on command output.

**Flag:** `pwn.college{kXBWUdPeqR9FZ4JH8MbE1rkohml.QX5EDO0wyMwkjNzEzW}`

The process of obtaining the flag involved piping output to `grep`.

```
hacker@piping~grepping-live-output:~$ /challenge/run | grep -m1 'pwn.college'
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{kXBWUdPeqR9FZ4JH8MbE1rkohml.QX5EDO0wyMwkjNzEzW}
```

## What I Learned

Pipe the program’s stdout into grep so that I can  search the stream directly and stop after the first matching flag with -m1 (first match).

## References

None

---

## Grepping Errors - Challenge 8
### This challenge requires grepping standard error output.

**Flag:** `pwn.college{UChzoRmpFcjTpNXzghwLA-sFHfc.QX1ATO0wyMwkjNzEzW}`

The process of obtaining the flag involved redirecting stderr and piping to `grep`.

```
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep -m1 'pwn.college'
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{UChzoRmpFcjTpNXzghwLA-sFHfc.QX1ATO0wyMwkjNzEzW}
```

## What I Learned

Redirected stderr into stdout with 2>&1 so the pipe receives both streams. then grep the combined output for the flag and stop using -m1 related to first match.

## References

None

---

## Filtering with grep -v - Challenge 9
### This challenge requires filtering out lines with `grep -v`.

**Flag:** `pwn.college{oHmKsHe0W9qxez_PTXlZ483IzUp.0FOxEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `grep -v` to exclude lines.

```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v 'DECOY' | grep -m1 'pwn.college'
pwn.college{oHmKsHe0W9qxez_PTXlZ483IzUp.0FOxEzNxwyMwkjNzEzW}
```

## What I Learned

learned to pipe the program into grep -v to remove any lines containing DECOY. Then I used grep -m1 the remaining stream for the real pwn.college flag.

## References

None

---

## Duplicating Piped Data with tee - Challenge 10
### This challenge requires using `tee` to duplicate output.

**Flag:** `pwn.college{Q0nCKbAA6GU1qWP_HSOi737qin9.QXxITO0wyMwkjNzEzW}`

The process of obtaining the flag involved using `tee` to write output to a file and display it.

```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee intercepted.txt | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat intercepted.txt
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "Q0nCKbAA"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret Q0nCKbAA | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{Q0nCKbAA6GU1qWP_HSOi737qin9.QXxITO0wyMwkjNzEzW}
```

## What I Learned

learned how to use the tee command to view the hidden output of a program within a pipeline to debug how it works

## References

None

---

## Process Substitution for Input - Challenge 11
### This challenge requires process substitution for input.

**Flag:** `pwn.college{wHQJWl9N1j8yx2TK4pgPdI0gh3O.0lNwMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using `<(command)`.

```
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
51a52
> pwn.college{wHQJWl9N1j8yx2TK4pgPdI0gh3O.0lNwMDOxwyMwkjNzEzW}
```

## What I Learned

Process substitution <(...) gives diff file like views of each command's output so we can compare them and extract the lines present only in the version that contains the real flag.

## References

None

---

## Writing to Multiple Programs - Challenge 12
### This challenge requires writing output to multiple programs.

**Flag:** `pwn.college{Ys4jOnrftt0CA9fhW57uoohkgUB.QXwgDN1wyMwkjNzEzW}`

The process of obtaining the flag involved using `tee` with multiple commands.

```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
2766611139138117527
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{Ys4jOnrftt0CA9fhW57uoohkgUB.QXwgDN1wyMwkjNzEzW}
```

## What I Learned

Used output process substitution >(command) with tee to send /challenge/hack’s output simultaneously to both /challenge/the and /challenge/planet.

## References

None

---

## Split-piping stderr and stdout - Challenge 13
### This challenge requires splitting stderr and stdout.

**Flag:** `pwn.college{IWhoDkdTU6U1hMfJXYfiCYw5sf2.QXxQDM2wyMwkjNzEzW}`

The process of obtaining the flag involved redirecting and piping outputs separately.

```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >( /challenge/planet ) 2> >( /challenge/the )
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{IWhoDkdTU6U1hMfJXYfiCYw5sf2.QXxQDM2wyMwkjNzEzW}
```

## What I Learned

Used output process substitution >(...) to hook the command’s stdout into /challenge/planet and its stderr (via 2>) into /challenge/the, keeping the streams separate.

## References

OPENAI LLM

---

## Named Pipes - Challenge 14
### This challenge requires using named pipes (FIFOs).

**Flag:** `pwn.college{oBEPt-XI9RuGdoeh0S8VxTtshNN.01MzMDOxwyMwkjNzEzW}`

The process of obtaining the flag involved creating and using a named pipe.

```
Terminal A (reader):

hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at
/tmp/flag_fifo! Here is your flag:
pwn.college{oBEPt-XI9RuGdoeh0S8VxTtshNN.01MzMDOxwyMwkjNzEzW}

Terminal B (writer):
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!
```

## What I Learned

I learned how to use named pipes for inter-process communication. FIFOs block until both reader and writer are open, so start a reader (cat /tmp/flag_fifo) to unblock /challenge/run > /tmp/flag_fifo and I receive the flag

## References


OPENAI LLM, GOOGLE GEMINI
