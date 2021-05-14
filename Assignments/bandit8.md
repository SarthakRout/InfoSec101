# Bandit Level 8 to 9 Writeup


Author: [Keval Moliya](https://github.com/Keval-moliya)

Problem Page: [bandit8](https://overthewire.org/wargames/bandit/bandit9.html)

## List of Commands Used
```
ls - list files in a directory
sshpass - noninteractive ssh password provider
ssh - OpenSSH remote login client
sort - sort lines of text files
uniq - report or omit repeated lines
```

## Walkthrough
First I thought to use the `uniq -u` command to quickly find the unique line in the text file but turn out that it just checks the consecutive lines and finds the unique line among them, so then I had to sort the data in any order doesnt matter. I tried to store the output of sorted data in new file but we are not given the permission to create a new file so I piping to send the output from `sort` program to `uniq` program to find the uniqe line in data.txt file. 

## Password
`cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

## Bash/Python script to automate the process
```
#!/bin/bash

sshpass -p "cvX2JJa4CFALtqS87jk27qwqGhBM9plV" ssh bandit8@bandit.labs.overthewire.org -p 2220 'sort data.txt | uniq -u'
```