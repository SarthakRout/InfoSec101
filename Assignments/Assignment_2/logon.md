# PicoGym Web Exploitation Writeup

Author: [Parinay Chauhan](https://github.com/parinayc20)

Challenge Page: [logon](https://jupiter.challenges.picoctf.org/problem/15796/)

## Walkthrough
This problem deals with some kind of cookie loophole. As given in the hint, the code does not check the password of anyone but Joe. The cookie informs the server that the admin id trying to login is the "admin" cookie. Thus after logging in as some random user with some random username and password, we can set the admin cookie to "admin=True", telling the server that the admin has logged in. Thus we get the flag from there.

## Flag
`picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}`
