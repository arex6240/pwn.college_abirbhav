# Terminal Multiplexing

## Launching Screen - Challenge 1
**Flag:** `pwn.college{ccNPsOC-EsBt3m6d8f5VsSfoozZ.0VN4IDOxwyMwkjNzEzW}`

The process of obtaining the flag involved launching GNU Screen.

```
hacker@tmux~launching-screen:~$ screen
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{ccNPsOC-EsBt3m6d8f5VsSfoozZ.0VN4IDOxwyMwkjNzEzW}
```

## What I Learned
I learned how to launch and use GNU Screen.

## References
None

---

## Detaching and Attaching - Challenge 2
**Flag:** `pwn.college{4D_v4yenhB3H9y73O9rVHaKq6WX.0lN4IDOxwyMwkjNzEzW}`

The process of obtaining the flag involved detaching and reattaching to a session.

```
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 139.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 139.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
[detached from 139.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{4D_v4yenhB3H9y73O9rVHaKq6WX.0lN4IDOxwyMwkjNzEzW}
Yes! Flag is: pwn.college{4D_v4yenhB3H9y73O9rVHaKq6WX.0lN4IDOxwyMwkjNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
```

## What I Learned
I learned how to detach and reattach to terminal sessions.

## References
None

---

## Finding Sessions - Challenge 3
**Flag:** `pwn.college{IqyHhYeDG-3qfq7O2WP708XAyG7.01N4IDOxwyMwkjNzEzW}`

The process of obtaining the flag involves finding an existing GNU Screen session.

```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
        139.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_b82cb4ba08cbe17a    (Detached)
        147.session_47fc3db48cdf8cf0    (Detached)
        150.session_bd40ca87906480c8    (Detached)
4 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r pts-0.terminal-multiplexing~detaching-and-attaching
There is a screen on:
        139.pts-0.terminal-multiplexing~detaching-and-attaching (Dead ???)
Remove dead screens with 'screen -wipe'.
There is no screen to be resumed matching pts-0.terminal-multiplexing~detaching-and-attaching.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r session_b82cb4ba08cbe17a

hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{IqyHhYeDG-3qfq7O2WP708XAyG7.01N4IDOxwyMwkjNzEzW}
pwn.college{IqyHhYeDG-3qfq7O2WP708XAyG7.01N4IDOxwyMwkjNzEzW}
hacker@terminal-multiplexing~finding-sessions:~$
```

## What I Learned
learnt to list active screen sessions with `screen -ls` and to reattach to a specific session with `screen -r <id>`.

## References
None

---

## Switching Windows - Challenge 4
**Flag:** `pwn.college{4pq3uzNi9VXvksuQkK5RxEm5oyL.0FO4IDOxwyMwkjNzEzW}`

The process of obtaining the flag involved switching windows in GNU Screen.

```
hacker@terminal-multiplexing~switching-windows:~$ screen -ls
There are screens on:
        139.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_b82cb4ba08cbe17a    (Remote or dead)
        147.session_47fc3db48cdf8cf0    (Remote or dead)
        150.session_bd40ca87906480c8    (Remote or dead)
        135.challenge_session   (Detached)
5 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~switching-windows:~$ screen -r
[detached from 135.challenge_session]

 cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
hacker@terminal-multiplexing~switching-windows:~$

hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{4pq3uzNi9VXvksuQkK5RxEm5oyL.0FO4IDOxwyMwkjNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{4pq3uzNi9VXvksuQkK5RxEm5oyL.0FO4IDOxwyMwkjNzEzW}
hacker@terminal-multiplexing~switching-windows:~$
```

## What I Learned
How to navigate between windows in Screen using key bindings.

## References
None

---

## Detaching and Attaching (tmux) - Challenge 5
**Flag:** `pwn.college{MWcN9B0m2eCA0K5TvqpATIF9bAZ.0VO4IDOxwyMwkjNzEzW}`

The process of obtaining the flag involved using tmux to detach and reattach to a session.

```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux attach
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{MWcN9B0m2eCA0K5TvqpATIF9bAZ.0VO4IDOxwyMwkjNzEzW}
Congratulations, here is your flag: pwn.college{MWcN9B0m2eCA0K5TvqpATIF9bAZ.0VO4IDOxwyMwkjNzEzW}
```

## What I Learned
learnt to start tmux and detach with Ctrl-b d and to list tmux sessions with tmux ls and reattach with tmux attach.

## References
None

---

## Switching Windows (tmux) - Challenge 6
**Flag:** `pwn.college{cm0H83CqK8tGM0Os7qdja0AahnC.0FM5IDOxwyMwkjNzEzW}`

The process of obtaining the flag involved switching windows inside tmux.

```
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux attach
 cat <<MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Welcome to the tmux window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-B 0 to switch to window 0!
> MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!

hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{cm0H83CqK8tGM0Os7qdja0AahnC.0FM5IDOxwyMwkjNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{cm0H83CqK8tGM0Os7qdja0AahnC.0FM5IDOxwyMwkjNzEzW}
hacker@terminal-multiplexing~switching-windows-tmux:~$
```

## What I Learned
How to navigate between tmux windows with Ctrl-b and num key like 0,1,2...

## References
None
