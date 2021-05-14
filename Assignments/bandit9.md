# Bandit Level 9 to 10 Writeup


Author: [Praveen Singh](https://github.com/GTA-VeteraN) 

Problem Page: [bandit9](https://overthewire.org/wargames/bandit/bandit10)

## List of Commands Used
```
ls - list files in a directory
ssh - OpenSSH remote login client
file - determine file type
strings - print the sequences of printable characters in files
grep - print lines that match patterns
cd - change directory
```

## Walkthrough
How did you solve this level? Include the complete thought process, even stuff that didn't work. Give explanations wherever necessary.

1. Login to the server using `ssh`.
2. Then I did `ls` (did this for almost all the levels) to list the file `data.txt`.
3. Then I did `cat data.txt` which printed down the content of the file.
4. After that I just scrolled down and got the password preceded by several `=` and copied it.
> Note : There were 4 patterns having several `=` followed by content but other three were `password`, `is` and `the*2i"4`.
5. But to do it more formally I did `grep == data.txt` but it showed `Binary file data.txt matches`.
6. Then I googled about `Binary file` and also did `file data.txt`.
> Note : Binary files contain compiled source code (or machine code) that are not human-readable and are executable.
7. Then I checked for all the commands listed on the page (bandit 9 --> 10) and got the `strings` command.
8. Then I did `strings data.txt` and got the list of strings, 4 of them clearly had the pattern and I got the password.
9. But I knew that I have to use `grep` in this level.
10. So lastly I used piping - `strings data.txt | grep ==` and got the password.
> Note : Piping is used for flow through 2 commands whereas redirection is used for flow into a file.


## Password
- For entry to __this level__ - `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`
- From __this level__ - `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`

## Bash/Python script to automate the process
After logging in to the server (No password automation).
``` 
#!/bin/bash
cd  
# If I had to run this script when I logged in to the server, then I have to create it inside the /tmp .
# So to return to the home directory I used cd.
ls 
file data.txt
strings data.txt | grep ==
```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.

- When I did `cat data.txt` then only I got the password. So the use of `grep` and `strings` were not really necessary.
### __Suggestion__
- Make the file very big and the password should be placed in between the file ( i.e neither at end nor at beginning).
