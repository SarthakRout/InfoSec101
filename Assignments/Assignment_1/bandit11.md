# Bandit Level 11 to 12 Writeup


Author: [Ashutosh Sharma](https://github.com/asharma8602)

Problem Page: [bandit11](https://overthewire.org/bandit/bandit12)

## List of Commands Used
```
ls - list files in a directory
cat - concatenate files and print on the standard output
man - an interface to the on-line reference manuals
ssh — OpenSSH SSH client (remote login program) 
tr - translate or delete characters
```

## Walkthrough
The password was contained in a file named data.txt which was encrypted in by ROT13 algorithm , in which each small and upeer case alphabet is changed to 13th alphabet after it. So the translate(tr) command was the most appropirate for this task. From the man page and reading some examples through google, the sets for tr command had to be ranges in which each character will be lying and another will be range in which the given characters will be translated.

## Password
`5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

## Bash/Python script to automate the process
```
#!/usr/bin/expect -f
spawn ssh -p 2220 bandit11@bandit.labs.overthewire.org
expect "password: "
send "IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR\r"
expect "$ "
ls
man tr
cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
expect "$ "
send "exit\r"
```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.