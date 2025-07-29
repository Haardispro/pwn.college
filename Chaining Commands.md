### Chaining with Semicolons

Give it a try now! In this level, you must run `/challenge/pwn` and then `/challenge/college`, chaining them with a semicolon.

Commands used: 
`/challenge/pwn ; /challenge/college`

flag: `pwn.college{oWTM4cWoYTs5G3qmB6h7AW0VRNb.QX1UDO0wyNwkzNyEzW}`


### Building on Success 


In this challenge, you need to chain the programs `/challenge/first-success` and `/challenge/second` using the `&&` operator. Try running each command separately first to see what happens (which is that you will _not_ get the flag). But if you chain them with `&&`, the flag will appear!

Command used:
`/challenge/first-success && /challenge/second`

flag: `pwn.college{sl6rM-iBNmbDSyQTBoCdgzdGowP.0lM0MDOxwyNwkzNyEzW}`

### Handling failure 

In this challenge, you need to chain `/challenge/first-failure` and `/challenge/second` using the `||` operator. Go for it!

Command used: 
`/challenge/first-failure || /challenge/second`

flag: `pwn.college{07Bf0-Vzf2TFYY7MBMZduJ5IIc3.01M0MDOxwyNwkzNyEzW}`

### Your First Shell Script 

Now, it's your turn! Same as last level, run `/challenge/pwn` and then `/challenge/college`, but this time in a shell script called `x.sh`, then run it with `bash`!

x.sh: 
```bash
/challenge/pwn ; /challenge/college 
```
Command used: 
`bash x.sh`

flag: `pwn.college{gO4oOARU3YVhsXU7t1MUKTSPDyC.QXxcDO0wyNwkzNyEzW}`

### Redirecting Script Output

In this level, we will practice piping (`|`) from your script to another program. Like before, you need to create a script that calls the `/challenge/pwn` command followed by the `/challenge/college` command, and pipe the output of the script into a single invocation of the `/challenge/solve` command!

Command used: `bash x.sh | /challenge/solve`
contents of x.sh are mentioned above 

flag: `pwn.college{YMMgsoosi3zCjCXkzqomESHxYWU.QX4ETO0wyNwkzNyEzW}`

### Executable Shell Scripts 

Try that here! Make a shell script that will invoke `/challenge/solve`, make it executable, and run it without explicitly invoking `bash`!

Command used: 
`chmod +x x.sh`
`./x.sh`

flag: `pwn.college{Ecc94E-4V6dPRwh-Id18EowMZsm.QX0cjM1wyNwkzNyEzW}`


### Understanding Shebangs

For this challenge, create a script at `/home/hacker/solve.sh` that has a proper shebang and outputs "hack the planet". Remember to make it executable, then run `/challenge/run` to verify your script works correctly!

solve.sh
```bash
#!/bin/bash
echo "hack the planet"
```
Command used: 
`chmod +x solve.sh`
`/challenge/run`

flag: `pwn.college{MnSNin5dCrWHTdtpr7zRh4qq45l.0VOzMDOxwyNwkzNyEzW}`
### Scripting with Arguments

Once your script works correctly, run `/challenge/run` to get your flag!

solve.sh 
```bash
echo "$2 $1"
```

Command used: 
`bash solve.sh pwn college`
`/challenge/run`

flag: `pwn.college{IgsOAwEmhqCCOiG7ZyvhFABiIsn.0VNzMDOxwyNwkzNyEzW}`

### Scripting with Conditionals

For this challenge, write a script at `/home/hacker/solve.sh` that:

- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output nothing

solve.sh
```bash
#!/bin/bash
if [ "$1" == "pwn"]
then 
	echo "college"
fi
```

flag: `pwn.college{Mjw6x--tcEiqMVP4WexNEjgc3nu.0lNzMDOxwyNwkzNyEzW}`

### Scripting with Default Cases 

For this challenge, write a script at `/home/hacker/solve.sh` that:

- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output "nope"

solve.sh
```bash
if [ "$1" == "pwn" ]
then 
	echo "college"
else
	echo "nope"
fi
```

flag: `pwn.college{g4R50nBfyD-rJWBMsQ4HbmT3gYA.01NzMDOxwyNwkzNyEzW}`

### Scripting with Multiple Conditions

For this challenge, write a script at `/home/hacker/solve.sh` that:

- Takes one argument
- If the argument is "hack", output "the planet"
- If the argument is "pwn", output "college"
- If the argument is "learn", output "linux"
- For any other input, output "unknown"

```bash
if [ "$1" == "hack" ]
then 
	echo "the planet"
elif [ "$1" == "pwn" ]
then
	echo "college"
elif [ "$1" == "learn" ]
then
	echo "linux"
else
	echo "unknown"
fi
```

flag: `pwn.college{wfITgZRgw5dE6mduydGTuyrd7Tw.0FOzMDOxwyNwkzNyEzW}`

