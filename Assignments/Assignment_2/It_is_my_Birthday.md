# PicoGym Web Exploitation Writeup

Author: [Praveen Singh](https://github.com/GTA-VeteraN) 

Challenge Page: [It is my Birthday](http://mercury.picoctf.net:63578/) 

## Walkthrough
How did you solve this level? Include the complete thought process, even stuff that didn't work. Give explanations wherever necessary.

1. Firstly I looked on the source code and got nothing.
2. So there was two input for uplaoding pdf files in the form , so I tried to upload two random (different) pdf files and it showed `MD5 hashes do not match!`.
3. So then I uploaded same pdf file in both the input and it showed `Files are not different!`.
4. So then I checked hints and then read the question again which said something about MD5 hash so I read about MD5 hashes [here](http://www.unixwiz.net/techtips/iguide-crypto-hashes.html).
5. Then I concluded that I need to find two files with different data but having same MD5 sum which is referred to as `MD5 Collision`.
6. And I got it [here](https://www.mscs.dal.ca/~selinger/md5collision/) and I just uploaded them in the form and got the flag.

## Flag

`picoCTF{c0ngr4ts_u_r_1nv1t3d_5c8c5ce2}` 

## Useful resources (if any)

1. For getting details about MD5 hashing : [http://www.unixwiz.net/techtips/iguide-crypto-hashes.html]
2. For getting two different files having same MD5 sum : [https://www.mscs.dal.ca/~selinger/md5collision/]

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.