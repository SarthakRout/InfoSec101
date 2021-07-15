# PicoGym Web Exploitation Writeup

Author: [Parinay Chauhan](https://github.com/parinayc20) 

Challenge Page: [Cookies](http://mercury.picoctf.net:21485/)

## Walkthrough
I used burpsuite to solve this level. From the name of the problem it was quite clear that the problem deals with cookies. I cloned the url into the repeater tool of burp suite and processed the get request with different parameters of the only cookie being passed which was "name" after processing for some numbers, I found the flag by processing the get request for "name=18".

## Flag
`picoCTF{3v3ry1_l0v3s_c00k135_94190c8a}`

## Suggested modifications
I think that more parameters could be added to cookies to make it impossible for manually bruteforcing all the parameters and the need to initiate a brute force attack arises.