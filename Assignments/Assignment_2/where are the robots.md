# PicoGym Web Exploitation Writeup

Author: [Aarchie](https://github.com/aarchie-r)

Challenge Page: [where are the robots](https://jupiter.challenges.picoctf.org/problem/56830/)

## Walkthrough
First by looking at hint `What part of the website could tell you where the creator doesn't want you to look?`, I got an idea to search the codes by inspecting it to find something. But nothing seemed to be useful there. Then I again looked upon the name of puzzle something “robots” and hint directed me to search for how robots helping creator to hide something on website. And it showed me results of using “robots.txt” to use at the end of website address to go through it.
By using same, I got the message as-
```
User-agent: *
Disallow: /1bb4c.html
```
Something Disallow for user with `*`. Again I searched on internet for the same. I got related searches as ‘disallow user agent robots txt’ (some connection with prior experience) this directed me to a google site, where I found the meanings of this disallow and thus from reading there, I changed my address to end with “/1bb4c.html” by removing the “robots.txt”. And this worked, I found the flag with message as- 
```
Guess you found the robots
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}

```

## Flag
`picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}`

## Useful resources (if any)
https://developers.google.com/search/docs/advanced/robots/create-robots-txt

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
