# Bandit Level 10 to 11 Writeup



Author: [Kuldeep Singh Chouhan](https://github.com/kuldeep-singh-chouhan)

Problem Page: [bandit11](https://overthewire.org/wargames/bandit/bandit11.html)

## List of Commands Used

```
ls - list files in a directory
cat - view contain of a file
base64 - encoding and decoding for base64 encryption
```

## Walkthrough
This level asks us to decode a file which has a base64 encryption. It has a simple thought process to use the manual page of base64 `man base64`. The page shows to use -d for decoding an encoded data `base 64 -d file_name.txt`.

## Password
`IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

## Bash/Python script to automate the process
```
#!/bin/bash
sshpass -p truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk ssh bandit10@bandit.labs.overthewire.org -p 2220
cat data.txt
base64 -d data.txt
```

## Suggested modifications [Optional]
Double base64 encryption could be used or rot13 encryption could be used along with base64 encryption.
