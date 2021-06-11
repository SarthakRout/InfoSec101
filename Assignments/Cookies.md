# PicoGym Web Exploitation Writeup

Author: [Aarchie](https://github.com/aarchie-r)

Challenge Page: [Cookies](http://mercury.picoctf.net:54219/)

## Walkthrough
As I opened the website it had a box entitled `Welcome to my cookie search page. See how much I like different kinds of cookies!` with a search option. First, I typed “cookies” by looking at the title for something to happen but only got message as `That doesn't appear to be a valid cookie.` Now I wrote `snickerdoodle` which was the text appearing on the box. And upon hitting the search tab, it gave message as `I love snickerdoodle cookies!`. But now I had no idea how to proceed. So I decided to inspect the site.
I looked upon the source codes but nothing seemed to be written there. Then I navigated through different tabs and found a tab `cookies` under storage section which hit my mind with the title of the puzzle. As selected that option I found values specified with request.
As I entered wrong text like cookies, it changed its value to "-1" and with snickerdoodle to "0". That showed, for every right text it seems to have nonzero values. I edited the value to 1 and refreshed the website and got the message `I love chocolate chip cookies!.`
Again changed the value to 2 and got `I love oatmeal raisin cookies!.` By increasing values various times, finally at value 18, I got message with the Flag.

## Flag
`picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}`

## Useful resources (if any)

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
