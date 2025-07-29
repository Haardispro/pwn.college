
### Translating Characters

Now, you try it! In this level, `/challenge/run` will print the flag but will swap the casing of all characters (e.g., `A` will become `a` and vice-versa). Can you undo it with `tr` and get the flag?

Command used: 
`/challenge/run | tr 'A-Za-z 'a-zA-Z' `

flag: `pwn.college{wwmVTL4TJyi0Vs9fPPUA7p4Pm1C.01MxEzNxwyNwkzNyEzW}`


### Deleting Characters 

Pretty simple! Now you give it a try. I'll intersperse some decoy characters (specifically: `^` and `%`) among the flag characters. Use `tr -d` to remove them!

Command used: 
`/challenge/run | tr -d %^`

flag: `pwn.college{ArYqkQifCE4vBrmABN0v4pEXjR3.0FNxEzNxwyNwkzNyEzW}`

### Deleting Newlines

Now, let's combine this with deletion. In this challenge, we'll inject a bunch of newlines into the flag. Delete them with `tr`'s `-d` flag and the _escaped_ newline specification!

Command used: 
`/challenge/run | tr -d "\n" `

flag: `pwn.college{QSw0W9gQavZZBDmEIer4gQ0ivww.0VNxEzNxwyNwkzNyEzW}`

### Extracting the first lines with head 

This challenge's `/challenge/pwn` outputs a bunch of data, and you'll need to pipe it through `head` to grab just the first 7 lines and then pipe them onwards to `/challenge/college`, which will give you the flag if you do this right! Your solution will be a long composite command with _two_ pipes connecting three commands. Good luck!

Command used: 
`/challenge/pwn | head -n 7 | /challenge/college`

flag: `pwn.college{YVVMAZQ6yPDDrrTmhwj3QDU7JiF.0lNxEzNxwyNwkzNyEzW}`

### Extracting specific sections of text 

In this challenge, the `/challenge/run` program will give you a bunch of lines with random numbers and single characters (characters of the flag) as columns. Use `cut` to extract the flag characters, then pipe them to `tr -d "\n"` (like the previous level!) to join them together into a single line. Your solution will look something like `/challenge/run | cut ??? | tr ???`, with the `???` filled out.

Commands used: 
`/challenge/run | cut -d " " -f 2 | tr -d "\n"`

flag: `pwn.college{QGZ3wf8Pr-F-KZl1edeOjVAUC9C.01NxEzNxwyNwkzNyEzW}`


### Sorting Data

In this challenge, there's a file at `/challenge/flags.txt` containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be at the end (we made sure of this when generating fake flags). Go get it!

Command used: 
`sort /challenge/flags.txt`

flag: `pwn.college{oehM1AR1n_8ooliNMgu3-lqkes2.0FM0MDOxwyNwkzNyEzW}`



