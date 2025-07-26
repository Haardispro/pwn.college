
### Redirecting output

In this challenge, you must use this input redirection to write the word `PWN` (all uppercase) to the filename `COLLEGE` (all uppercase).

Command used: `echo PWN > COLLEGE`
flag: `pwn.college{kS4iVDX_k3I9n6h7LU6Qesoe9kB.QX0YTN0wyNwkzNyEzW}`

### Redirecting more output

Aside from redirecting the output of `echo`, you can, of course, redirect the output of any command. In this level, `/challenge/run` will once more give you a flag, but _only_ if you redirect its output to the file `myflag`. Your flag will, of course, end up in the `myflag` file!

Command used: 
`/challenge/run > myflag`
`cat myflag`

flag:` pwn.college{Em_m3acj763eg0xueV0umpcexcG.QX1YTN0wyNwkzNyEzW}`

### Appending output

To practice, run `/challenge/run` with an append-mode redirect of the output to the file `/home/hacker/the-flag`. The practice will write the first half of the flag to the file, and the second half to `stdout` if `stdout` is redirected to the file. If you properly redirect in append-mode, the second half will be appended to the first, but if you redirect in _truncation_ mode (`>`), the second half will _overwrite_ the first and you won't get the flag!

Command used: 
`/challenge/run >> /home/hacker/the-flag`

flag: `pwn.college{w2gdJ-YqFUUlRTav-AB4ZnSw4Eq.QX3ATO0wyNwkzNyEzW}`


### Redirecting errors 

Let's put this into practice! In this challenge, you will need to redirect the output of `/challenge/run`, like before, to `myflag`, and the "errors" (in our case, the instructions) to `instructions`. You'll notice that nothing will be printed to the terminal, because you have redirected everything! You can find the instructions/feedback in `instructions` and the flag in `myflag` when you successfully pull this off!

Command used: `/challenge/run > myflag 2> instructions`
`cat myflag`

flag: ` pwn.college{w-O3S3KGHoUlilCm5Po8m1L5I8W.QX3YTN0wyNwkzNyEzW}`

### Redirecting input

You can do interesting things with a lot of different programs using input redirection! In this level, we will practice using `/challenge/run`, which will require you to redirect the `PWN` file to it and have the `PWN` file contain the value `COLLEGE`! To write that value to the `PWN` file, recall the prior challenge on output redirection from `echo`!

Command used: `echo COLLEGE > PWN`
`/challenge/run < PWN`

### Grepping stored results 

In preparation for more complex levels, we want you to:

1. Redirect the output of `/challenge/run` to `/tmp/data.txt`.
2. This will result in a hundred thousand lines of text, with one of them being the flag, in `/tmp/data.txt`.
3. Grep that for the flag!

Command used: 
`/challenge/run > /tmp/data.txt`
`grep "pwn.college" /tmp/data.txt`

flag: `pwn.college{Izent-6oQewWy7W2fN_vrggo_Ts.QX4EDO0wyNwkzNyEzW}`

### Grepping live output

Now try it for yourself! `/challenge/run` will output a hundred thousand lines of text, including the flag. Grep for the flag!

Command used: 
`/challenge/run | grep pwn.college`

flag: `pwn.college{YWviX52d-6-qRO9zzQKc2UymGAK.QX5EDO0wyNwkzNyEzW}`

### Grepping Errors

Try it now! Like the last level, this level will overwhelm you with output, but this time on standard error. Grep through it to find the flag!

Command used: 
`/challenge/run 2>& 1 | grep "pwn.college"`

flag: `pwn.college{cBQnZD6sk8MqUyfJgLvtPcA9ECW.QX1ATO0wyNwkzNyEzW}`

### Filtering with grep -v

Sometimes, the only way to filter to just the data you want is to filter _out_ the data you _don't_ want. In this challenge, `/challenge/run` will output the flag to stdout, but it will also output over 1000 decoy flags (containing the word `DECOY` somehwere in the flag) mixed in with the real flag. You'll need to filter _out_ the decoys while keeping the real flag!

Command used: 
`/challenge/run | grep -v DECOY`

flag: `pwn.college{4cGJSAg0L8AXQFCXMkfLp_ja1Zk.0FOxEzNxwyNwkzNyEzW}`

### Duplicating piped data with tee 

Now, you try it! This process' `/challenge/pwn` must be piped into `/challenge/college`, but you'll need to intercept the data to see what `pwn` needs from you!

Command used: 
`/challenge/pwn | tee arg_file | /challenge/college`
`/challenge/pwn --secret 0Xdh62f | /challenge/college`

flag: `pwn.college{0Xdh62afV6NYri9w0bJ8zYDE--f.QXxITO0wyNwkzNyEzW}`


### Process substitution for input 

Now for your challenge! Recall what you learned in the `diff` challenge from [Comprehending Commands](https://pwn.college/linux-luminarium/commands). In that challenge, you diffed two files. Now, you'll diff two sets of command outputs: `/challenge/print_decoys`, which will print a bunch of decoy flags, and `/challenge/print_decoys_and_flag` which will print those same decoys plus the real flag.

Use process substitution with `diff` to compare the outputs of these two programs and find your flag!

Command used: 
`diff <(/challenge/print_decoys_and_flag) <(/challenge/print_decoys)`

flag: `pwn.college{UBAXiuf0WozDaZBvlS1XG4UTfqF.0lNwMDOxwyNwkzNyEzW}`

### Writing to multiple programs

Now it's your turn! In this challenge, we have `/challenge/hack`, `/challenge/the`, and `/challenge/planet`. Run the `/challenge/hack` command, and duplicate its output as input to both the `/challenge/the` and the `/challenge/planet` commands!

Command used: 
`/challenge/hack | tee>(/challenge/the) | /challenge/planet`


flag: `pwn.college{MDXODHO_l0mhoh2S0Og6stS8blk.QXwgDN1wyNwkzNyEzW}`


### Split-piping stderr and stdout 

In this challenge, you have:

- `/challenge/hack`: this produces data on _stdout_ and _stderr_
- `/challenge/the`: you must redirect `hack`'s _stderr_ to this program
- `/challenge/planet`: you must redirect `hack`'s _stdout_ to this program

Go get the flag!

Command used: `/challenge/hack 2> >(/challenge/the) > >(/challenge/planet)`

### Named pipes 

This challenge will be a simple introduction to FIFOs. You'll need to create a `/tmp/flag_fifo` file and redirect the stdout of `/challenge/run` to it. If you're successful, `/challenge/run` will write the flag into the fifo! Go do it!

Basically, operations on FIFOs will *block* until both the read side and the write side is open, so `/challenge/run` will not actually be launched until you start reading from the FIFO. 
So, simultaneously, `cat /tmp/flag_fifo` and `/challenge/run > /tmp/flag_fifo` need to be run. 

Command used: 
`mkfifo /tmp/flag_fifo`
`cat /tmp/flag_fifo &`<- & will put the cat command in the background
`/challenge/run > /tmp/flag_fifo`


flag: `pwn.college{ED2dL7wmKZw1oqjcxW_ICbCqcLo.01MzMDOxwyNwkzNyEzW}`