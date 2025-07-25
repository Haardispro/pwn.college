
### Changing File Ownership 

In this level, we will practice changing the owner of the `/flag` file to the `hacker` user, and then read the flag. For this challenge only, I made it so that you can use chown to your heart's content as the `hacker` user (again, typically, this requires you to be `root`). Use this power wisely and chown away!

Command used: 
`chown hacker /flag`
`cat /flag`

flag: `pwn.college{cPIcNd6c1p3Zt5zJLSWUiyjKz3l.QXxEjN0wyNwkzNyEzW}`

### Groups and Files

In this level, I have made the flag readable by whatever group owns it, but this group is currently `root`. Luckily, I have also made it possible for you to invoke `chgrp` as the `hacker` user! Change the group ownership of the flag file, and read the flag!

Command used: 
`chgrp hacker /flag`
`cat /flag`

flag: `pwn.college{QNDcOl_Uqroi2EEI2TfmZokfS-5.QXxcjM1wyNwkzNyEzW}`

### Fun With Groups Names

The point is, you've used `hacker` for the group before, but in this level, that is not going to work. I'll still allow you to use `chgrp`, but I have randomized the name of the group that your user is in. You will need to use the `id` command to figure that name out, then `chgrp` to victory!

Commands used: 
`id`
`chgrp grp24801 /flag`
`cat /flag`

flag: `pwn.college{s7vn16TUKOsy_A_rcIzU_Lr8k84.QXycjM1wyNwkzNyEzW}`

### Changing Permissions

In this challenge, you must change the permissions of the `/flag` file to read it! Typically, you need to have write access to the file in order to change its permissions, but I have made the `chmod` command all-powerful for this level, and you can `chmod` anything you want even though you are the `hacker` user. This is an ultimate power. The `/flag` file is owned by root, and you can't change that, but you can make it readable. Go and solve this!


Command used: 
`chmod +r /flag`
`cat /flag`

flag: `pwn.college{YhCDf2Adf-d443dpWu69F9KJDQa.QXzcjM1wyNwkzNyEzW}`

### Executable Files 

In this challenge, the `/challenge/run` program will give you the flag, but you must first make it executable! Remember your `chmod`, and get `/challenge/run` to tell you the flag!

Command used: 
`chmod +x /challenge/run`
`/challenge/run`

flag: `pwn.college{MtyhPCOqTQaaMu6BjdIB2o8mS5t.QXyEjN0wyNwkzNyEzW}`

### Permission Tweaking Practice

This challenge will ask you to change the permissions of the `/challenge/pwn` file in specific ways a few times in a row. If you get the permissions wrong, the game will reset and you can try again. If you get the permissions right eight times in a row, the challenge will let you `chmod` `/flag` to make it readable for yourself :-) Launch `/challenge/run` to get started!



### Permission Setting Practice 

### The SUID Bit