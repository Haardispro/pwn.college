
### Matching with *

Now, practice this yourself! Starting from your home directory, change your directory to `/challenge`, but use globbing to keep the argument you pass to `cd` to at most four characters! Once you're there, run `/challenge/run` for the flag!

Command used: 
`cd /ch*`
`/challenge/run`

flag: `pwn.college{YwT4dpamDPTSAT0uW3QPhxzbuNb.QXxIDO0wyNwkzNyEzW}`

### Matching with ? 

Now, practice this yourself! Starting from your home directory, change your directory to `/challenge`, but use the `?` character instead of `c` and `l` in the argument to `cd`! Once you're there, run `/challenge/run` for the flag!

Command used: 
`cd /?ha??enge`
`/challenge/run`

flag: `pwn.college{kk8hXZtux4rx5OFnCwGJYgO1Bs_.QXyIDO0wyNwkzNyEzW}`

### Matching with []

Try it here! We've placed a bunch of files in `/challenge/files`. Change your working directory to `/challenge/files` and run `/challenge/run` with a single argument that bracket-globs into `file_b`, `file_a`, `file_s`, and `file_h`!

Command used: 
`cd /challenge/files`
`/challenge/run file_[absh]`

flag: `pwn.college{sWUeqftHjA1Bvk0crR0WXRjOST4.QXzIDO0wyNwkzNyEzW}`

### Matching paths with []

Now it's your turn. Once more, we've placed a bunch of files in `/challenge/files`. Starting from your home directory, run `/challenge/run` with a single argument that bracket-globs into the absolute paths to the `file_b`, `file_a`, `file_s`, and `file_h` files!

Command used: 
`/challenge/run /challenge/files/file_[bash]`

flag: `pwn.college{Uy5McVz49ghlmx73DD_UaYHYahR.QX0IDO0wyNwkzNyEzW}`


### Multiple globs

Now you try it. We put a few happy, but diversely-named files in `/challenge/files`. Go `cd` there and run `/challenge/run`, providing a single argument: a short (3 characters or less) globbed word with two `*` globs in it that covers every word that contains the letter `p`.

Command used: 
`cd /challenge/files`
`/challenge/run *p*`

flag: `pwn.college{4iD7-ebp6IT5mILt7Wm9oXwP3oK.0lM3kjNxwyNwkzNyEzW}`

### Mixing globs 

Now, let's put the previous levels together! We put a few happy, but diversely-named files in `/challenge/files`. Go `cd` there and, using the globbing you've learned, write a single, short (6 characters or less) glob that (when passed as an argument to `/challenge/run`) will match the files "challenging", "educational", and "pwning"!




### Tab Completion 

This challenge has copied the flag into `/challenge/pwncollege`, and you can freely `cat` that file. But you can't type the filename: we used some serious trickery to make sure that you _must_ tab-complete it. Try it out!

Command used: `/challenge/pwn<tab>`

flag: `pwn.college{MkU0bYg9ImyUkcFTIQU7PVz5XwB.0FN0EzNxwyNwkzNyEzW}`


