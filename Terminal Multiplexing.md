### Launching Screen 

For this challenge, we've hooked things up so that just launching screen will get you the flag. Easy!

Command used: `screen`

flag: `pwn.college{Mw-BTUqAHTcr6KQWyfHNNNGN76J.0VN4IDOxwyNwkzNyEzW}`


### Detaching and Attaching 

For this challenge, you'll need to:

1. Launch screen
2. Detach from it.
3. Run `/challenge/run` (this will secretly send the flag to your detached session!)
4. Reattach to see your prize

Commands used: 
`screen`
`CTRL + A, d`
`/challenge/run`
`screen -r`

flag: `pwn.college{wK54H6F1R4PfWZljyjD1hKjyxeC.0lN4IDOxwyNwkzNyEzW}`

### Finding Sessions 

In this challenge, we've created three screen sessions for you. One of them contains the flag. The other two are decoys!

Command used: `screen -ls`
`screen -r {session_name}`

flag: `pwn.college{8SsSAMp-ssAEC9Oln725cRXpICn.01N4IDOxwyNwkzNyEzW}`

### Switching Windows 

For this challenge, we've set up a screen session with two windows:

- Window 0 has a welcome message
- Window 1 has... well, you'll have to switch there to find out!

Attach to the session with `screen -r`, then use one of the key combinations above to switch to Window 1. Go get that flag!

Command used: 
`screen -r`
`Ctrl A 0`

flag: `pwn.college{obCuDd9u5MJUpqBCTnknQlprTmj.0FO4IDOxwyNwkzNyEzW}`

### Detaching and Attaching (tmux)

For this challenge:

1. Launch tmux
2. Detach from it.
3. Run `/challenge/run` (this will send the flag to your detached session!)
4. Reattach to see your prize

Command used: 
`tmux`
`Ctrl-B, then d`
`/challenge/run`

flag: `pwn.college{QsYp3jC7U6oeYoYftmBsVlZ8RlU.0VO4IDOxwyNwkzNyEzW}`

### Switching Windows(tmux)

We've created a tmux session with two windows:

- Window 1 has the flag!
- Window 0 has your warm welcome.

Go get that flag!

Command used: 
`Ctrl-B 1, then, Ctrl-B 0`

flag: `pwn.college{cMB7aQ53XEaQIecrb-jJz1qBtlj.0FM5IDOxwyNwkzNyEzW}`


