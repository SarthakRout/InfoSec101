# Bandit Level 13 to 14 Writeup

Author: [Ashutosh Sharma](https://github.com/asharma8602)

Problem Page: [bandit13](https://overthewire.org/bandit/bandit14)

## List of Commands Used

```
ls - list files in a directory
cat - concatenate files and print on the standard output
man - an interface to the on-line reference manuals
ssh — OpenSSH SSH client (remote login program)
ssh -i — Selects a file from which the identity (private key) for public key authentication is read
```

## Walkthrough

This level asks for a key which is stored in file which can be accessed by the user Bandit14. So for that first checked what file do we get in the bandit13 user , there was a rsa encrypted file having a private key to access the se bandit14 by local host , on the man page of ssh i saw how to use the ssh command and use the private key , by looking at he synopsis.

## Password

`4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`

## Bash/Python script to automate the process

```
#!/usr/bin/expect -f
spawn ssh -p 2220 bandit13@bandit.labs.overthewire.org
expect "password: "
send "8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL\r"
expect "$ "
ls
man ssh
ssh -i sshkey.private bandit14@localhost
cat /etc/bandit_pass/bandit14
expect "$ "
send "exit\r"
```

## Suggested modifications [Optional]

What can you do to make this level more difficult. The inherent idea should be similar.
