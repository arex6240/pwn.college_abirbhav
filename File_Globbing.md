# File Globbing

## Matching with * - Challenge 1
### This challenge requires us to use the * to match the directory to cd into.

**Flag:** `pwn.college{cNRtDeCyuXpr6o__baYqMdqfS-t.QXxIDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved switching to SSH on the pwn.college challenge first, then using the given command along the * (matching operator).

```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{cNRtDeCyuXpr6o__baYqMdqfS-t.QXxIDO0wyMwkjNzEzW}
```

## What I Learned

This challenge showed me how to use the asterisk (*) as a matching operator to simplify directory navigation.

## References

None

## Matching with ? - Challenge 2
### This challenge requires us to use the ? as a matching operator.

**Flag:** `pwn.college{ci938R1M-RDnuop2KA3JpqKEXOB.QXyIDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the ? match operator to get into the working directory.

```
hacker@globbing~matching-with-:~$ cd /?????enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{ci938R1M-RDnuop2KA3JpqKEXOB.QXyIDO0wyMwkjNzEzW}
```

## What I Learned

I learned how the question mark (?) can be used as a wildcard to match single characters in directory or file names.

## References

None

## Matching with [] - Challenge 3
### This challenge requires us to use the [] matching operator to find the flag.

**Flag:** `pwn.college{4IaXYBoC2GAJpFCdM62xTElaI8M.QXzIDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the match operator using [].

```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{4IaXYBoC2GAJpFCdM62xTElaI8M.QXzIDO0wyMwkjNzEzW}
```

## What I Learned

This task helped me understand how square brackets ([]) can be used to match specific sets of characters when searching for files.

## References

None

## Matching Paths with [] - Challenge 4
### This challenge requires us to use the [] matching operator along with the path to get the flag.

**Flag:** `pwn.college{kT1846lewZVwGYCul6XJ1ZcQabL.QX0IDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the [] match operator along with path of the file to run.

```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{kT1846lewZVwGYCul6XJ1ZcQabL.QX0IDO0wyMwkjNzEzW}
```

## What I Learned

I realized that combining [] with a file path makes it much easier to target and run files from a specific directory.

## References

None

## Multiple Globs - Challenge 5
### This challenge requires us to use multiple globs to find the flag in one of many files that are similarly titled.

**Flag:** `pwn.college{koc_bJcPCrcRw3Xe9Lz6fkfBQhh.0lM3kjNxwyMwkjNzEzW}` 

The process of obtaining the flag involved using multiple glob i.e *p* to find the flag.

```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{koc_bJcPCrcRw3Xe9Lz6fkfBQhh.0lM3kjNxwyMwkjNzEzW}
```

## What I Learned

I discovered that using multiple globs lets you quickly traverse through lots of similarly named files with minimal effort.

## References

None

## Mixing Globs - Challenge 6
### This challenge requires us to use mixed globs to obtain the flag in a file.

**Flag:** `pwn.college{8oBQSTUvw68DpwF5nJJLutHH1PJ.QX1IDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the mixed glob []* to get the flag.

```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[cpe]*
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[cep]*
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[cp]*
Your expansion did not expand to the requested files (challenging, educational,
pwning). Instead, it expanded to:
challenging educational fantastic happy incredible magical nice optimistic pwning splendid uplifting victorious
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cpe]*
You got it! Here is your flag!
pwn.college{8oBQSTUvw68DpwF5nJJLutHH1PJ.QX1IDO0wyMwkjNzEzW}
```

## What I Learned

This challenge demonstrated how mixing different glob patterns can help you match files that fit certain criteria more efficiently.

## References

None

## Exclusion Globs - Challenge 7
### This challenge requires us to use excluded command to obtain flags in a file without the words p,w,n.

**Flag:** `pwn.college{0DLiomCxcEqnycNJN1YgdXfz0v9.QX2IDO0wyMwkjNzEzW}` 

The process of obtaining the flag using exclusion glob command to obtain the flag.

```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files/
hacker@globbing~exclusionary-globbing:/challenge/files$ ls
amazing      delightful   great       jovial    magical     pwning   splendid   victorious  youthful
beautiful    educational  happy       kind      nice        queenly  thrilling  wonderful   zesty
challenging  fantastic    incredible  laughing  optimistic  radiant  uplifting  xenial
hacker@globbing~exclusionary-globbing:/challenge/files$  /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{0DLiomCxcEqnycNJN1YgdXfz0v9.QX2IDO0wyMwkjNzEzW}
```

## What I Learned

I learned that exclusion globs are a handy way to filter out unwanted files and focus on a targeted group.

## References

None

## Tab Completion - Challenge 8
### This challenge requires us to use tab to complete commands for the suggested ones by the terminal.

**Flag:** `pwn.college{o_Xl5LvfTi8K44nYYuLDO0UMXY7.0FN0EzNxwyMwkjNzEzW}` 

The process of obtaining the flag using the tab completion to access a file in a given directory.

```
hacker@globbing~tab-completion:~$ ls /challenge/
DESCRIPTION.md  pwncollege​
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​
pwn.college{o_Xl5LvfTi8K44nYYuLDO0UMXY7.0FN0EzNxwyMwkjNzEzW}
```

## What I Learned

I found out that using tab completion can really speed up typing commands and reduce mistakes.

## References

None

## Multiple options for Tab Completion - Challenge 9
### This challenge requires us to use tab to complete commands for the suggested ones by the terminal.

**Flag:** `pwn.college{8-mL27ERxF340YJnqo94YSfrqcb.0lN0EzNxwyMwkjNzEzW}` 

The process of obtaining the flag using the tab completion to access a file in a given directory.

```
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/
cat: /challenge/files/: Is a directory
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/
hack-the-planet        pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{8-mL27ERxF340YJnqo94YSfrqcb.0lN0EzNxwyMwkjNzEzW}
```

## What I Learned

The challenge taught me on how to use the tab to complete the commands to get through them easier.

## References

None

## Tab Completion On Commands - Challenge 10
### This challenge requires us to use tab to complete commands for the suggested ones by the terminal.

**Flag:** `pwn.college{Qf-hOyGguVvVL-vvgN_t9K-4sen.0VN0EzNxwyMwkjNzEzW}` 

The process of obtaining the flag using the tab completion to access a file in a given directory.

```
Connected!
hacker@globbing~tab-completion-on-commands:~$ pwncollege-8690
Correct! Here is your flag:
pwn.college{Qf-hOyGguVvVL-vvgN_t9K-4sen.0VN0EzNxwyMwkjNzEzW}
```

## What I Learned

I realized that tab completion is useful not just for files, but also for completing command names.

## References

None