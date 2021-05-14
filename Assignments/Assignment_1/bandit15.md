# Bandit Level 15 to 16 Writeup


Author: [Praveen Singh](https://github.com/GTA-VeteraN) 

Problem Page: [bandit15](https://overthewire.org/wargames/bandit/bandit16)

## List of Commands Used
```
ssh - OpenSSH remote login client
openssl - OpenSSL command line tool for using the various cryptography functions of OpenSSL's crypto library from the shell.
s_client - implements a generic SSL/TLS client which connects to a remote host using SSL/TLS
cd - change directory

```

## Walkthrough
How did you solve this level? Include the complete thought process, even stuff that didn't work. Give explanations wherever necessary.

1. Login to the server using `ssh`.
2. In the previous level i used `netcat` command to send the password. So here also I did `nc localhost 30001` but nothing happened.
> Note : `Netcat` is a command-line utility that reads and writes data across network connections, using the TCP or UDP protocols.
3. Then I looked for `openssl` and `s_client`.
4. In the `man` page of `s_client` I got the syntax to connect to the port - `openssl s_client -connect host:port`.
5. I also googled it and got the same syntax.
6. The I used `openssl s_client -connect localhost:30001` and then sent the password of the previous level.
7. And I got the same thing given in the `Helpful Note: ` section on the problem page.
8. So I googled about `-ign_eof`.
> Note : `-ign_eof` - inhibit shutting down the connection when end of file is reached in the input by ignoring input eof.
9. And then I used `openssl s_client -connect localhost:30001 -ign_eof -quiet` and sent the password.
> Note : `-quiet` - inhibit printing of session and certificate information.
10. And I got the password.


## Password
- For entry to __this level__ - `BfMYroe26WYalil77FoDi9qh59eK5xNr`
- From __this level__ - `cluFn7wTiGryunymYOu4RcffSxQluehd`

## Bash/Python script to automate the process
After logging in to the server (No password automation).
``` 
#!/bin/bash
cd  
# If I had to run this script when I logged in to the server, then I have to create it inside the /tmp .
# So to return to the home directory I used cd.
openssl s_client -connect localhost:30001
# Then using -ign_eof for ignoring input eof
openssl s_client -connect localhost:30001 -ign_eof -quiet
# Got connected and then wrote the password
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.


