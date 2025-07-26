
### cat: not the pet, but the command! 

In this challenge, I will copy the flag to the `flag` file in your home directory (where your shell starts). Go read it with `cat`!

command used: `cat flag`

flag: `pwn.college{I_LyBtYW1PtXE5W6kncfhAf2Qh7.QXxcTN0wyNwkzNyEzW}`


### catting absolute paths

In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with `cat` at its absolute path: `/flag`.

command used: `cat /flag`

flag: `pwn.college{I8_7SEgYvrsVxyHX1Lsp2sraOKu.QX5ETO0wyNwkzNyEzW}`

### more catting practice 

In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with `cd`, so no `cat flag` for you. You must retrieve the flag by absolute path, wherever it is.

command used: `cat /usr/share/enchant-2/flag`

flag: `pwn.college{oofohlEVKeHHfDWYnYmiDOWCM3K.QXwITO0wyNwkzNyEzW}`

### grepping for a needle in a haystack 

In this challenge, I've put a hundred thousand lines of text into the `/challenge/data.txt` file. Grep it for the flag!


command used: `grep "pwn.college" /challenge/data.txt`

flag: `pwn.college{0kAvKt6TfY6bJ2sdhUWZ6_WOM7v.QX3EDO0wyNwkzNyEzW}`

### comparing files 

Now for your challenge! There are two files in `/challenge`:

- `/challenge/decoys_only.txt` contains 100 fake flags
- `/challenge/decoys_and_real.txt` contains all 100 fake flags plus the one real flag

Use `diff` to find what's different between these files and get your flag!

Command used: `diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt`

flag: `pwn.college{wfQuhx_K7hV1_L_qHPwxLGrNisH.01MwMDOxwyNwkzNyEzW}`


### listing files 

commands used: 
`cd /challenge`
`ls`
`./26548-renamed-run-6558`

flag: `pwn.college{YIhFRNQEAPrVx9aifKaYM8FA9JK.QX4IDO0wyNwkzNyEzW}`


### touching files

commands used: 
`touch /tmp/pwn`
`touch /tmp/college`
`/challenge/run`

flag: `pwn.college{I17M_ddJDAb82YaUSiBGn_pC-m2.QXwMDO0wyNwkzNyEzW}`

### removing files 

commands used: `rm delete_me`

flag: `pwn.college{silwOta-7CjrbXS_STyJjjVCjf2.QX2kDM1wyNwkzNyEzW}`


### moving files 

commands used: `mv /flag /tmp/hack-the-planet`


flag: `pwn.college{Ah3uy_hB0dfRQAGsy-aJVp42i62.0VOxEzNxwyNwkzNyEzW}`


### hidden files 

commands used: 
`cd /`
`ls -la`
`cat .flag-31368749318170`

flag: `pwn.college{gvDOZEs8efj52MNd2a9BfOsODDu.QXwUDO0wyNwkzNyEzW}`


### An Epic Filesystem Quest

flag: `pwn.college{UV4dbtuk7Y5TXPHMOOWh1aLGKE1.QX5IDO0wyNwkzNyEzW}`

### making directories 

commands used: 
`mkdir /tmp/pwn`
`cd /tmp/pwn`
`touch college`
`/challenge/run`

flag: `pwn.college{Q8rGOT0j74nwI49bHDy-IVTdwiY.QXxMDO0wyNwkzNyEzW}`


### finding files 

Now it's your turn. I've hidden the flag in a random directory on the filesystem. It's still called `flag`. Go find it!

Command used: `find / -name flag`

flag: `pwn.college{ck8hE6R9BoA3Z2-kYLNeVqDOKSB.QXyMDO0wyNwkzNyEzW}`


### linking files 

Okay, now you try it! In this level the flag is, as always, in `/flag`, but `/challenge/catflag` will instead read out `/home/hacker/not-the-flag`. Use the symlink, and fool it into giving you the flag!

Command used: 
`ln -s /flag /home/hacker/not-the-flag`
`/challenge/catflag`

flag: `pwn.college{YQLFN3_3SObpSUHQ4D0Y1bVSY4E.QX5ETN1wyNwkzNyEzW}`



