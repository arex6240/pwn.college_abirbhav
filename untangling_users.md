# Untangling Users

## Becoming root with su - Challenge 1
**Flag:** `pwn.college{MdsxNP_4V9auUrO-wCmWDVZexHT.QX1UDN1wyMwkjNzEzW}`

The process of obtaining the flag involved using `su` to switch to root.

```
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{MdsxNP_4V9auUrO-wCmWDVZexHT.QX1UDN1wyMwkjNzEzW}
root@users~becoming-root-with-su:/home/hacker#
```

## What I Learned
I learned how to use `su` to become root. then after that I used cat /flag to receive the flag

## References
None

---

## Other users with su - Challenge 2
**Flag:** `pwn.college{4oda-6xNCmv28LHdyaWmO0Idw7s.QX2UDN1wyMwkjNzEzW}`

The process of obtaining the flag involved using `su` to switch to another user.

```
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{4oda-6xNCmv28LHdyaWmO0Idw7s.QX2UDN1wyMwkjNzEzW}
```

## What I Learned
I learned how to use `su` to switch to user `zardus` from where I ran /challenge/run to receive the flag .

## References
None

---

## Cracking passwords - Challenge 3
**Flag:** `pwn.college{ES4AjfXtVW9qyg2qObXVPb8FhP-.QX3UDN1wyMwkjNzEzW}`

The process of obtaining the flag involved password cracking techniques.

```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:15 0% 2/3 0g/s 270.1p/s 270.1c/s 270.1C/s Alexis..bigred
aardvark         (zardus)
1g 0:00:00:21 100% 2/3 0.04705g/s 274.0p/s 274.0c/s 274.0C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{ES4AjfXtVW9qyg2qObXVPb8FhP-.QX3UDN1wyMwkjNzEzW}
```

## What I Learned
I learned about password cracking tools. Security of the `/etc/shadow` was exploited to obtain the password of the account `zardus`. 

## References
None

---

## Using sudo - Challenge 4
**Flag:** `pwn.college{AdJi3rLfiwJO8oDnLUAYWKdesn0.QX4UDN1wyMwkjNzEzW}`

The process of obtaining the flag involved using `sudo` for privilege escalation.

```
hacker@users~using-sudo:~$ sudo whoami
root
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{AdJi3rLfiwJO8oDnLUAYWKdesn0.QX4UDN1wyMwkjNzEzW}
```

## What I Learned
I learned how to use `sudo` for administrative tasks. sudo is more like a modern version of su. su needs password, but sudo by default runs task as root if you already have required permissions. used this to obtain the flag by running cat /flag

## References
None
