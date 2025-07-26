
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

