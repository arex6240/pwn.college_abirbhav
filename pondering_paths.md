# Pondering Paths

## The Root - Challenge 1
### This challenge requires us to invoke the / command followed by a directory to get the flag.

**Flag:** `pwn.college{ginnlK400SlaCLG-Mqf0yJ4cuEx.QX4cTO0wyMwkjNzEzW}` 

The process of obtaining the flag involved switching to SSH on the pwn.college challenge first, then using the / followed by 'pwn' to move into the directory of /pwn to get the flag.

```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{ginnlK400SlaCLG-Mqf0yJ4cuEx.QX4cTO0wyMwkjNzEzW}
```

## What I Learned

I figured out how to move around directories using the main `/` command.

## References

None

## Programs and absolute paths - Challenge 2
### This challenge requires us to navigate to the challenge directory for 'run' which gives us the flag.

**Flag:** `pwn.college{MJFTxJUzSXttOYCIAuGREaNdvvh.QX1QTN0wyMwkjNzEzW}` 

The process of obtaining the flag involved navigating to the /challenge/run directory i.e the absolute path.

```
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{MJFTxJUzSXttOYCIAuGREaNdvvh.QX1QTN0wyMwkjNzEzW}
```

## What I Learned

I learned how to jump straight to a file or folder using its full path. At first, I tried using `cd` before the path, but turns out, that wasn’t needed.

## References

None

## Position Thy Self - Challenge 3
### This challenge requires us to navigate to the challenge directory using the 'change directory(cd)' command which gives us the flag.

**Flag:** `pwn.college{QgDYBM79bx2G6ux622s01M9sMpl.QX2QTN0wyN4gjNzEzW}` 

The process of obtaining the flag involved navigating to the /challenge/run first, which gave us the directory to actually go to using the cd command to get the flag.

```
hacker@paths~position-thy-self:/sys/kernel$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{IwjqUR4689RViHikB4xlH3wQmFJ.QX2QTN0wyMwkjNzEzW}
```

## What I Learned

This time, I learned that sometimes you have to use `cd` to get into a pretty unusual directory like `/sys/kernel`before running a command.

## References

OpenAI ChatGPT LLM

## Position Elsewhere - Challenge 4
### This challenge requires us to navigate to the usr/include directory using the 'change directory(cd)' command which gives us the flag.

**Flag:** `pwn.college{EmLPQKYaCMEc9KgfmqBWMGl0YJe.QX3QTN0wyN4gjNzEzW}` 

The process of obtaining the flag involved navigating to the /challenge/run first, which gave us the directory to actually go to using the cd command to get the flag.

```
hacker@paths~position-elsewhere:/var$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{w9KPgfzti9-MB8HsloQRB11L8Fh.QX3QTN0wyMwkjNzEzW}
```

## What I Learned

I got a better feel for using `cd` to move to a specific directory, and then running commands from there using the absolute path.

## References

OpenAI ChatGPT LLM

## Position Yet Elsewhere - Challenge 5
### This challenge requires us to navigate to the /proc/131/fd directory using the 'change directory(cd)' command which gives us the flag.

**Flag:** `pwn.college{w9KPgfzti9-MB8HsloQRB11L8Fh.QX3QTN0wyMwkjNzEzW}` 

The process of obtaining the flag involved navigating to the /challenge/run first, which gave us the directory to actually go to using the cd command to get the flag.

```
hacker@paths~position-elsewhere:/var$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{w9KPgfzti9-MB8HsloQRB11L8Fh.QX3QTN0wyMwkjNzEzW}
```

## What I Learned

Again, using `cd` to get to the right spot was key.

## References

None

## Implicit Relative Paths, from / - Challenge 6
### This challenge requires us to navigate to the / directory using the 'change directory(cd)' and then run the relative path to obtain the flag.

**Flag:** `pwn.college{UlOGrkGXrPVm78pVa5n9dtt0eq7.QX5QTN0wyMwkjNzEzW}` 

The process of obtaining the flag involved navigating to the /directory using cd first, and then running the challenge/run relative path.

```
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UlOGrkGXrPVm78pVa5n9dtt0eq7.QX5QTN0wyMwkjNzEzW}
```

## What I Learned

I learned that if you’re already in the right folder, you can just use a relative path to run things directly

## References

None

## Explicit Relative Paths, from / - Challenge 7
### This challenge requires us to navigate to the / directory using the 'change directory(cd)' and then use explicit relative paths to get the flag.

**Flag:** `pwn.college{Yd2bZnLtNr7D2pnxtHvttYU3tCa.QXwUTN0wyMwkjNzEzW}` 

The process of obtaining the flag involved navigating to the /directory using cd first, using explicit relative paths, in this case './challenge/run'.

```
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Yd2bZnLtNr7D2pnxtHvttYU3tCa.QXwUTN0wyMwkjNzEzW}
```

## What I Learned

This one made it clear how to use explicit relative paths (like `./something`) when you’re in the right directory.

## References

None

## Implicit Relative Paths - Challenge 8    
### This challenge requires us to navigate to the /challenge directory using the 'change directory(cd)' and then use  relative paths to get the flag.

**Flag:** `pwn.college{Yd2bZnLtNr7D2pnxtHvttYU3tCa.QXwUTN0wyMwkjNzEzW}` 

The process of obtaining the flag involved navigating to the /challenge directory using cd first, using relative paths, in this case './run'.

```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Yd2bZnLtNr7D2pnxtHvttYU3tCa.QXwUTN0wyMwkjNzEzW}
```

## What I Learned

The process of obtaining the flag involved navigating to the /challenge directory using cd first, using relative paths, in this case './run'.

## References

None

## Home Sweet Home - Challenge 9   
### This challenge requires us to provide an absolute path and file along with /challenge/run which write the flag and reads it to us.

**Flag:** `pwn.college{owLEQpWtfqLscf9fEOhCf6SI6fJ.QXzMDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved providing an absolute path of a file for the flag to be written into.

```
hacker@paths~home-sweet-home:~$ /challenge/run ~/trr
The argument you provided must not have been longer than 3 characters (it's
currently 5 characters long)!
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{owLEQpWtfqLscf9fEOhCf6SI6fJ.QXzMDO0wyMwkjNzEzW}
```

## What I Learned

I learned that `~` always points to your home directory in Linux

## References

None