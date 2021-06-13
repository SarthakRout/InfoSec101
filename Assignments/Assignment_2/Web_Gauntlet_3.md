# PicoGym Web Exploitation Writeup

Author: [Akash Biswas](https://github.com/akashkb-a01)

Challenge Page: [Web Gauntlet 3](http://mercury.picoctf.net:63504/index.php) [Filter page](http://mercury.picoctf.net:63504/filter.php)

## Walkthrough
Going through the filter page, I noticed that it was exactly same as the filter page for Web Gauntlet 2. It read "Filters: or and true false union like = > < ; -- /* */ admin".
Also, the problem said "Only 25 characters this time" hinting that total length must be equal to 25. Also, hint3 said "sqlite", so I just searched for sqlite tutorial and got a list of basic operators used in sqlite.
There, I came across the operator "||" which would add two different strings and make new one. So, we can obtain the string admin by replacing it with adm'||'in ,here we can place the operator anywhere between a to n.
As, it is of length 11 (including beginning and ending '), so, we want a password of length 12 (excluding beginning and ending '). In solving Web Gauntlet 1, I used '1'!='2' , which returned true. Also, in the list of operators, I found that 'IS NOT' operator worked exactly like != and also, it was not on the filter page. 
So,I tried something like 1' IS NOT '2 and got the flag by reloading the filter page.


## Flag
`picoCTF{k3ep_1t_sh0rt_eb90a623e2c581bcd3127d9d60a4dead}`

## Useful resources 
https://www.tutorialspoint.com/sqlite/sqlite_operators.htm

