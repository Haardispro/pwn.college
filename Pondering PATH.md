
### The PATH Variable

In this level, you will disrupt the operation of the `/challenge/run` program. This program will **DELETE** the flag file using the `rm` command. However, if it can't find the `rm` command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that `/challenge/run` also can't find the `rm` command!

Command used: 
`PATH=""`
`/challenge/run`

flag: `pwn.college{8NuDy-Srp8-9ndqVLF87fat04h0.QX2cDM1wyNwkzNyEzW}`

### Setting PATH 

This level's `/challenge/run` will run the `win` command via its bare name, but this command exists in the `/challenge/more_commands/` directory, which is not initially in the PATH. The `win` command is the _only_ thing that `/challenge/run` needs, so you can just overwrite `PATH` with that one directory. Good luck!


Command used: 
`export PATH=$PATH:/challenge/more_commands`
`/challenge/run`

flag: `pwn.college{YhFfJxQadk3g8fb7fGikLScTiNm.QX1cjM1wyNwkzNyEzW}`

### Finding Commands 

In this challenge, we added a `win` command somewhere in your `$PATH`, but it won't give you the flag. Instead, it's in the same directory as a `flag` file that we made readable by you! You must find `win` (with the `which` command), and `cat` the flag out of that directory!

Commands used: 
`which win`
`cd /challenge/paths/19500`
`cat flag`

flag: `pwn.college{ACHDGuUNrvums7psBlQRBowVQXD.01NzEzNxwyNwkzNyEzW}`

### Adding Commands 

Previously, the `win` command that `/challenge/run` executed was stored in `/challenge/more_commands`. This time, `win` does not exist! Recall the final level of [Chaining Commands](https://pwn.college/linux-luminarium/chaining), and make a shell script called `win`, add its location to the `PATH`, and enable `/challenge/run` to find it!





