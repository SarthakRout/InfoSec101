# Bandit Level 14 to 15 Writeup

Author: [Aarchie](https://github.com/aarchie-r)

Problem Page: [bandit14](https://overthewire.org/bandit/bandit14)

## List of Commands Used
```
nc - reads the port specified as the name of host
```

## Walkthrough

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
Thus it is clear that we need to read data on port 30000 from localhost, for that we wrote command to get connected to it-

nc localhost 30000

Then entered the current level password as given in gint and got output with the next level password.

## Password
`BfMYroe26WYalil77FoDi9qh59eK5xNr`

## Bash/Python script to automate the process
```
bandit14@bandit:~$ nc localhost 30000
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr

```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
