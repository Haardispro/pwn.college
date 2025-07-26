
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

Command used: 
`/challenge/run [pce]*`

flag: `pwn.college{gqlpXLgXO2LFwk_v4w6HurAwczD.QX1IDO0wyNwkzNyEzW}`

### Exclusionary globbing 

Armed with this knowledge, go forth to `/challenge/files` and run `/challenge/run` with all files that don't start with `p`, `w`, or `n`!

Command used:
`cd /challenge/files`
`/challenge/run [!pwn]*`

flag: `pwn.college{AyV9b9rtyLE2FCtVnxaC3x5uqoS.QX2IDO0wyNwkzNyEzW}`

### Tab Completion 

This challenge has copied the flag into `/challenge/pwncollege`, and you can freely `cat` that file. But you can't type the filename: we used some serious trickery to make sure that you _must_ tab-complete it. Try it out!

Command used: `/challenge/pwn<tab>`

flag: `pwn.college{MkU0bYg9ImyUkcFTIQU7PVz5XwB.0FN0EzNxwyNwkzNyEzW}`


### Multiple options for tab completion 

This challenge has a `/challenge/files` directory with a bunch of files starting with `pwncollege`. Tab-complete from `/challenge/files/p` or so, and make your way to the flag!

Command used: 
`cat /challenge/files/p`
`cat /challenge/files/pwncollege-flag`

flag: `pwn.college{MSYRthZpcfG3--3Wkc6fX5JRhhz.0lN0EzNxwyNwkzNyEzW}`


### Tab completion on commands 

Tab completion is for more than files! You can also tab-complete commands. This level has a command that starts with `pwncollege`, and it'll give you the flag. Type `pwncollege` and hit the tab key to auto-complete it!

Command used: 
`pwncollege<TAB>`

flag: `pwn.college{U-3A6FaPcDdPFi1qZvrm1MC6eDC.0VN0EzNxwyNwkzNyEzW}`



