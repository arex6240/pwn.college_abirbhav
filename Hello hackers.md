
# Hello Hackers!

### Intro to commands - Challenge 1
### This challenge requires us to invoke a command on the terminal to receive the flag.

**Flag:** `pwn.college{koMlM09S0U_KTQSdjhNZf2G0MpQ.QX3YjM1wyMwkjNzEzW}` 

The process of obtaining the flag involved switching to SSH on the pwn.college challenge first, then connecting using SSH on the terminal and then invoking the 'hello' command in the terminal on wsl.

```
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{koMlM09S0U_KTQSdjhNZf2G0MpQ.QX3YjM1wyMwkjNzEzW}
```

## What I Learned

The challenge taught me on the process of connecting via ssh and starting the challenge and about how commands are processed and the steps that go behind it.

## References

None


## Intro to arguements - Challenge 2
### This challenge requires us to call an arguement along with 'hello' on the terminal to receive the flag.

**Flag:** `pwn.college{MdR1nIRqIQk1zs710_iR1JHiYyF.QX4YjM1wyMwkjNzEzW}` 

The process of obtaining the flag involved calling upon the 'hello' command with the respective arguement 'hackers'.

```
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{MdR1nIRqIQk1zs710_iR1JHiYyF.QX4YjM1wyMwkjNzEzW}
```

## What I Learned

The challenge taught me on how arguements are called and how they function.

## References

None

## Command History - Challenge 3
### This challenge requires us to scroll through our command history i.e the previous commands to find an inserted flag.

**Flag:** `pwn.college{UG0djoDoza4YpzuJejWTjPsrHZW.0lNzEzNxwyMwkjNzEzW}` 

The process of obtaining the flag involved scrolling up and down using the arrow keys to obtain an inserted flag.

```
hacker@hello~command-history:~$ the flag is pwn.college{UG0djoDoza4YpzuJejWTjPsrHZW.0lNzEzNxwyMwkjNzEzW}
```

## What I Learned

The challenge taught me where and how the history of the commands a user inputs is stored in the terminal and can be accessed.

## References

None
