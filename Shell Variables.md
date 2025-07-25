
### Printing variables 

Now it's your turn. Have your shell print out the `FLAG` variable and solve this challenge!

Command used: `echo $PATH`

flag: `pwn.college{IbZmvcG9ST0kYXrBV4PDZDMXy6s.QX3UTN0wyNwkzNyEzW}`

### Setting Variables

To solve this level, you must set the `PWN` variable to the value `COLLEGE`. Be careful: both the names and values of variables are case-sensitive! `PWN` is not the same as `pwn` and `COLLEGE` is not the same as `College`.

Command used: `PWN=COLLEGE`

flag: `pwn.college{Mvvjw6TQQLmea4Husghsf32w-M0.QX5UTN0wyNwkzNyEzW}`

### Multi-word Variables

Here, the shell reads `1337 SAUCE` as a single token, and happily sets that value to `VAR`. In this level, you'll need to set the variable `PWN` to `COLLEGE YEAH`. Good luck!

Command used: `PWN="COLLEGE YEAH"`

flag: `pwn.college{k4CZbQKDuzndPsYcEJJdI8I733a.QXwYTN0wyNwkzNyEzW}`

### Exporting Variables

In this challenge, you must invoke `/challenge/run` with the `PWN` variable exported and set to the value `COLLEGE`, and the `COLLEGE` variable set to the value `PWN` but _not_ exported (e.g., not inherited by `/challenge/run`). Good luck!

Command used: 
`export PWN=COLLEGE`
`COLLEGE=PWN`
`/challenge/run PWN`

flag: `pwn.college{MweJYWjQxXfDwM0UqFEt72lk1Op.QXyYTN0wyNwkzNyEzW}`

### Printing Exported Variables

Try the `env` command: it'll print out every _exported_ variable set in your shell, and you can look through that output to find the `FLAG` variable!

Command used: `env | grep "FLAG"`

flag: `pwn.college{sTklTp7hLyBWx-lBW0lRSnaBxRO.QX4UTN0wyNwkzNyEzW}`

### Storing Command Output

Neat! Now, you practice. Read the output of the `/challenge/run` command directly into a variable called `PWN`, and it will contain the flag!

Command used: `PWN=$(/challenge/run)`
`echo $PWN`

flag: `pwn.college{IUt3I7viJoRjJKGtbzBii4ovNk6.QX1cDN1wyNwkzNyEzW}`


### Reading Input

In this challenge, your job is to use `read` to set the `PWN` variable to the value `COLLEGE`. Good luck!

command used: 
`read PWN`
`INPUT: COLLEGE`

flag: `pwn.college{0tGjUisYBQ0gOv_gQd0ycetVFFZ.QX4cTN0wyNwkzNyEzW}`

### Reading files 

What happened there? The example redirects `some_file` into the _standard input_ of `read`, and so when `read` reads into `VAR`, it reads from the file! Now, use that to read `/challenge/read_me` into the `PWN` environment variable, and we'll give you the flag! The `/challenge/read_me` will keep changing, so you'll need to read it right into the `PWN` variable with one command!

Command used: 
`read PWN < /challenge/read_me`

flag: `pwn.college{oQXHL4kXn_YGjt5p1AAzcIqtfzG.QXwIDO0wyNwkzNyEzW}`

