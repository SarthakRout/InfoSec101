# Bandit Level 14 to 15 Writeup


Author: [Akash Biswas](https://github.com/akashkb-a01)

Problem Page: [bandit14](https://overthewire.org/wargames/bandit/bandit15.html)

## List of Commands Used
```
ssh  - OpenSSH SSH client (remote login program)
echo - display a line of text
nc   - arbitrary TCP and UDP connections and listens
exit - To close the connection to ssh server

```

## Walkthrough
First I tried to understand the function of each command given at the problem page. After that, I shortlisted telnet and nc and went through their man page. On the man page of nc towards the end just before EXAMPLES , I found "$ echo "QUIT" | nc host.example.com 20-30" and gave it a try by substituting appropriate information.

## Password
`BfMYroe26WYalil77FoDi9qh59eK5xNr`

## Bash/Python script to automate the process
```
#!/bin/expect -f
spawn ssh bandit14@bandit.labs.overthewire.org -p 2220
expect "password: "
send "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e\r"
expect "$ "
send "echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc localhost 30000\r"
expect "$ "
send "exit\r"

```
