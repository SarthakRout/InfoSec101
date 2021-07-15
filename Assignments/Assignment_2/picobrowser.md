# PicoGym Web Exploitation Writeup

Author: [Akash Biswas](https://github.com/akashkb-a01)

Challenge Page: [picobrowser](https://jupiter.challenges.picoctf.org/problem/28921/)

## Walkthrough
Following the hint, I searched about browser detection and came across the term "User-Agent". I then searched how to change User-Agent and just used a custom User-Agent named "picobrowser" to get the flag.

## Flag
`picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}`

## Useful resources 
https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent

https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent

https://www.searchenginejournal.com/change-user-agent/368448/

## Suggested modifications 
In this problem, we just had to change the User-Agent but, there was a similar but more difficult problem named "Who are you?". Similar complexity could have been added in this one too.
