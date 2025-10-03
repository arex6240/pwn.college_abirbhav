# Perceiving Permissions

## Changing File Ownership - Challenge 1
**Flag:** `pwn.college{g-8gX3iOLETV-1AOGG-MNr5CvwR.QXxEjN0wyMwkjNzEzW}  `

The process of obtaining the flag involved using `chown` to change the owner of a file.

```
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{g-8gX3iOLETV-1AOGG-MNr5CvwR.QXxEjN0wyMwkjNzEzW}
```

## What I Learned
I learned how to use `chown` to change the owner of a file. Here is changed the owner to hacker.

## References
None

---

## Groups and Files - Challenge 2
**Flag:** `pwn.college{4O6iXjaysJdzi9yNL5yA28frLlV.QXxcjM1wyMwkjNzEzW}`

The process of obtaining the flag involved using `chgrp` to change the group of a file.

```
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{4O6iXjaysJdzi9yNL5yA28frLlV.QXxcjM1wyMwkjNzEzW}
```

## What I Learned
I learned how to use `chgrp` to change the group ownership of a file. Linux has various types of group ownerships. by this command i changed the file   's group to hacker which is a group I am in.

## References
None

---

## Fun With Group Names - Challenge 3
**Flag:** `pwn.college{EF3CUbVVh3TYHQnQRxJlXa5FkBW.QXycjM1wyMwkjNzEzW}`

The process of obtaining the flag involved listing and understanding group names and their permissions.

```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp24360) groups=1000(grp24360)
hacker@permissions~fun-with-groups-names:~$ chgrp grp24360 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{EF3CUbVVh3TYHQnQRxJlXa5FkBW.QXycjM1wyMwkjNzEzW}
```

## What I Learned
I learned how to list and interpret group names for the current user. I used id command to indentify the correct random group name

## References
None

---

## Changing Permissions - Challenge 4
**Flag:** `pwn.college{YJe8G_8_mZryBXhTLrktQw7LLb_.QXzcjM1wyMwkjNzEzW}`

The process of obtaining the flag involved using `chmod` to change file permissions.

```
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{YJe8G_8_mZryBXhTLrktQw7LLb_.QXzcjM1wyMwkjNzEzW}
```

## What I Learned
I learned how to use `chmod` to set file permissions. I also learnt about the options of chmod which are u+r, as above, adds read access to the user's permissions
g+wx adds write and execute access to the group's permissions
o-w removes write access for other users
a-rwx removes all permissions for the user, group, and world

## References
None

---

## Executable Files - Challenge 5
**Flag:** `pwn.college{seV9hslzBB9fd2f9KFpK1iZLkI4.QXyEjN0wyMwkjNzEzW}`

The process of obtaining the flag involved making a file executable using `chmod +x`.

```
hacker@permissions~executable-files:~$ chmod o+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ chmod o+x /challenge
chmod: changing permissions of '/challenge': Operation not permitted
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-x 1 hacker hacker 32 Jan 14  2025 /challenge/run
hacker@permissions~executable-files:~$  /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ cp /challenge/run /tmp/run_copy
hacker@permissions~executable-files:~$ chmod +x /tmp/run_copy
hacker@permissions~executable-files:~$ /tmp/run_copy
You MUST invoke me via /challenge/run to solve this challenge.
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{seV9hslzBB9fd2f9KFpK1iZLkI4.QXyEjN0wyMwkjNzEzW}
```

## What I Learned
I learned how to make files executable with `chmod a+x`. I also learned that since Im the file’s owner, I needed to set the owner execute bit `(a+x)`, not just give execute to others (o+x), because Linux checks owner permissions first.

## References
GOOGLE GEMINI LLM

---

## Permission Tweaking Practice - Challenge 6
**Flag:** `pwn.college{wyryXoBe9NlsdPvG51QQvm7u4a-.QXwEjN0wyMwkjNzEzW}`

The process of obtaining the flag involved adjusting permissions to meet specific requirements.

```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ------r--
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=,g=,o=r /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": ------r--
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod 000 /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ----wx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=,g=wx,o=wx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": ----wx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --x-wx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=x,g=wx,o=wx /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": --x-wx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ----wx-w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=,g=wx,o=w /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": ----wx-w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -----x-w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=,g=x,o=w /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": -----x-w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u=,g=,o= /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{wyryXoBe9NlsdPvG51QQvm7u4a-.QXwEjN0wyMwkjNzEzW}
```

## What I Learned
I learned how to tweak file permissions for privacy and security.

## References
GOOGLE GEMINI LLM

---

## Permissions Setting Practice - Challenge 7
**Flag:** `pwn.college{8COOuLiVSxZn17AaGlqOUbqKwtM.QXzETO0wyMwkjNzEzW}`

The process of obtaining the flag involved setting permissions as specified in the challenge (like the previous challenge).

```
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx--x--x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=x,o=x /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -wx--x--x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxr-x-wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=rx,o=wx /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": rwxr-x-wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w-----wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=,o=wx /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": -w-----wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--rwxrwx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=rwx,o=rwx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": r--rwxrwx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-----rwx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=,o=rwx /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": r-----rwx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr-xrw-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=rx,o=rw /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": r-xr-xrw-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --xrw----
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rw,o= /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": --xrw----
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wxr-xr--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=rx,o=r /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u+r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{8COOuLiVSxZn17AaGlqOUbqKwtM.QXzETO0wyMwkjNzEzW}
```

## What I Learned
It is very similar to the previous challenge which involved changing permissions of a file for 8 times correctly consecutively...

## References
None

---

## The SUID Bit - Challenge 8
**Flag:** `pwn.college{QYgpltRP8h8LwhE_d-tFhvshkGS.QXzEjN0wyMwkjNzEzW}`

The process of obtaining the flag involved setting the SUID bit on a file using `chmod u+s`.

```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{QYgpltRP8h8LwhE_d-tFhvshkGS.QXzEjN0wyMwkjNzEzW}
root@permissions~the-suid-bit:~#
```

## What I Learned
I learned about the SUID bit and its effect on file execution privileges. By using chmod u+s on a program owned by root, I was able to execute it and gain a root shell

## References
None

