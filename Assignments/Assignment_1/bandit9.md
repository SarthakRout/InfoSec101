# Bandit Level 9 to 10 Writeup

Author: [Harsh Jain](https://github.com/Harshj20) 

Problem Page: [bandit10](https://overthewire.org/wargames/bandit/bandit10.html)

## List of Commands Used
```
ls - list files in a directory
strings - print the sequences of printable characters in files
grep -  print lines that match patterns

```

## Walkthrough
How did you solve this level? Include the complete thought process, even stuff that didn't work. Give explanations wherever necessary.
First few steps were common - using *ssh* to connect to the remote machine and then doing *ls* to look for the file *data.txt*. 
Then I used cat command to see the content of the file. It was not readable. Now I went to the bandit page again where it had recommended some commands to clear this level.It was quite obvious that *strings* would be used to clear this level.I looked up its manpage.Now the password was preceded by several *=* characters. I knew *grep* would be useful as I had used in one of the previous level.

## Password
`truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`

## Bash/Python script to automate the process
```
#!/usr/bin/bash
sshpass -p UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR ssh bandit9@bandit.labs.overthewire.org -p 2220 << HI
strings data.txt | grep -E "==" | tail +4 | tr -d '=&'
exit
HI

```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
