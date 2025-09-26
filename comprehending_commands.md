# Comprehending Commands

## Cat - not the pet, but the command! - Challenge 1
### This challenge requires us to invoke the cat command follwed by the file name to get the flag.

**Flag:** `pwn.college{oeIZ01e0SVdvCf26vNCepPjU0cr.QXxcTN0wyMwkjNzEzW}` 

The process of obtaining the flag involved switching to SSH on the pwn.college challenge first, then using the cat command along with the flag file to get the flag.

```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat ~/flag
pwn.college{oeIZ01e0SVdvCf26vNCepPjU0cr.QXxcTN0wyMwkjNzEzW}
```

## What I Learned

I got the hang of how the cat command works and what it actually does.

## References

None

## Catting absolute paths - Challenge 2
### This challenge requires us to use the cat command for the absolute path of a file which gives us the flag.

**Flag:** `pwn.college{gZ-RG4x79eRxG3y--Kb1cUVlbf2.QX5ETO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the cat commands followed by the absolute path of the flag file.

```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{gZ-RG4x79eRxG3y--Kb1cUVlbf2.QX5ETO0wyMwkjNzEzW}
```

## What I Learned

I figured out how to use cat with an absolute path to read files.

## References

None

## More catting practice - Challenge 3
### This challenge requires us to use the cat command along with the absolute path of a hidden file.

**Flag:** `pwn.college{IdxW1HZdvwMtJOjX88tVxQpAo80.QXwITO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using cd, which gave us the directory and the catting the absolute path of the file.

```
hacker@commands~more-catting-practice:~$ cat /usr/share/cmake/flag
pwn.college{IdxW1HZdvwMtJOjX88tVxQpAo80.QXwITO0wyMwkjNzEzW}
```

## What I Learned

Using cat with the full path makes grabbing hidden files super easy.

## References

None

## Grepping for a needle in a haystack - Challenge 4
### This challenge requires us to use the grep command to find the flag.

**Flag:** `pwn.college{UkiaC-6kxgzBH20dIlKpB7WN94B.QX3EDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved using the grep commands followed by the required substring to be found in a large text file.

```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{UkiaC-6kxgzBH20dIlKpB7WN94B.QX3EDO0wyMwkjNzEzW}
```

## What I Learned

I learned that when cat can't handle a huge file, grep can swoop in and find what I need fast.

## References

None

## Comparing Files - Challenge 5
### This challenge requires us to use the diff command to find the real flag in two files.

**Flag:** `pwn.college{ImcoaXP4SDopTfOG2w-UxnqVFdk.01MwMDOxwyMwkjNzEzW}` 

The process of obtaining the flag involved using the diff f1 f2 command to find the only real flag by comparing the two files.

```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
2a3
> pwn.college{ImcoaXP4SDopTfOG2w-UxnqVFdk.01MwMDOxwyMwkjNzEzW}
```

## What I Learned

I finally saw how diff points out differences between big files. Makes spotting changes way easier.

## References

None

## Listing Files - Challenge 6
### This challenge requires us to list the files in a given directory to obtain the flag.

**Flag:** `pwn.college{cZxi4fxQFbua9CLA4axf3UfezwN.QX4IDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved listing files in the challenge directory and then executing a file in it.

```
hacker@commands~listing-files:~$ ls /challenge
30237-renamed-run-29018  DESCRIPTION.md
hacker@commands~listing-files:~$  cat /challenge/30237-renamed-run-29018
#!/opt/pwn.college/bash

echo "Yahaha, you found me! Here is your flag:"
cat /flag
hacker@commands~listing-files:~$ /challenge/30237-renamed-run-29018
Yahaha, you found me! Here is your flag:
pwn.college{cZxi4fxQFbua9CLA4axf3UfezwN.QX4IDO0wyMwkjNzEzW}
```

## What I Learned

Listing out files and then poking around in them is actually pretty straightforward with ls.

## References

Google gemini

## Touching Files - Challenge 7
### This challenge requires us to create two files in the specified directories to get the flag.

**Flag:** `pwn.college{osFXzXO3Gwkujqf51wOoy8DAAlg.QXwMDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved navigating to the /tmp directory using cd first, then using the touch command to create two files pwn and college to get the flag.

```
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.TpSOPGOVKK
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.TpSOPGOVKK
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{osFXzXO3Gwkujqf51wOoy8DAAlg.QXwMDO0wyMwkjNzEzW}
```

## What I Learned

Making new files with touch is super simple. just a one-liner and done.

## References

None

## Removing files - Challenge 8    
### This challenge requires us to remove a file and then check it to get the flag.

**Flag:** `pwn.college{Mqon4hzhV-HW7FRaLMA5U98QAF0.QX2kDM1wyMwkjNzEzW}` 

The process of obtaining the flag involved checking the contents of the home directory and then using the rm command to delete the file.

```
hacker@commands~removing-files:~$ ls
a  delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Mqon4hzhV-HW7FRaLMA5U98QAF0.QX2kDM1wyMwkjNzEzW}
```

## What I Learned

Deleting stuff with rm is quick and easy, but you gotta be careful not to nuke the wrong thing cuz once its gone its gone xD

## References

None

## Moving Files - Challenge 9   
### This challenge requires us to move a specified file into a given location and then check to get the flag.

**Flag:** `pwn.college{IyOsKFvMPPRNXDwXR0UfNO9d99F.0VOxEzNxwyMwkjNzEzW}` 

The process of obtaining the flag involved moving a givewn file into a different one and then checking it to obtain a flag.

```
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{IyOsKFvMPPRNXDwXR0UfNO9d99F.0VOxEzNxwyMwkjNzEzW}
```

## What I Learned

Moving files around with mv is just like dragging and dropping, but in the terminal.

## References

None

## Hidden Files - Challenge 10   
### This challenge requires us to find the hidden flag file to get the flag.

**Flag:** `pwn.college{0RX0Iniq2nEY8GPdpVfaYyAvY6e.QXwUDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved finding the contents of / using ls -a / and catting the flag file.

```
hacker@commands~hidden-files:~$ ls -a /
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-18198591130948  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:~$ cat /.flag-18198591130948
pwn.college{0RX0Iniq2nEY8GPdpVfaYyAvY6e.QXwUDO0wyMwkjNzEzW}
```

## What I Learned

The flag wasn't in the current working directory so only using ls -a didnt help so hence had to use ls -a/  which scanned the root directory for the flag

## References

None

## An Epic filesystem Quest - Challenge 11   
### This challenge requires us to find the hidden flag file to get the flag.

**Flag:** `It is: pwn.college{Yu_sH1tWRJJ_NAwAXa-8Sds98yU.QX5IDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved finding the contents of a hidden flag file using clues.

```
hacker@commands~an-epic-filesystem-quest:~$ ls /
NUGGET  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin     challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:~$ cat NUGGET
cat: NUGGET: No such file or directory
hacker@commands~an-epic-filesystem-quest:~$ ls /
NUGGET  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin     challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:~$ cat /NUGGET
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/traitlets/tests/pycache

The next clue is delayed --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:~$ cd /usr/local/lib/python3.8/dist-packages/traitlets/tests/pycache
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/traitlets/tests/__pycache__$ cat INSIGHT
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/arch/powerpc/platforms/8xx

The next clue is delayed --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/traitlets/tests/__pycache__$ cd /opt/linux/linux-5.4/arch/powerpc/platforms/8xx
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/powerpc/platforms/8xx$ ls -a
.        MEMO        cpm1.c        machine_check.c  mpc86xads_setup.c  mpc8xx.h  tqm8xx_setup.c
..       Makefile    ep88xc.c      micropatch.c     mpc885ads.h        pic.c
Kconfig  adder875.c  m8xx_setup.c  mpc86xads.h      mpc885ads_setup.c  pic.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/powerpc/platforms/8xx$ cat MEMO
Lucky listing!
The next clue is in: /usr/share/javascript/three/examples/jsm/nodes/inputs

The next clue is delayed --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/powerpc/platforms/8xx$ cd /usr/share/javascript/three
/examples/jsm/nodes/input
bash: cd: /usr/share/javascript/three/examples/jsm/nodes/input: No such file or directory
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/powerpc/platforms/8xx$ cd /usr/share/javascript/three/examples/jsm/nodes/inputs
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/three/examples/jsm/nodes/inputs$ ls -a
.               CubeTextureNode.d.ts  IntNode.js         PropertyNode.js     ScreenNode.js     Vector3Node.js
..              CubeTextureNode.js    Matrix3Node.d.ts   RTTNode.d.ts        TextureNode.d.ts  Vector4Node.d.ts
BoolNode.d.ts   FloatNode.d.ts        Matrix3Node.js     RTTNode.js          TextureNode.js    Vector4Node.js
BoolNode.js     FloatNode.js          Matrix4Node.d.ts   ReflectorNode.d.ts  Vector2Node.d.ts
ColorNode.d.ts  GIST                  Matrix4Node.js     ReflectorNode.js    Vector2Node.js
ColorNode.js    IntNode.d.ts          PropertyNode.d.ts  ScreenNode.d.ts     Vector3Node.d.ts
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/three/examples/jsm/nodes/inputs$ cat GIST
Tubular find!
The next clue is in: /opt/linux/linux-5.4/Documentation/networking/device_drivers/stmicro
Watch out! The next clue is trapped. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/three/examples/jsm/nodes/inputs$ cd ~
hacker@commands~an-epic-filesystem-quest:~$ ls -a /opt/linux/linux-5.4/Documentation/networking/device_drivers/stmicro
.  ..  MESSAGE-TRAPPED  stmmac.txt
hacker@commands~an-epic-filesystem-quest:~$ cat ls -a /opt/linux/linux-5.4/Documentation/networking/device_drivers/stmicro/MESSAGE-TRAPPED
cat: invalid option -- 'a'
Try 'cat --help' for more information.
hacker@commands~an-epic-filesystem-quest:~$ cat ls -a /opt/linux/linux-5.4/Documentation/networking/device_drivers/stmicro/MESSAGE-TRAPPED
cat: invalid option -- 'a'
Try 'cat --help' for more information.
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/linux/linux-5.4/Documentation/networking/device_drivers/stmicro/MESSAGE-TRAPPED
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/arch/m68k/apollo

The next clue is hidden --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:~$ cd /opt/linux/linux-5.4/arch/m68k/apollo
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/m68k/apollo$ ls -a
.  ..  .WHISPER  Makefile  config.c  dn_ints.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/m68k/apollo$ cat .WHISPER
Congratulations, you found the clue!
The next clue is in: /opt/linux/linux-5.4/tools/memory-model/litmus-tests

Watch out! The next clue is trapped. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/m68k/apollo$ cd ~
hacker@commands~an-epic-filesystem-quest:~$ ls -a /opt/linux/linux-5.4/tools/memory-model/litmus-tests
.                                                         MP+polockonce+poacquiresilsil.litmus
..                                                        MP+polocks.litmus
.gitignore                                                MP+poonceonces.litmus
CLUE-TRAPPED                                              MP+pooncerelease+poacquireonce.litmus
CoRR+poonceonce+Once.litmus                               MP+porevlocks.litmus
CoRW+poonceonce+Once.litmus                               R+fencembonceonces.litmus
CoWR+poonceonce+Once.litmus                               R+poonceonces.litmus
CoWW+poonceonce.litmus                                    README
IRIW+fencembonceonces+OnceOnce.litmus                     S+fencewmbonceonce+poacquireonce.litmus
IRIW+poonceonces+OnceOnce.litmus                          S+poonceonces.litmus
ISA2+pooncelock+pooncelock+pombonce.litmus                SB+fencembonceonces.litmus
ISA2+poonceonces.litmus                                   SB+poonceonces.litmus
ISA2+pooncerelease+poacquirerelease+poacquireonce.litmus  SB+rfionceonce-poonceonces.litmus
LB+fencembonceonce+ctrlonceonce.litmus                    WRC+poonceonces+Once.litmus
LB+poacquireonce+pooncerelease.litmus                     WRC+pooncerelease+fencermbonceonce+Once.litmus
LB+poonceonces.litmus                                     Z6.0+pooncelock+poonceLock+pombonce.litmus
MP+fencewmbonceonce+fencermbonceonce.litmus               Z6.0+pooncelock+pooncelock+pombonce.litmus
MP+onceassign+derefonce.litmus                            Z6.0+pooncerelease+poacquirerelease+fencembonceonce.litmus
MP+polockmbonce+poacquiresilsil.litmus
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/linux/linux-5.4/tools/memory-model/litmus-tests/CLUE-TRAPPED
Yahaha, you found me!
The next clue is in: /usr/share/libtool
hacker@commands~an-epic-filesystem-quest:~$ ls -a /usr/share/libtool
.  ..  BRIEF  build-aux
hacker@commands~an-epic-filesystem-quest:~$ cat /usr/share/libtool/BRIEF
Congratulations, you found the clue!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/DoubleStruck
hacker@commands~an-epic-filesystem-quest:~$ ls -a /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/DoubleStruck
.  ..  ALERT  Bold  BoldItalic  Italic  Regular
hacker@commands~an-epic-filesystem-quest:~$ cat /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/DoubleStruck/ALERT
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{Yu_sH1tWRJJ_NAwAXa-8Sds98yU.QX5IDO0wyMwkjNzEzW}
```

## What I Learned

This one really made me use ls, ls -a, and cd together—and yeah, patience is key :)

## References

None

## Making Directories - Challenge 12   
### This challenge requires us to make a directory and create a file in it to get the flag.

**Flag:** `pwn.college{A2IztdX-Ta6uhz9EaLzyiTECt6l.QXxMDO0wyMwkjNzEzW}` 

The process of obtaining the flag involved making a directory inside /tmp and making a file in it.

```
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  tmp.TpSOPGOVKK
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ ls
college
hacker@commands~making-directories:/tmp/pwn$ cd ~
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
pwn.college{A2IztdX-Ta6uhz9EaLzyiTECt6l.QXxMDO0wyMwkjNzEzW}
```

## What I Learned

Making folders with mkdir is fast. Just type it and done.

## References

None

## Finding Files - Challenge 13   
### This challenge requires us to find a flag file.

**Flag:** `pwn.college{oRK52BeoaruqwkMuowVRMdMHdTF.QXyMDO0wyMwkjNzEzW}` 

The process of obtaining the flag using the command find /- name flag.

```
hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/doc/libxrandr2/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /usr/share/doc/libxrandr2/flag
pwn.college{oRK52BeoaruqwkMuowVRMdMHdTF.QXyMDO0wyMwkjNzEzW}

```

## What I Learned

I learned how to find files with find. Also, don’t cat a directory, it gets messy fast.

## References

None

## Linking Files - Challenge 14   
### This challenge requires us symbolic link files and trick a file into giving us the flag.

**Flag:** `pwn.college{82TKZrr-4TanmGKQ8RWhPVMVRX-.QX5ETN1wyMwkjNzEzW}` 

The process of obtaining the flag using ls -l and linking the file to flag.

```
hacker@commands~linking-files:~$ ls -l /challenge/catflag
-rwsr-xr-x 1 root root 123 Jan 14  2025 /challenge/catflag
hacker@commands~linking-files:~$ ls -l /home/hacker/not-the-flag
ls: cannot access '/home/hacker/not-the-flag': No such file or directory
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ ls -l /home/hacker/not-the-flag
lrwxrwxrwx 1 hacker hacker 5 Sep 26 20:15 /home/hacker/not-the-flag -> /flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{82TKZrr-4TanmGKQ8RWhPVMVRX-.QX5ETN1wyMwkjNzEzW}
```

## What I Learned

Symbolic links are like shortcuts which are super useful for tricking programs into reading stuff they normally can’t.

## References

None