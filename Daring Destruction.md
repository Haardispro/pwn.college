### Fork Bomb

This challenge contains a `/challenge/check` that'll try to determine if your fork bomb is working (e.g., if it can't launch new processes) and give you the flag if so. Make sure to launch it (in a different terminal) _before_ launching your attack; otherwise you won't be able to launch it!

fork contains:
```bash
#!/bin/bash
:(){ :|:& };:
```

flag: `pwn.college{AUvJKuYf3E-BdcITvNFbR17YszP.0VMyEzNxwyNwkzNyEzW}`
### Disk-Space Doomsday 

This challenge forces you to fill the disk and then clean up. The process:

1. Fill your disk.
2. Run `/challenge/check`. It will attempt to create a 1 megabyte temporary file. If that fails, you pass the first stage and the checker will ask you to free the space.
3. Delete the file you made (with `rm`) to clear up the space.
4. Run `/challenge/check` a second time. If it can now create the temporary file (i.e., you successfully cleaned up your home directory), you’ll receive the flag.


Commands I used: 
1. `touch big_file.txt`
2. `yes > big_file.txt`
3. `/challenge/check`
4. `rm big_file.txt`
5. `/challenge/check`

flag: `pwn.college{QjxVGMeu80hmT4E9eC5wqqFRRT-.0lMyEzNxwyNwkzNyEzW}`

### rm -rf / 

In this challenge, you will do something that you might never do again: wipe the whole system. We've actually modified things a bit to keep your home directory safe (normally, it would get wiped as well!), but otherwise, all that stands before you and the flag is your willingness to wipe the drive. But before you wipe it all, make sure to start `/challenge/check` so that it can watch the fireworks (and give you the flag)!

What I did: 
I split terminal into two windows using `tmux`, ran `rm -rf / --no-preserve-root` in 1st window and second window I ran `/challenge/check`


flag: `pwn.college{IWUKZB38AlJU--tU64jBQ0AvRcj.0lMzEzNxwyNwkzNyEzW}`


### Life after rm -rf / 

This challenge will force you to try it. It's almost the same as the previous one, but you must read the flag yourself after you destroy the system. After you `rm` everything, your previously-launched `/challenge/check` will restore the `/flag` file and make it readable. Then you can `read` it!

What I did: 
I split terminal into two windows using `tmux`, ran `rm -rf / --no-preserve-root` in 1st window and second window I ran `/challenge/check`


I ran this script to find the contents of the `/flag`:
```bash
while read line; do
    echo "Line: $line"
done < /flag
```

flag: `pwn.college{IxtJhQeHp7qyHxQaCFAGuWr5GjZ.01MzEzNxwyNwkzNyEzW}`


### Finding meaning after rm -rf / 

Whatever route you use, find the randomly-named file that `/challenge/check` makes in `/` after you `rm`, read it, and get the flag!

What I did: 
I split terminal into two windows using `tmux`, ran `rm -rf / --no-preserve-root` in 1st window and second window I ran `/challenge/check`

Command used: 
`echo /*`

I ran this script to find the contents of the `/flag`:
```bash
while read line; do
    echo "Line: $line"
done < /aa93cccf
```



