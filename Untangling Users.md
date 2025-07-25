
### Becoming root with su 

But THIS challenge (and only this challenge) _does_ have a root password. That password is `hack-the-planet`, and you must provide it to `su` to become root! Go do that, and read the flag!

Commands used: 
`su`
`cd /`
`cat flag`

flag: `pwn.college{oDMDMrtR5ttdAazjju_cq6KIvFL.QX1UDN1wyNwkzNyEzW}`


### Other users with su 

Awesome! In this level, you must switch to the `zardus` user and then run `/challenge/run`. Zardus' password is `dont-hack-me`. Good luck!

Commands used: 
`su zardus`
`/challenge/run`

flag: `pwn.college{Iy9y65vhY2r4Sc3zC16OGRaC8qi.QX2UDN1wyNwkzNyEzW}`

### Cracking passwords

Commands used: 
`john /challenge/shadow-leak`
`su zardus`
`/challenge/run`

flag: `pwn.college{w6bohWtUKGA84nKbLzafkaIDC9O.QX3UDN1wyNwkzNyEzW}`

### Using sudo 

Commands used: 
`cd /`
`sudo cat flag`

flag: `pwn.college{QfI55yhBLdABlmG_h9yJtjl4Q7I.QX4UDN1wyNwkzNyEzW}`