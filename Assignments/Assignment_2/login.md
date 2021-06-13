# PicoGym Web Exploitation Writeup

Author: [Soham Samaddar](https://github.com/CrypthiccCrypto) (Mention your name, GitHub profile)

Challenge Page: [login](https://login.mars.picoctf.net/)


## Walkthrough
First I inspected index.js. The username and password input by the user was directly being compared with some string on the client side. The password was passed as an input to a function atob(). So I researched about atob() and found that it was a function which decoded JavaScript Base64. So using atob() with the string with which the password was being compared, I was able to obtain the flag.

## Flag
`picoCTF{53rv3r_53rv3r_53rv3r_53rv3r_53rv3r}`

## Useful resources (if any)
https://www.w3schools.com/jsref/met_win_atob.asp

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
