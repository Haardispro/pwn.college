### Chaining with Semicolons

Give it a try now! In this level, you must run `/challenge/pwn` and then `/challenge/college`, chaining them with a semicolon.

Commands used: 
`/challenge/pwn ; /challenge/college`

flag: `pwn.college{oWTM4cWoYTs5G3qmB6h7AW0VRNb.QX1UDO0wyNwkzNyEzW}`

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




