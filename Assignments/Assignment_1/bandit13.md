# Bandit Level 13 to 14 Writeup

**Author:** [Parinay Chauhan](https://github.com/parinayc20/) 

**Problem Page:** [bandit13](https://overthewire.org/wargames/bandit/bandit14.html)

## List of Commands Used
```
ls      - list files in a directory
ssh     - enables secure connection to a ssh server on a remote machine
ssh -i  - enables connection using the private key
sshpass - enables authentication during ssh via single command
cad     - to view a given file
cd      - to navigate to a directory on the local system
```

## Walkthrough
In this level the first thing I encountered was how to establish a secure connection to a ssh server using the private key. The only file present in the bandit13 directory was the private key. By some searching on the internet I could find the ssh -i command and thus I could access the bandit14 server. From there I just followed the steps given and was able to retrieve the password.

## Password
`4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`

## Bash/Python script to automate the process
```
#!/bin/sh

sshpass -p "8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL" ssh  bandit13@bandit.labs.overthewire.org -p 2220 "ssh -y  -o StrictHostKeyChecking=no  -i sshkey.private bandit14@localhost "cat /etc/*/bandit14""
```
