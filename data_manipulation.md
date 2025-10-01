# Data Manipulation

## Translating Characters - Challenge 1
**Flag:** `pwn.college{Qw9M8sYSHSXoEr8vWZcCJR2FVD3.01MxEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `tr` to translate characters.

```
hacker@data~translating-characters:~$ /challenge/run | tr 'a-zA-Z' 'A-Za-z'
yOUR CASE-SWAPPED FLAG:
pwn.college{Qw9M8sYSHSXoEr8vWZcCJR2FVD3.01MxEzNxwyMwkjNzEzW}
```

## What I Learned
I learned that the `tr` command can translate multiple characters at once by mapping one set to another. Here I used the character ranges a-z and A-Z.

## References
GOOGLE GEMINI

---

## Deleting Characters - Challenge 2
**Flag:** `pwn.college{8aXasfrjNSOlT_w99MnFd3qcJ96.0FNxEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `tr -d` to delete characters.

```
hacker@data~deleting-characters:~$ /challenge/run | tr -d '^%'
Your character-stuffed flag:
pwn.college{8aXasfrjNSOlT_w99MnFd3qcJ96.0FNxEzNxwyMwkjNzEzW}
```

## What I Learned
I learned that the `tr` command can also be used for deleting characters.  I can use quotes and input a list of characters that I want to be deleted.

## References
None

---

## Deleting Newlines - Challenge 3
**Flag:** `pwn.college{w5Fe20sIiqbYXp2pv4VOske7VPV.0VNxEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `tr -d '\n'`.

```
hacker@data~deleting-newlines:~$ /challenge/run | tr -d '\n'
Your line-split flag: pwn.college{w5Fe20sIiqbYXp2pv4VOske7VPV.0VNxEzNxwyMwkjNzEzW}hacker@data~deleting-newlines:~$
```

## What I Learned
I learned how to delete newlines from output.

## References
None

---

## Extracting the First Lines with head - Challenge 4
**Flag:** `pwn.college{o-4v9ygwa3AlhTvZYFempdEbdBo.0lNxEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `head`.

```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{o-4v9ygwa3AlhTvZYFempdEbdBo.0lNxEzNxwyMwkjNzEzW}
```

## What I Learned
I learned how to use `head` to extract first n lines from files. Then here I also piped that output from head to /challenge/college to receive the flag

## References
None

---

## Extracting Specific Sections of Text - Challenge 5
**Flag:** `pwn.college{c2wog8PQBUob9pYIcNa4A-ezfUV.01NxEzNxwyMwkjNzEzW}`

The process of obtaining the flag involved using `cut`.

```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d ' ' -f 2
p
w
n
.
c
o
l
l
e
g
e
{
c
2
w
o
g
8
P
Q
B
U
o
b
9
p
Y
I
c
N
a
4
A
-
e
z
f
U
V
.
0
1
N
x
E
z
N
x
w
y
M
w
k
j
N
z
E
z
W
}
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d ' ' -f 2 | tr -d '\n'
pwn.college{c2wog8PQBUob9pYIcNa4A-ezfUV.01NxEzNxwyMwkjNzEzW}hacker@data~extracting-specific-sections-of-text:~$
```

## What I Learned
I learned how to use the cut command to extract specific columns of data. By specifying -d and a field number with -f, I can isolate just the data I need. I also forgot to use the tr -d to delete the newline characters at first.

## References
None

---

## Sorting Data - Challenge 6
**Flag:** `pwn.college{Q-5NjsuXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using `sort`.

```
hacker@data~sorting-data:~$ sort /challenge/flags.txt -r
pwn.college{Q-5NjsuXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.college{Q-5NjsuXOq6uorlP-7hSxf8LPFF.0FM0LDOxwyMwkjNzEzW}
pwn.college{Q-5NjsuXOq6uorlP-6hTxf8LPFF.0FM0MCOxwyMwkjNyEzW}
pwn.college{Q-5NjsuXOq6uorlP-6gTxf8LPFF.0FM0MDOxwyMwkjNzDzW}
pwn.college{Q-5NjsuXOq6uorkP-7hTxf8LPFF.0FM0MDOxvyMwkjNzEzW}
pwn.college{Q-5NjsuXOp6torlO-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzV}
pwn.college{Q-5NjsuXNq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.college{Q-5NjsuXNq5tnqlP-7hTxf7LPFF.0FL0LDOxwyMwkjNzEzW}
pwn.college{Q-5NjstXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.college{Q-5NjstXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyLwkjNzEzW}
pwn.college{Q-5NjstXOq6uorlP-6hSxf8LOFF.0FL0MDOwwyMwkjNzEyW}
pwn.college{Q-5NjrtXOq6uorkP-7hTwf8LPEF.0FM0MCOxwyLwkjNyEzW}
pwn.college{Q-4NisuXOq6uorlP-7hTxf8LPFF.0FM0LDOxvyMwkiNzEyW}
pwn.college{Q-4NisuXOq6unrlP-7gTxf8LPEF.0FM0MDOxwyMwkiNzEzW}
pwn.college{P-5NjsuXOq5torlP-7hSxf8KPFF.0FM0MCOxwyMwjjMzEzW}
pwn.college{P-5NjsuWOq6unrlP-7hTxe8LPFF.0FM0MDOxwxMvkjNzEzW}
pwn.collegd{Q-5NjstWNq6uorlP-7hTxf8LPFF.0FM0MDOxwxMwkjNyEzW}
pwn.collegd{Q-5NjruXNq5uorlO-6hTxf8LOFF.0FM0MDOxwxMwjjNzDzW}
pwn.collegd{Q-5MjrtXNq5uorlP-7hSxf7LPFF.0FM0MDNxwyMwkiMzEzW}
pwn.collegd{Q-5MjrtWNp6torlO-7hTxf7KPFE.0EM0MDOxwyMvkjMzDzV}
pwn.collegd{Q-4NjstXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.collegd{P-5NjsuWOp5uoqlO-7hSxf7KPFF.0EM0LDOxwxMwjjNzDzW}
pwn.collefe{Q-5NjsuXNq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.collefe{Q-5MjsuXOq6uoqlP-7hTxf8LPFF.0FM0MDOwwyMwkjNzEzW}
pwn.collefd{Q-4NisuWOp6uorlP-7hTxe8LPEF.0FM0MCNxwyMwkjMzEyW}
pwn.colldge{Q-5NjsuWOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.colldgd{Q-5NjsuXOq6uorlP-7gTwf8LPFF.0FL0MDOxvyMwkjNzEzW}
pwn.colldfe{Q-5NjruXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwn.colldfe{Q-4NjsuXOq6uoqlP-7hTxf8LPFF.0FM0LDOxwyMwkjNyEzW}
pwn.colkege{Q-5NjsuXOq6uorlP-7hTxf8KPFF.0FM0MDOxwyMwkjNzEzW}
pwn.colkege{Q-5NisuXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEyW}
pwn.colkegd{Q-4NisuXOq6uorlP-7hTxf8LPFE.0FM0MDOxwyLwkjNyEzW}
pwn.colkefe{P-5MjstWOq5uorlP-7hSwe8KPEF.0FL0LCNwvxMwkjNzEzV}
pwn.coklege{Q-5MjsuXOq6uorlP-7hTxf8KPFF.0FM0MDOxvyLwkjNzEzW}
pwn.cnllege{Q-5NjsuWOq6uoqkP-7gSxf8LPFE.0FM0MDOxvyMvkjMzEzW}
pwn.cnllege{P-4NjsuXOq5torkP-7hSxf7LPFF.0FM0MDNxwxLvkiNzEzW}
pwn.cnllegd{Q-4NiruXNq5uorlP-7hTxf7KPFF.0FM0LDOxwxMwkiNzEyW}
pwn.cnllegd{P-5NjruXOq6tnrlP-6hTxf8LPEF.0EM0MDOxwyMwkjNzEzW}
pwn.cnllefe{Q-4NjrtXOq6uoqkP-7gSxf8KPFF.0FM0MCOxwyMwkjMyEzW}
pwn.cnllefd{Q-5MjstXOp5tnrkO-6gTxf7KPFF.0FL0MCNxwyMwkiMyEzV}
pwn.cnlkefd{Q-4NisuXNp6uorlP-7gTwe7LOEE.0EL0MDOxwyMvkjNzEzW}
pwn.cnlkdge{P-4NjruXOq5unrlP-7hTxf8KPEF.0FM0LDNxwxMwkjNzEyV}
pwn.cnklegd{P-4MjsuXOq6uorlO-6hTxf8LPFF.0FM0MCOxwyMwjjNzEzW}
pwn.cnklefd{Q-5NirtXNp6uoqlP-7gTwf8LPFF.0FM0MDOxvyMvkjMzEyW}
pwn.bollege{Q-5NjsuXOq6uorkP-7hTxf8LPFF.0FM0MDOxwyMvkjNyEzW}
pwn.bollege{Q-5NjsuXOp6uoqkP-7gSwf7KPFE.0FM0MDOwvyLvkiNzEzW}
pwn.bollege{Q-5NjsuWNp6tnrlP-7hSwe8KPEE.0FL0LDNxvyLwkjNzDzW}
pwn.bollege{Q-4NjsuXOq6uorlP-7hTxf8LPFF.0FM0MDOwwyMwkjNzEzW}
pwn.bollege{Q-4NjstXOp6unqlO-7hTwf8LPFF.0FL0MCOxwyMwkjNzEzW}
pwn.bolldfe{Q-5MjsuXOq6uorlP-6hTxf8LPEF.0FL0LDOxvxMvjjMzEzW}
pwn.bolkege{Q-5NjsuXOq6torlP-7hTxe8LPFF.0FM0MDOxwxMwkjMyEzW}
pwn.bolkdge{Q-5NisuXOp6tnrlP-7hTxf8LPEE.0FL0MDNwwyMwjjNzEzV}
pwn.bokkege{Q-5MjsuXOp6unrlP-6gTxe8LPFF.0FM0LDOxwyMwkjNzDzW}
pwn.bnlldge{Q-5NjsuXOq6uorlO-6hTxe8LOFF.0FM0LDOxvyMwjjNyDzW}
pwn.bnlldge{Q-5NjstWOq6torlP-7hTxf7KPFE.0FM0MDOxwyMvkjMzEzW}
pwn.bnklegd{Q-5NjsuXNp5uorkO-6hTxe8LOEF.0EL0MDNxwyLwkjNzEzW}
pwm.college{Q-5NjsuXOq6uorlP-6hTxf8LPFF.0FM0MDOxwyMwkjNzDzV}
pwm.college{Q-5NjstXOq6uorlP-7hTxf8LPFF.0FM0MDOxwyMwkjNzEzW}
pwm.college{P-5NjstXOq6unqlP-6hTxf7LPFF.0EM0LDOxwyLwkjNyEyW}
pwm.collefe{P-5NjsuXOq6uorlP-7hTxe7LPFF.0FL0LCOxwyMwjjMzEzV}
pwm.colldge{Q-5NjruXOq6uorlP-7hTxf8LPFF.0FM0LDOxwyMwkjNzEzV}
pwm.colkege{P-5NjsuXNq6uorlP-7hTxf8LOFF.0FM0MDOxwyMwkjNzEzW}
pwm.colkege{P-5NjstXNq6uorkP-6hSxe8LPEF.0EM0LCOwvxMwjiNzEzW}
pwm.colkege{P-4MjruXOp6uorlO-6hTwf8LOEF.0FM0LDOwwyMvkjNzEzW}
pwm.colkefe{Q-4NisuWOq6uorlP-7gSxf8KPFF.0FM0MDOxwyMwkjNyDzW}
pwm.colkdfe{P-5NisuXOq5uorkP-7gTxe8LPFF.0FM0MDOwwyMwkjNzDzV}
pwm.coklefe{Q-5NisuWOq5torkP-6gTxf8KPFF.0FL0MDOxwyMvkjNzEzV}
pwm.cnllege{Q-5NjsuXOq6uoqlP-7hTxf8LPFF.0EM0MDOwwyMvkjMzEzW}
pwm.cnllegd{Q-5NjruWNq6uorlO-7hTwf7LOEF.0FM0MDOxwyMwkjMzEzW}
pwm.bollege{Q-5NjsuWOq6uoqkO-6hTxf8LPFF.0FM0MDOwvyMwkiMzEzW}
pwm.bollegd{P-5NjsuXNp6uoqlP-6gTxf8LPEF.0EL0LDOxwyLwkiMzDzW}
pwm.bollefe{Q-5NjsuXOq6torkO-7hSwf7LPEE.0EM0MCNwwyLwkiMyEyV}
pvn.college{Q-5NjsuXOq6uoqlP-7hTxf8LPFF.0FM0MDNxwyMwkjNzEzW}
pvn.college{Q-5MjstXOp6torkP-7hTxe8LPFF.0FL0LDOxwyMwkjNzDzW}
pvn.collegd{Q-5MjsuXOp5unrlO-7gTxe7LPEF.0EM0MDOxvyMvjjNzEyV}
pvn.colkdfe{P-5NiruXNq6uorkP-6hTxf7LPFE.0FM0MDOwwxLwkiNzDzW}
pvn.coklegd{Q-5NjrtWOp6unrlP-7hSxf7LPEE.0FM0LDOxwyMwkiMzEzW}
pvn.coklegd{Q-5MjruWOq5uorlP-7hTxe8LPFF.0FM0MCOxwyMwjjMzEyW}
pvn.cokldge{P-4NjruXNq6uorkO-7hTwe8LPEE.0EM0LDNwwxMvkiNzEyV}
pvn.cokkdfe{Q-5NiruXNp6toqlP-6hTwf7LOEF.0FM0LDOwwyMwkjNzEyV}
pvn.bollefe{P-4NjsuXOp5tnrlO-7hTxf7LPEE.0FM0MDNwwyMwjjNzEzV}
pvn.bnlkege{Q-5MjsuWOq5torlP-7hTxf8LPEE.0EL0MCOxwyMwkjNzDyW}
pvn.bnklege{Q-4NirtXOq6tnrlP-7gTwe7LOEF.0FM0LDOwvyLvkjNzEyW}
pvm.college{P-4NirtXOq6unqkP-7hSwf8LPEE.0FM0MDOwwyMwjiNzDyW}
pvm.colldge{Q-4NjsuXOp6uorkP-6hTxe8LPFF.0FM0MDOxwyMwkiNzEzW}
pvm.coklege{Q-5NjsuXOq6uorlP-7gSxf7KOFE.0FM0MDNxwxLwkjNyEzV}
pvm.coklefe{P-5NjsuXNp6uorkP-6hSxe7LPEE.0FM0MCOwwyMwkiMzEzW}
pvm.cokkege{Q-5NjsuWOq6uorlP-7gTxf8LPEF.0FM0MDOxwyMvkjNzEzW}
pvm.cnllefe{P-4NiruXNq6uorlP-7hSxe8LPEE.0FL0MCOwwxMvkiMzEyW}
own.cokkege{Q-5NisuXOq6uorlP-7hTwf8LPFF.0FM0MDOxwyMwkjNyEzW}
own.cnlkegd{Q-5NjsuXNq6uorlP-7hTxf8LPFE.0FM0MDOxwyLwkjNzEzV}
own.bollege{Q-5NjruXOq6toqlP-7gSwf8LPFF.0EL0LDOwwyMwjiMzEzV}
own.bokldgd{P-5MistXOq5tnrlP-6hTxf7LPFF.0FL0MDOwwyMvkjNyEzV}
owm.college{P-5NjstXOq5torlO-6hSwf7KOFF.0FM0LDNxwyMwkjMzEzV}
owm.colldge{Q-5MjsuWOq5uorlP-7hTxf8LPFE.0FL0LDOwvyMwkiNzEzW}
owm.colldge{P-5MjrtXNq6unrlP-7hTxf8KPFF.0FM0MDNwwxLwjjMzEyW}
owm.colldgd{Q-5NjstWOp6unrkP-7hTwf7LOFE.0FM0LDNwvyLwkjNyEzW}
owm.cokkdgd{Q-4MisuWOp6uorkO-6gTwf7LPEF.0FM0MDOxvyMvkiNzEzV}
ovn.college{Q-4NjstXNp6uoqlO-7hSxe8LPFE.0FL0LDNxvyMwjiNzEzW}
ovn.boklege{Q-5MisuXOp5uorlP-7hSwf7KOFE.0FM0MDOwvxMwjjMzEyW}
ovm.cnllefe{Q-5NistXNq6unqlO-6hSwf8LPFF.0EM0MDOxwyLwjjNyEzV}
```

## What I Learned
I learned how to sort data in files. Here I used sort (location) -r to reverse the order so that the flag appears in the first (question says that the real flag is at the end).

## References
None
