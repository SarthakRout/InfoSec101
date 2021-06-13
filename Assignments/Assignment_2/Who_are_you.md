# PicoGym Web Exploitation Writeup

Author: [Praveen Singh](https://github.com/GTA-VeteraN) 

Challenge Page: [Who are you?](http://mercury.picoctf.net:36622/) 

## Walkthrough
How did you solve this level? Include the complete thought process, even stuff that didn't work. Give explanations wherever necessary.

1. Inspected the page source and got nothing and there was nothing to interact with on the webpage.
2. So I just went to the Burp Suite Community Edition.
3. The webpage showed `Only people who use the official PicoBrowser are allowed on this site!`, so in the burp suite page there was only one line that mentioned about the user which is `User-Agent` so I wrote `User-Agent: picoBrowser` in the repeater and rendered it.
4. I got the next page which showed `I don't trust users visiting from another site.` which I got instantly that it indicates the use of `Referer`. This is because of the natas level where I got to know about Referer.
5. Then I added a line in burp as `referer: mercury.picoctf.net:36622`. And then I got another webpage saying `Sorry, this site only worked in 2018`.
6. Then I realised that I need to add another line regarding date in the burp.
7. So then I googled it and got that these are `HTTP Headers` and one of them is `Date`. Then I realised that this CTF is based completely on `HTTP Headers`.
8. So for all `HTTP Headers` , I used [this](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/) website.
9. So then I chose a random date of 2018 and added a new line `Date: Wed, 13 Jun 2018 10:00:00 GMT`.
10. Then a new webpage showed `I don't trust users who can be tracked` , so I got `DNT` header which is used for tracking.
11. So I added the line `DNT : 1` which meant not to be tracked.
12. Then comes a new message `This website is only for people from Sweden` and this one was the toughest.
13. I was not able to find any header regarding this (as I was looking for headers that captures the location and there was no headers regarding this), then I looked for a writeup where the IP address feature was used for this message.
14. So the header used was `X-Forwarded-For` which is used for identifying the originating IP address of a client, so then I looked for an IP address of Sweden and added another line `X-Forwarded-For: 31.15.63.255`.
15. Then comes another message `You're in Sweden but you don't speak Swedish?`, which means I have to change the language, for this I got the header `Accept-Language`.
16. So I added another line `Accept-Language: sv-fi` and then came the flag finally.


## Flag
`picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_0da16bb2}` 

## Useful resources (if any)

1. For the syntax and data for all the headers I used this website : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/]

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
```
Some more HTTP Headers should be included to make it more interesting and also helping us to gain knowledge about more HTTP headers.

```