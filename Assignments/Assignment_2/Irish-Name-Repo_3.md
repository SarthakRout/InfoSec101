# PicoGym Web Exploitation Writeup

Author: [Udit Prasad](https://github.com/uditpd3000)

Challenge Page: [Irish-Name-Repo 3](http://jupiter.challenges.picoctf.org:29132)

## Walkthrough
As mentioned in the hint, the password is encrypted. So i first looked for any key/hint but it was not there.

Then i found out this. 

`<input type="hidden" name="debug" value="0">`

in login.php.

Here i changed the value of debug to "1".

I tried the password `' or 1=1--` for which i got this SQL query as response

### SQL query: SELECT * FROM admin where password = '' be 1=1--' ###

So here simple ROT13 was used to encode the password.

Then i used `' be 1=1--` as password and yeah it worked.
   

## Flag
`picoCTF{3v3n_m0r3_SQL_06a9db19}`

## Useful resources (if any)

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
