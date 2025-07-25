
### Listing Processes 

Anyways! Let's practice. In this level, I have once again renamed `/challenge/run` to a random filename, and this time made it so that you cannot `ls` the `/challenge` directory! But I also launched it, so you can find it in the running process list, figure out the filename, and relaunch it directly for the flag! Good luck!

Commands used: 
`ps -ef`
`/challenge/<the run filename>`

flag: `pwn.college{46NmO0UrBQJf9nsDGqO_yncPMNK.QX4MDO0wyNwkzNyEzW}`

### Killing Processes 

Now, it's time to terminate your first process! In this challenge, `/challenge/run` will refuse to run while `/challenge/dont_run` is running! You must find the `dont_run` process and `kill` it. If you fail, `pwn.college` will disavow all knowledge of your mission. Good luck.

Command used: 
`ps -ef`
`kill 128`

flag: `pwn.college{AJ66-q1fb_D4qZJzN4kCgZrpuFq.QXyQDO0wyNwkzNyEzW}`

### Interrupting Processes 

Try it here! `/challenge/run` will refuse to give you the flag until you interrupt it. Good luck!

Command used: `Ctrl-C`

flag: `pwn.college{wx6w0olqFairv8yQYVk4ZQ9yb5L.QXzQDO0wyNwkzNyEzW}`

### Suspending Processes

This level's `run` wants to see another copy of itself running _and using the same terminal_. How? Use the terminal to launch it, then suspend it, then launch another copy while the first is suspended!

Commands used: 
`/challenge/run`
`Ctrl-Z`
`/challenge/run`


flag: `pwn.college{ERp1c9-k62BeVLKphALYa_XzG9w.QX1QDO0wyNwkzNyEzW}`

### Resuming Processes

Go try it out! This challenge's `run` needs you to suspend it, then resume it. Good luck!

Commands used: `/challenge/run`
`Ctrl-Z`
`fg`

flag: `pwn.college{wVRZ_bmZxkjwn1gSujamd2Wd8XM.QX2QDO0wyNwkzNyEzW}`

### Backgrounding Processes 

This level's `run` wants to see another copy of itself running, _not suspended_, and using the same terminal. How? Use the terminal to launch it, then suspend it, then _background_ it with `bg` and launch another copy while the first is running in the background!


Command used: 
`/challenge/run`
`bg`
`/challenge/run`

flag: `pwn.college{YB4h6cCdB94JsYjbtGVQmlhqun6.QX3QDO0wyNwkzNyEzW}`


### Foregrounding Processes

Imagine that you have a backgrounded process, and you want to mess with it some more. What do you do? Well, you can foreground a backgrounded process with `fg` just like you foreground a suspended process! This level will walk you through that!

Command used: 
`/challenge/run`
`bg`
`fg`

flag: `pwn.college{gFrcNgfkhZNWsqSzF0rokG-qY4a.QX4QDO0wyNwkzNyEzW}`


### Starting Backgrounded Processes

Here, `sleep` is actively running in the background, _not_ suspended. Now it's your turn to practice! Launch `/challenge/run` backgrounded for the flag!


Command used: 
`/challenge/run`
`/challenge/run &`

flag: `pwn.college{Y-aFF-j3MRXSOQ6hflqX467gR7o.QX5QDO0wyNwkzNyEzW}`

### Process Exit Codes 

In this challenge, you must retrieve the exit code returned by `/challenge/get-code` and then run `/challenge/submit-code` with that error code as an argument. Good luck!

Command used: 
`/challenge/get-code`
`echo $?`
`/challenge/submit-code 71`

flag: `pwn.college{E18yIX5D3ZGz6AePPB12B3QTGQN.QX5YDO1wyNwkzNyEzW}`
